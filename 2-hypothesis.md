# Hypotheses

## Hypothesis-Driven Analysis

Before opening the dataset or running any analysis, I formed four business hypotheses based on Olist's operating model and the structural challenges facing marketplace aggregators in geographically diverse markets. This approach kept the analysis purposeful—testing specific predictions rather than browsing data randomly.

---

## H1: Late Deliveries Are the Biggest Driver of Low Review Scores

**Hypothesis**: Delivery timing directly impacts customer satisfaction. Orders that arrive late will receive significantly worse review scores compared to on-time or early deliveries.

**Business Logic**: In e-commerce, unmet delivery expectations erode trust. If a customer expects a package on Tuesday and it arrives on Friday, the product quality becomes secondary to the frustration of waiting.

**Test Method**: Compare average review scores across delivery status categories (Early, On Time, Late) and severity bands (Late 1-3 days, Late 4-7 days, Late 7+ days).

---

## H2: São Paulo Dominates Revenue — The Rest of Brazil Is Underserved

**Hypothesis**: Revenue and order volume are heavily concentrated in São Paulo and the surrounding southeast states, while northern and remote regions contribute minimal GMV despite potential latent demand.

**Business Logic**: Olist's seller base grew organically in São Paulo, Brazil's economic centre. This creates a network effect—more sellers in SP attract more customers in SP, while remote states remain underserved due to insufficient seller density.

**Test Method**: Calculate total revenue (sum of price) by customer state and identify the percentage contribution of the top states. Build geographic maps showing customer vs. seller distribution.

---

## H3: Top 20% of Sellers Generate the Majority of GMV (Pareto Principle)

**Hypothesis**: A small subset of high-performing sellers accounts for a disproportionate share of total platform revenue, following the 80/20 rule commonly observed in marketplace economics.

**Business Logic**: Not all sellers are created equal. A few professional sellers with optimised logistics, better inventory, and competitive pricing will naturally capture most of the order volume.

**Test Method**: Rank all sellers by total revenue (sum of price), calculate the revenue contribution of the top 20% (592 out of 2,960 sellers), and visualise the concentration using a Lorenz curve (GMV Pareto Distribution).

---

## H4: Freight Cost as a Percentage of Product Price Is Much Higher in Northern States

**Hypothesis**: Customers in remote northern regions (Roraima, Rondônia, Amazonas, Maranhão) pay significantly more in freight relative to their order value compared to customers in São Paulo and the southeast.

**Business Logic**: Brazil's logistics infrastructure is concentrated in the southeast. Shipping to remote states involves longer distances, fewer carrier options, and higher per-kilometre costs. This freight burden makes products effectively more expensive for customers in underserved regions.

**Test Method**: Calculate `freight_pct = (freight_value / price) * 100` for each order, then compute the average freight percentage by customer state.

---

**Next Step**: Before I confirmed all 4 hypotheses  through Data analysis & Visualisation in [Analysis](./5-analysis.md), I decided to identify all the stakeholders in [Stakeholder-Map](./3-stakeholder-map)
