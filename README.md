# SaaS Subscriber Cancelation Analysis

## Executive Summary

SQL-based cancelation analysis in Snowflake identifying the key drivers of a 37.3% SaaS churn rate through cohort analysis, year-over-year trending, and exit survey data — with business impact modeling quantifying the revenue opportunity of targeted retention tactics.

1. Analyzed user-reported cancelation reasons across a three-question exit survey
2. Identified cohort-level churn patterns and year-over-year trends in cancelation behavior
3. Modeled the financial impact of targeted retention tactics and recommended three actionable interventions

---

### Business Problem

Leadership identified an above-average subscriber churn rate resulting in significant revenue loss. Before launching an enterprise-wide retention campaign, the team needed to understand the root causes driving cancelations. Fortunately, the company collects user-reported cancelation data through a structured exit survey — giving the analytics team direct access to subscriber-stated reasons for leaving.

[![Subscription Status Breakdown](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/churn_pie.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/churn_pie.png)

---

### Approach

1. **Data Generation & Preparation:** A synthetic dataset was generated using ChatGPT to simulate realistic SaaS cancelation behavior across multiple subscriber cohorts and exit survey response patterns, then loaded into a Snowflake data warehouse.
2. **Exploratory Data Analysis:** Used SQL (including multi-table joins, unions, CTEs, and window functions) to explore dataset structure, validate data integrity, and surface the distribution of cancelation reasons across all three exit survey slots.

[![Cancelation Reason 1](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/reason1.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/reason1.png)

[![Cancelation Reason 2](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/reason2.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/reason2.png)

[![Cancelation Reason 3](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/reason3.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/reason3.png)

3. **Cancelation Reason & Churn Analysis:** Applied CASE statements, views, unions, and cohort segmentation to understand why subscribers canceled, how they engaged with the cancelation workflow, and what churn rates looked like in aggregate, year-over-year, and by subscriber cohort.
4. **Data Visualization:** Visualized findings in HEX Notebook using pie, column, and line charts to communicate current state and year-over-year trends in a decision-ready format.

---

### Skills

* SQL (CTEs, multi-table joins, unions, window functions, CASE statements, views, cohort analysis)
* Data visualization
* Data wrangling and cleaning
* Data science notebooks (HEX)
* Snowflake Data Warehouse
* Business impact modeling

---

### Results & Business Recommendations

| Metric | Value |
| --- | --- |
| Overall Churn Rate | 37.3% |
| Top Cancelation Reason | Not Useful (primary) · Expensive (consistent across all three survey slots) |
| Competitive Threat | Went to a Competitor — #1 secondary reason, tied for #1 overall |
| Survey Engagement | Subscribers averaged 2.18 cancelation reasons — above typical exit survey completion |
| Highest-Risk Cohort | First-year subscribers; churn decreases significantly with tenure |
| Trending Concern | Bad customer service and expense complaints increased year-over-year |

**1) Cancelation Drivers:** 'Not Useful' was the most frequently cited primary cancelation reason, with 'Expensive' consistent across all three exit survey slots. When analyzed in aggregate without ranking, 'Expensive' and 'Went to a Competitor' tied as the top overall cancelation reasons — indicating price sensitivity and competitive displacement are the two most strategically significant churn drivers.

[![Cancelation Reasons Across All Subscriptions](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/total_reason.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/total_reason.png)

[![Aggregate Cancelation Reasons](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/agg_reason.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/agg_reason.png)

**2) Workflow Completion Rate:** Subscribers provided an average of 2.18 cancelation reasons — above typical exit survey completion — indicating the data is a reliable signal rather than low-quality noise.

[![Average Answers](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/avg_answers.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/avg_answers.png)

**3) Year-over-Year Trends:** Cancelation reasons as a percentage of total cancelations increased across all categories year-over-year, while null responses declined — indicating subscribers have become more willing to report multiple reasons over time. The most notable increases were in bad customer service and expense-related complaints.

[![Year over Year Cancelation Reasons](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/YoY_reason.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/YoY_reason.png)

**4) Cohort Churn Patterns:** Churn risk is highest among first-year subscribers and decreases meaningfully with each year of tenure. This pattern strongly supports an onboarding-focused intervention: retaining subscribers through their first year significantly improves long-term retention probability and subscriber lifetime value.

[![Percent Churn by Cohort Year](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/cohort.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/cohort.png)

**5) Business Impact Model:** To quantify the financial stakes, the following model applies benchmark pricing to the observed churn data.

> Note: The dataset is synthetic and does not include pricing. A benchmark monthly subscription price of $100/month is used for illustrative purposes.

[![Business Impact Model](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/raw/main/model.png)](https://github.com/abruce1184-stack/SaaS_Cancelation_Analysis/blob/main/model.png)

| Assumption | Value |
| --- | --- |
| Total subscribers | 59 |
| Churned subscribers (37.3%) | 22 |
| Monthly subscription price (benchmark) | $100/month |
| MRR at risk | $2,200/month |
| ARR at risk | $26,400/year |

| Retention Scenario | Subscribers Retained | Recovered ARR |
| --- | --- | --- |
| Recover 10% of churned subscribers | ~2 | ~$2,400 |
| Recover 20% of churned subscribers | ~4 | ~$4,800 |
| Recover 30% of churned subscribers | ~7 | ~$8,400 |

---

### Next Steps

1. **Onboarding Redesign:** Review training and documentation processes for new subscribers and implement structured onboarding milestones in the first 90 days — including feature adoption checkpoints, proactive check-in touchpoints, and advanced training resources for users who have not engaged with key features.
2. **Cancelation Rescue Tactic:** Consult with the product team and finance to model what level of promotional discount generates a positive LTV return at current churn rates, and implement a targeted offer in the cancelation workflow for subscribers citing 'Expensive.'
3. **Competitive Monitoring:** Establish a regular competitive monitoring cadence tracking competitor pricing, features, and positioning — and consider a targeted win-back campaign for subscribers who cited competitors as their reason for leaving.
4. **Measurement:** Build a live churn rate dashboard to replace ad hoc reporting and enable ongoing monitoring of cancelation trends by reason and cohort.
5. **Limitations:** The dataset is intentionally small, which limits statistical power of trend analysis. Further data collection and more granular subscriber event tracking would provide deeper insights.

---

👉 [View the full project write-up on Notion](your-notion-link)

*Part of the [Alicia Bruce Data & Financial Analytics Portfolio](your-notion-portfolio-link)*
