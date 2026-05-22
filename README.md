# Olist E-Commerce Business Analysis (2016–2018)

## Executive Summary

Olist, a Brazilian e-commerce marketplace aggregator, faced severe geographic concentration during 2016–2018. São Paulo generated 42% of platform revenue while customers in northern states paid freight costs exceeding 50% of product price — more than double São Paulo's baseline. I analysed 96,478 delivered orders across Brazil's 27 states using Excel pivot tables and Tableau dashboards, testing four hypotheses across delivery performance, revenue concentration, seller distribution, and freight burden. The analysis traced all three business risks to a single structural root cause: seller concentration in São Paulo.

---

## Hypotheses

Before touching the data, I formed four business hypotheses to guide the analysis:

- **H1:** Late deliveries are the biggest driver of low review scores
- **H2:** São Paulo dominates revenue — the rest of Brazil is underserved
- **H3:** Top 20% of sellers generate the majority of GMV (Pareto Principle)
- **H4:** Freight cost as a percentage of product price is much higher in northern states

All four hypotheses were validated through structured analysis. Detailed hypothesis testing logic and predictions are documented in [Hypothesis](./hypothesis.md).

---

## Dashboard Preview

![Olist E-Commerce Dashboard](./images/dashboard_full_view.png)

The dashboard visualises delivery performance collapse, geographic revenue concentration, seller Pareto distribution, and freight cost inequality across Brazil's 27 states. Interactive Tableau visualisations include:

- **Delay Severity vs. Review Score** — Shows progressive satisfaction degradation from 4.30 (early) to 1.70 (7+ days late)
- **Revenue by State** — SP: R$4.62M (42%), top 3 states control 70% of GMV
- **GMV Pareto Curve** — Lorenz curve proving top 20% of sellers (592) generate 82.54% of platform revenue
- **Freight % by State** — Northern states pay 50-60% freight burden vs. 25% in São Paulo
- **Monthly Growth Trend** — Platform peaked at 7,289 orders/month (Nov 2017), then plateaued
- **Geographic Maps** — Customer distribution (all 27 states) vs. seller concentration (SP: 1,764 sellers)

Full dashboard available in `dashboard/Olist_Analysis_Dashboard.pptx`.

---

## Business Problem

Olist faced three interconnected structural gaps that limited sustainable growth and created revenue vulnerability:

1. **Freight Cost Inequality**: Customers in remote northern states (Roraima, Rondônia, Maranhão) paid freight exceeding 50% of product price compared to ~25% in São Paulo, suppressing demand through a "distance tax."

2. **Delivery Performance Collapse**: Late deliveries caused review scores to drop from 4.03 (on-time) to 2.27 (late)—a 1.76-point satisfaction gap that destroyed customer retention and repeat purchase behaviour.

3. **Geographic Revenue Concentration**: São Paulo generated 42% of platform revenue, with the top three states accounting for ~70% of GMV, exposing the platform to regional economic shocks and growth saturation.

These gaps were causally linked: heavy seller concentration in São Paulo forced most orders into long-haul fulfilment, which drove both high freight costs and increased late delivery risk in remote regions. The analysis quantified these gaps and traced them to a root cause—insufficient seller density outside the southeast.

Detailed problem context, business impact, and analytical questions are documented in [Business Problem](./business-problem.md).

---

## Project Structure

This analysis follows the Business Analyst workflow from problem identification through actionable recommendations:

### 1. [Business Problem](./business-problem.md)
Defines Olist's operating model, the structural geographic concentration problem, business impact quantification, and the four hypotheses formed before analysis began.

### 2. [Hypothesis](./hypothesis.md)
Documents the four business hypotheses (H1-H4) formed before touching the data, including predictions, business logic, test methods, and validation results.

### 3. [Stakeholder Map](./stakeholder-map.md)
Identifies all parties impacted by or influencing the analysis, classifies them using a Power/Interest Grid (RACI framework), and determines engagement strategies for each stakeholder group (CEO, Operations, Sales, Investors, Sellers, Customers).

