# SaaS Subscriber Cancelation Analysis

SQL-based cancelation analysis in Snowflake identifying the key drivers of a 37.3% SaaS churn rate through cohort analysis, year-over-year trending, and exit survey data — with business impact modeling quantifying the revenue opportunity of targeted retention tactics.

---

## Project Details

| | |
|---|---|
| **Industry** | SaaS / FinTech |
| **Tools** | SQL · Snowflake Data Warehouse · HEX Notebook |
| **SQL Techniques** | Multi-table joins, unions, CTEs, window functions, CASE statements, views, cohort analysis |
| **Data Source** | Synthetic dataset generated via ChatGPT, loaded into Snowflake |

---

## The Business Problem

A SaaS company experiencing above-average subscriber churn needed to understand the root causes driving cancelations before launching an enterprise-wide retention campaign. The company collects user-reported cancelation data through a structured three-question exit survey — giving the analytics team direct access to subscriber-stated reasons for leaving.

---

## Approach

- **Data Generation & Preparation** — Synthetic dataset generated using ChatGPT to simulate realistic SaaS cancelation behavior across multiple subscriber cohorts and exit survey response patterns, loaded into a Snowflake data warehouse
- **Exploratory Data Analysis (EDA)** — SQL used to explore dataset structure, validate data integrity, and understand descriptive statistics; techniques included multi-table joins, unions, CTEs, and window functions to surface cancelation reason distributions across all three exit survey slots
- **cancelation Reason & Churn Analysis** — CASE statements, views, unions, and cohort segmentation applied to understand cancelation drivers, workflow engagement, and churn rates in aggregate, year-over-year, and by subscriber cohort
- **Data Visualization** — Findings visualized in HEX Notebook using pie, column, and line charts to communicate current state and year-over-year trends in a decision-ready format

---

## Key Findings

| Metric | Finding |
|---|---|
| Overall churn rate | 37.3% |
| Top cancelation reason | Not Useful (primary) · Expensive (consistent across all three survey slots) |
| Competitive threat | Went to a Competitor — #1 secondary reason, tied for #1 overall |
| Survey engagement | Subscribers averaged 2.18 cancelation reasons — above typical exit survey completion |
| Highest-risk cohort | First-year subscribers churn at the highest rate; risk decreases significantly with tenure |
| Trending concern | Bad customer service and expense complaints increased year-over-year as % of total cancelations |

---

## Business Impact Model

> Note: The dataset is synthetic and does not include pricing. A benchmark monthly subscription price of $100/month is used for illustrative purposes.

| Assumption | Value |
|---|---|
| Total subscribers in dataset | 59 |
| Churned subscribers (37.3%) | 22 |
| Monthly subscription price (benchmark) | $100/month |
| MRR at risk | $2,200/month |
| ARR at risk | $26,400/year |

**Retention scenario modeling:**

| Scenario | Subscribers Retained | Recovered ARR |
|---|---|---|
| Recover 10% of churned subscribers | ~2 | ~$2,400 |
| Recover 20% of churned subscribers | ~4 | ~$4,800 |
| Recover 30% of churned subscribers | ~7 | ~$8,400 |

Given that churn risk is highest in the first year, even a modest improvement in first-year onboarding could meaningfully shift retention. Subscribers retained past year one churn at significantly lower rates — compounding the LTV return on any onboarding investment.

---

## Business Recommendations & Next Steps

**1. Redesign onboarding to address the 'Not Useful' finding**

The top cancelation reason across all survey slots is that subscribers do not find the product useful — most likely an onboarding and feature adoption issue rather than a product quality problem. Improving first-year onboarding simultaneously addresses the 'Not Useful' driver and the first-year cohort churn finding.

> ✅ **Next Step:** Implement structured onboarding milestones in the first 90 days — including feature adoption checkpoints, proactive check-in touchpoints, and advanced training resources for users who have not engaged with key features.

**2. Implement a price-sensitivity rescue tactic in the cancelation workflow**

For subscribers citing 'Expensive' as a cancelation reason, a targeted discount or promotional offer at the point of cancelation creates an opportunity to retain price-sensitive subscribers before they fully exit. Given that churn decreases significantly after year one, a short-term discount investment can yield meaningful long-term LTV recovery.

> ✅ **Next Step:** Consult with the product team and finance to model what level of promotional discount generates a positive LTV return at current churn rates.

**3. Build a competitive monitoring framework**

'Went to a Competitor' is the top secondary cancelation reason and tied for first overall — indicating competitive displacement is a meaningful and growing churn driver.

> ✅ **Next Step:** Establish a regular competitive monitoring cadence tracking competitor pricing, features, and positioning — and consider a targeted win-back campaign for subscribers who cited competitors as their reason for leaving.

---

## Full Project Narrative

👉 [View the full project write-up on Notion](your-notion-link)

---

*Part of the [Alicia Bruce Data & Financial Analytics Portfolio](your-notion-portfolio-link)*
