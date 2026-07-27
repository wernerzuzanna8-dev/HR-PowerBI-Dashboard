# HR PowerBI Dashboard 

An interactive Power BI dashboard analyzing employee attrition at the fictional company. Built on top of a DataCamp course project, extended with custom DAX measures, additional analysis, and business recommendations.

## Project Goal

Identify which employees, and under what circumstances, are most likely to leave the company, and translate that into actionable recommendations for HR.

## Dashboard Structure

- **Overview** – key KPIs (TotalEmployees, ActiveEmployees, InactiveEmployees, % Attrition Rate), hiring trends over time, active employees by department and job role
- **Demographic** – age, gender, marital status, ethnicity, and salary distribution
- **Performance Tracker** – per-employee view: satisfaction, work-life balance, and manager rating trends over time
- **Attrition** – core attrition analysis: attrition by tenure, business travel, overtime, department/job role, and yearly trend
- **Employee Risk Analysis** *(custom addition)* – original Risk Score measure and tenure-vs-attrition analysis
- **Key Insights** *(custom addition)* – summary of findings and recommendations for HR

## Original Contributions

Beyond the original DataCamp template, this project adds:

1. **Risk Score** – a custom DAX measure combining JobSatisfaction, WorkLifeBalance, and ManagerRating into a single 0–100% attrition risk indicator, visualized by department, job role, and education field
2. **Tenure Group analysis** – segmenting employees by years at the company (0-1, 2-3, 4-5, 5+) and comparing attrition across groups
3. **Supporting DAX measures** (Employee Count, tenure buckets, etc.)
4. **Key Insights page** with business conclusions and HR recommendations (see [INSIGHTS.md](INSIGHTS.md) for full detail)

## Key Findings (summary)

- Overall attrition rate: **16.1%** (237 of 1470 employees)
- **Overtime** is the strongest predictor of attrition in this dataset — employees working overtime leave at a much higher rate (~30%) than those who don't (~10%)
- **Tenure** strongly correlates with attrition — risk is highest in the first year and declines steadily with seniority
- The custom **Risk Score**, based on satisfaction ratings, turned out nearly identical across all departments (~31%) — a finding in itself, showing that self-reported satisfaction is a weak predictor compared to behavioral variables like overtime and tenure



## Dataset

The dataset used in this project comes from the DataCamp course exercise files:
[Download dataset](https://s3.amazonaws.com/assets.datacamp.com/production/repositories/6064/datasets/Exercises+and+Datasources/case-study-hr-analytics-in-power-bi.zip)

## Tools

- Power BI Desktop (Power Query, DAX, custom visuals)

## Data Model

The report uses a **star schema**, with one central fact table connected to several dimension tables:

**Fact table**
- `FactPerformanceRating` – one row per employee performance review, containing EmployeeID, JobSatisfaction, EnvironmentSatisfaction, RelationshipSatisfaction, SelfRating, ManagerRating, ReviewDate, and TenureYears

**Dimension tables**
- `DimEmployee` – employee attributes: Age, AgeBins, Attrition, BusinessTravel, Department, DistanceFromHome, Education, EducationField, Gender, MaritalStatus, Salary, etc.
- `DimDate` – calendar table (Date, DayName, DayNumber, DayOfWeek, etc.) enabling time-based analysis
- `DimEducationLevel` – lookup table mapping education level codes to labels
- `DimSatisfiedLevel` – lookup table mapping satisfaction rating codes (1–5) to labels (e.g. "Very Dissatisfied" → "Very Satisfied")
- `DimRatingLevel` – lookup table mapping manager/self-rating codes to labels (e.g. "Unacceptable" → "Above and Beyond")

All dimension tables connect to the fact table via one-to-many relationships, which is what allows a single rating or satisfaction score in `FactPerformanceRating` to be sliced and labeled consistently across every page of the report.


## Limitations

The dataset is synthetic (generated for course purposes), so some variables (e.g. satisfaction ratings) show limited variance. The methodology and findings are nonetheless fully transferable to real-world HR data.