### 4. [Current State (AS-IS)](./current-state.md)
Maps the operational order fulfilment process using a BPMN swimlane diagram across four actors (Customer, Olist System, Seller, Carrier). Identifies three sequential handoff points where delays accumulate and explains why the current workflow fails for long-distance orders.

### 5. [Analysis](./analysis.md)
Documents every step of the data analysis process using the STAR framework (Situation, Task, Action, Result):
- **Phase 1:** Data ingestion & consolidation (loaded 9 CSVs, created MASTER sheet with XLOOKUPs)
- **Phase 2:** Data cleaning & filtering (96,478 delivered orders, 8 calculated columns)
- **Phase 3:** Data Analysis (6 pivot tables testing H1-H4)
- **Phase 4:** Data Visualisation (7 visualisations, including a technically complex GMV Pareto curve with 8 custom calculated fields)

Shows exact formulas, business logic behind each metric, and analytical decisions made at each phase.

### 6. [Gap Analysis](./gap-analysis.md)
Quantifies the distance between current performance (AS-IS) and desired future state (TO-BE) across three dimensions:
- Freight cost: 50-60% → target <20% (30-40 percentage point reduction needed)
- Delivery performance: 2.27 late avg → target >3.5 (1.23-point improvement needed)
- Revenue concentration: SP = 42% → target <25% (17 percentage point diversification needed)

Applies the **Nadler-Tushman Congruence Model** to diagnose root causes across Work (processes), People (skills), Structure (org design), and Culture (values). Concludes that seller concentration drives all other gaps.

### 7. [Insights](./insights.md)
Translates analytical findings into strategic business implications:
- Late delivery = R$392K+ in lost customer lifetime value
- Geographic concentration = 40% revenue at risk from SP-region shock
- Pareto concentration = top 600 sellers control platform health
- Distance tax = 10-15% suppressed order volume in northern states
- Seller concentration is the root cause of freight and delivery gaps
- Growth ceiling reached without geographic expansion

### 8. [Business Recommendations](./business-recommendations.md)
Provides three prioritised, actionable recommendations with expected impact:

1. **Establish regional carrier partnerships** — Reduce freight costs by 30-40 percentage points in northern states
2. **Reduce transit time in remote routes** — Cut late delivery rate from 6.8% to <3%
3. **Launch seller acquisition campaign** — Recruit 500 new sellers in underserved states

Expected outcomes: 15% order volume growth in northern states, improved customer satisfaction, and revenue diversification away from São Paulo.

### 9. [Data Dictionary](./data-dictionary.md)
Technical reference documenting all calculated columns and custom fields:
- 8 Excel calculated columns (delivery_delay_days, delivery_status, delay_band, freight_pct, etc.)
- 8 Tableau calculated fields (True GMV, Concentration Ratio, Top 20% Sellers GMV, etc.)
- Exact formulas, data types, business logic, and usage context for each metric

---

## Key Findings

1. **Late deliveries collapse satisfaction**: Orders 7+ days late averaged 1.70 review scores vs. 4.30 for early deliveries — a 2.6-point gap that destroys repeat purchase potential.

2. **São Paulo controls 42% of GMV**: The top three states (SP, RJ, MG) generated ~70% of platform revenue, creating high concentration risk.

3. **Top 20% of sellers generate 82.5% of GMV**: Extreme Pareto concentration (592 of 2,960 sellers) means platform health depends on a small group of high performers.

4. **Northern states pay double the freight burden**: Customers in Roraima and Rondônia paid 58–60% of the product price in freight vs. 25% in São Paulo.

5. **Seller concentration in SP is the root cause**: 1,764 of 2,960 sellers operate from São Paulo. This drives both freight and delivery gaps in remote regions.

6. **Growth hit a ceiling in late 2017**: Monthly orders peaked at 7,289 (Nov 2017), then plateaued — indicating saturation in established markets.

---

## Tools & Methods

