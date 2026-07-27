# Key Insights & Recommendations

This document summarizes the main findings from the Atlas Labs attrition analysis and the corresponding recommendations for HR.

## 1. Overall Attrition Level

The company shows an overall attrition rate of **16.1%** (237 out of 1470 employees). The largest employee populations are concentrated in the Technology and Sales departments.

## 2. Overtime Is the Strongest Predictor of Attrition

Employees working overtime (OverTime = Yes) show a substantially higher attrition rate (~30%) compared to those who don't (~10%). This is the single strongest signal found in the dataset.

**Recommendation:** Review workload distribution in teams with a high share of overtime, and consider redistributing tasks or adding headcount where overtime is chronically high.

## 3. Tenure Strongly Correlates With Attrition

The highest attrition is observed among employees with the shortest tenure (0–1 year), decreasing steadily as tenure increases. The 5+ years group has the lowest attrition and is also the largest group by headcount.

**Recommendation:** Strengthen onboarding and mentoring programs during the first year of employment — this is the period of highest flight risk.

## 4. Business Travel Frequency

Employees who travel occasionally ("Some Travel") show a higher attrition rate than those who travel frequently or not at all — a non-obvious pattern worth investigating further (occasional travel may disrupt work-life balance more than a consistent travel routine).

## 5. Limitations of the Risk Score

The custom Risk Score (based on JobSatisfaction, WorkLifeBalance, and ManagerRating) turned out to be nearly identical across departments (31.06%–31.60%) and education fields (~30–32%), despite attrition rates varying meaningfully between these same groups. This is because satisfaction ratings in the dataset are fairly uniformly distributed (average ≈ 3/5 across the organization).

**Conclusion:** Self-reported satisfaction scores alone are not sufficient to predict attrition risk. In this dataset, behavioral variables — overtime and tenure — proved to be much stronger predictors than declarative satisfaction ratings.

## Summary of Recommendations

| Finding | Recommendation |
|---|---|
| High attrition tied to overtime | Audit workload in high-overtime teams |
| High attrition in first year | Invest in onboarding/mentoring |
| Uniform Risk Score across groups | Rebuild risk model using overtime + tenure instead of satisfaction alone |
| Non-obvious travel pattern | Investigate further with qualitative HR feedback |
