# -HR_Attrition_Analysis

# HR Analytics Dashboard — Employee Attrition Analysis

A Power BI portfolio project that analyzes employee attrition, workforce demographics, job characteristics, satisfaction, overtime, and compensation. The goal is to turn HR data into practical insights that can help HR teams identify employee groups with higher turnover and investigate possible retention risks.

> **Important:** This is an exploratory analytics project using a sample HR dataset, not verified data from a real company. The results show associations, not proof that any factor causes employees to leave.

## Project at a Glance

| Item | Details |
|---|---|
| Project | HR Analytics — Employee Attrition Analysis |
| Main tool | Microsoft Power BI |
| Supporting tool | Microsoft Excel |
| Dataset size | 1,470 employee records |
| Attrition records | 237 |
| Current employees | 1,233 |
| Overall attrition rate | 16.12% |
| Report pages | Executive Dashboard; Attrition Analysis; Workforce Analysis; Job & Satisfaction Analysis |
| Project type | HR / People Analytics |
| Audience | HR managers, people analytics teams, and business stakeholders |

## Business Problem

Employee turnover can increase recruitment and onboarding costs, interrupt team productivity, and lead to loss of organizational knowledge. HR stakeholders need a clear view of attrition patterns to decide where to investigate retention risks.

This dashboard helps answer questions such as:

- How many employees are in the dataset, and how many have left?
- What is the overall attrition rate?
- How does attrition differ by overtime, department, job role, age, gender, and marital status?
- How are job satisfaction, work-life balance, and other employee ratings associated with attrition?
- How does attrition vary across monthly income bands and tenure?
- Which employee groups may warrant deeper investigation by HR?

## Dataset and Data Preparation

The workbook contains 1,470 employee records and fields covering:

- **Employee profile:** age, gender, marital status, education, and education field
- **Organization:** department, job role, job level, and business travel
- **Compensation:** monthly income, daily/hourly/monthly rates, salary hike, and stock option level
- **Employment history:** total working years, years at company, years in current role, time since promotion, and years with current manager
- **Work experience and engagement:** overtime, training, performance rating, job involvement, satisfaction ratings, and work-life balance
- **Outcome:** attrition status and current/ex-employee label

The accompanying Excel workbook is organized into these sheets:

1. `01_Raw_Data`
2. `02_Data_Validation`
3. `03_KPI_Analysis`
4. `04_Attrition_Analysis`
5. `05_Demographic_Analysis`
6. `06_Job_Analysis`
7. `07_Satisfaction_Analysis`
8. `08_Compensation_Analysis`
9. `09_Pivot_Analysis`
10. `10_Dashboard`

The validation sheet reports 1,470 records, zero missing cells, and zero duplicate employee IDs. These are checks reported by the supplied workbook; rerun validation if the source data is changed.

## Power BI Report Pages

### 1. Executive Dashboard
High-level view of employee headcount, attrition, attrition rate, and workforce breakdowns. Intended for quick review by HR leaders.

### 2. Attrition Analysis
Explores attrition patterns across selected employee segments, including overtime and other workforce characteristics.

### 3. Workforce Analysis
Provides demographic and workforce composition views to compare employee groups.

### 4. Job & Satisfaction Analysis
Examines job-related characteristics and satisfaction measures alongside attrition.

The report includes interactive slicers and cards/charts to support segment-level exploration. Select a slicer value to filter the relevant report visuals; use the report's reset/clear-filter controls if available in the published version.

## Key Findings

The following figures are calculated from the supplied workbook's summary sheets:

| Finding | Result | Interpretation |
|---|---:|---|
| Total employee records | 1,470 | Overall dataset size |
| Employees recorded as attrition | 237 | Employees marked as having left |
| Current employees | 1,233 | Employees marked as current |
| Overall attrition rate | 16.12% | 237 divided by 1,470 |
| Attrition rate for employees with overtime | 30.53% | Higher observed attrition in this segment |
| Attrition rate for employees without overtime | 10.44% | Lower observed attrition in this segment |
| HR department attrition rate | 19.05% | 12 attrition records among 63 employees |
| R&D department attrition rate | 13.84% | 133 attrition records among 961 employees |
| Sales department attrition rate | 20.63% | 92 attrition records among 446 employees |
| Attrition rate for monthly income below 3,000 | 28.61% | Highest among the income bands shown in the workbook summary |

### What these findings suggest

- The overtime group has a substantially higher observed attrition rate than the non-overtime group. HR should investigate workload, scheduling, role expectations, and manager practices before deciding on interventions.
- Sales has a higher observed attrition rate than R&D in this dataset. Role mix, targets, travel, compensation, and workload may be useful follow-up dimensions.
- The lowest monthly-income band has a higher observed attrition rate than the higher bands shown in the summary. This is a signal for further analysis, not proof that income alone explains attrition.
- Department and demographic comparisons should be interpreted alongside employee counts. Small groups can have volatile rates.

**Do not interpret these patterns as causal conclusions.** The dashboard is descriptive. It does not establish why an employee left, and it does not prove that changing one factor will reduce attrition.

## KPIs

Recommended core measures used or relevant to this report:

- **Total Employees** — distinct count of employee IDs
- **Attrition Count** — count of employees with Attrition = `Yes`
- **Current Employees** — count of employees with Attrition = `No` (or the supplied current-employee field)
- **Attrition Rate** — attrition count divided by total employees
- **Average Monthly Income** — average monthly income for the selected employee segment
- **Average Tenure** — average years at company for the selected employee segment

Example DAX measures (adjust table and column names to match the model):

```DAX
Total Employees =
DISTINCTCOUNT ( HR_Analytics[Employee_ID] )

Attrition Count =
CALCULATE (
    DISTINCTCOUNT ( HR_Analytics[Employee_ID] ),
    HR_Analytics[Attrition] = "Yes"
)

Current Employees =
CALCULATE (
    DISTINCTCOUNT ( HR_Analytics[Employee_ID] ),
    HR_Analytics[Attrition] = "No"
)

Attrition Rate =
DIVIDE ( [Attrition Count], [Total Employees], 0 )
```

Format `Attrition Rate` as a percentage. Confirm the model's table and column names before pasting these measures.

## Tools and Skills Demonstrated

- Microsoft Excel: data review, validation checks, KPI summaries, and pivot analysis
- Power BI: report design, KPI cards, charts, slicers, and interactive filtering
- HR / People Analytics: attrition-rate analysis, workforce segmentation, and retention-risk exploration
- Business communication: translating metrics into follow-up questions for HR stakeholders

## Suggested Business Actions

1. Review overtime workload and staffing patterns by department and job role.
2. Compare attrition with tenure, job role, manager tenure, satisfaction, and compensation together rather than in isolation.
3. Investigate the Sales department's higher observed rate, taking employee counts and role mix into account.
4. Interview or survey employees to understand reasons that are not captured in the dataset.
5. Track attrition rate over time in a real company dataset before judging whether any intervention worked.

These are investigation ideas, not recommendations to make employment decisions about individual employees based solely on this dashboard.




## Author

**Praveen Kurma**

Aspiring Data Analyst | Excel • SQL • Power BI

- LinkedIn: [Praveen Kurma](https://www.linkedin.com/in/praveen-kurma-47a876357)
- GitHub: [PraveenK416](https://github.com/PraveenK416)

---

If you found this project useful, feel free to ⭐ the repository.