**Tools Used:**
- **Excel** (Power Query, XLOOKUP, Pivot Tables, Calculated Columns) — Data consolidation, transformation, and aggregation
- **Tableau Desktop** (LOD Calculations, Table Calculations, Geographic Mapping) — Dashboard visualisation and Pareto analysis
- **draw.io** (BPMN, Power/Interest Grid, Database Schema) — Process mapping and stakeholder analysis

**Frameworks Applied:**
- **STAR** (Situation-Task-Action-Result) — Structured analysis documentation in analysis.md
- **RACI** (Responsible-Accountable-Consulted-Informed) — Stakeholder classification in stakeholder-map.md
- **Nadler-Tushman Congruence Model** — Root cause diagnosis in gap-analysis.md (Work, People, Structure, Culture)
- **AS-IS vs. TO-BE** — Gap quantification framework in gap-analysis.md
- **Pareto Principle** (80/20 Rule) — Seller concentration analysis

---

## Data Source

**Dataset:** Olist Brazilian E-Commerce Public Dataset  
**Source:** [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/data)  
**Time Period:** September 2016 – August 2018  
**Orders Analysed:** 96,478 delivered orders (97% of the total dataset)  
**Sellers:** 2,960 unique sellers  
**Customers:** 99,441 unique customers  
**Geographic Coverage:** All 27 Brazilian states  
**Olist Website:** [https://olist.com/ecommerce/](https://olist.com/ecommerce/)

---

## Repository Contents

```
olist-analysis/
├── README.md (this file)
├── business-problem.md
├── hypothesis.md
├── stakeholder-map.md
├── current-state.md
├── analysis.md
├── gap-analysis.md
├── insights.md
├── business-recommendations.md
├── data-dictionary.md
├── images/
│   ├── database_schema.png (Physical ERD created by analyst)
│   ├── erd_olist_kaggle.png (Original ERD from Kaggle dataset)
│   ├── bpmn_process_map.png (AS-IS order fulfilment process)
│   ├── stakeholder_map.png (Power/Interest Grid)
│   ├── customers_by_state.png (Geographic map)
│   ├── sellers_by_state.png (Geographic map)
│   ├── h1_delay_severity_vs_score.png (Hypothesis 1 visualisation)
│   ├── h2_revenue_by_state.png (Hypothesis 2 visualisation)
│   ├── h3_gmv_pareto_distribution.png (Lorenz curve)
│   ├── h3_seller_concentration_kpi.png (KPI card)
│   ├── h4_freight_by_state.png (Hypothesis 4 visualisation)
│   ├── monthly_growth.png (Time series chart)
│   └── dashboard_full_view.png (Complete dashboard)
├── data/
│   ├── raw_data/
│   │   └── README.md (Points to Kaggle source)
│   └── Olist_Business_Analysis.xlsx (Analysis workbook)
└── dashboard/
    └── Olist_Analysis_Dashboard.pptx (Tableau export)
```

---

## About This Analysis

This project demonstrates end-to-end Business Analysis capabilities:
- Hypothesis-driven approach before data exploration
- Structured data transformation and consolidation
- Pivot table aggregation and statistical analysis
- Advanced Tableau visualisation (LOD calculations, table calculations, Lorenz curves)
- Stakeholder classification and engagement planning
- Process mapping using BPMN notation
- Root cause diagnosis using Nadler-Tushman framework
- Gap quantification (AS-IS vs. TO-BE)
- Prioritised, actionable recommendations with ROI estimates

The analysis shows that Olist's geographic concentration risk can be addressed through three coordinated interventions—carrier partnerships, delivery window optimisation, and seller acquisition—which require an R$250K investment over 12 months to unlock 15% order volume growth in underserved regions and diversify revenue away from São Paulo's 42% dependency.

---

**Analysis Date:** May 2026  
**Analyst:** Varneet Singh  
**Dataset Period:** September 2016 – August 2018  
**Business Context:** Brazilian E-Commerce Marketplace Aggregation
