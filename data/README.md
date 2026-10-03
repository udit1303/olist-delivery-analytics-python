# Olist Brazil E-commerce Delivery Performance — Python Portfolio Project

## Executive summary

This project analyzes late-delivery performance using the Olist Brazilian e-commerce dataset. The objective was to move from a broad operational problem to a focused, evidence-based action plan.

### Business problem

**How can an e-commerce operations team identify and prioritize the drivers of late delivery instead of treating the problem as a single network-wide KPI?**

### Key findings

- **96,470** delivered orders were usable for delivery-performance analysis.
- **6,534 orders (6.77%)** were delivered after the estimated delivery date.
- **32.02% of late orders** were delayed by more than 10 days.
- Customer-state performance varied materially; **RJ recorded a 12.11% late rate** and contributed **22.88% of all late orders**.
- Late orders showed **+19.91 days of additional carrier-transit time** versus on-time orders, compared with **+3.04 days of additional seller-handling time**.
- Late rate increased with shipping distance: **4.42% for <100 km** vs **12.09% for >2,000 km**.
- Peak periods showed material deterioration, with **18.96% late in March 2018**.
- Product category showed a narrower spread than geography; heavy shipments were somewhat riskier, with **8.86% late for >10 kg** vs **6.46% for <1 kg**.
- **SP → RJ** was the largest high-impact lane: **8,161 orders, 1,153 late, 14.13% late**, with **600 theoretical excess late orders** relative to the 6.77% network benchmark.
- The top 10 lanes represented **65.52% of all late orders**; benchmarking those lanes to the network average produced **995 theoretical addressable late orders (15.23% of all late orders)**.

## Approach

The analysis followed a business-first diagnostic sequence:

1. Establish the delivery baseline.
2. Quantify delay severity.
3. Compare performance by customer geography.
4. Compare product-category performance.
5. Examine seller-level performance.
6. Combine seller and customer geography.
7. Split fulfillment time into seller handling and carrier transit.
8. Test the relationship between distance and lateness.
9. Identify high-impact origin–destination lanes.
10. Test product-weight and freight characteristics.
11. Test seasonality and peak-period deterioration.
12. Reconcile the final analytical baseline.
13. Prioritize intervention areas using a network benchmark.
14. Translate findings into an operations action plan.

## Strategic diagnosis

The evidence points to a **network/transit problem concentrated in specific lanes and amplified by long-distance shipping and peak-period capacity pressure**. Seller handling and heavy shipments are secondary levers rather than the primary focus.

## Recommended action plan

### 0–30 days — Diagnose & design

- Audit the priority lanes beginning with SP → RJ, followed by SP → BA, SP → ES and SP → CE.
- Compare carriers, hubs, line-haul schedules and planned vs actual transit.
- Establish a lane-level SLA baseline.

### 31–60 days — Pilot & learn

- Test carrier-capacity reallocation on priority lanes.
- Test dispatch cut-off and route changes.
- Introduce targeted handling rules for heavy/bulky shipments.

### 61–90 days — Scale & govern

- Scale interventions that improve lane performance.
- Institutionalize peak-season capacity planning.
- Run a monthly lane scorecard using Late %, carrier transit days and excess late orders.

## Portfolio deliverables

- `notebooks/01_olist_delivery_analysis.ipynb` — analysis notebook
- `presentation/Olist_Brazil_Delivery_Portfolio_Story.pptx` — executive story deck
- `README.md` — project overview and business narrative
- `requirements.txt` — Python packages
- `data/README.md` — dataset source / usage notes

## Tools

Python, pandas, NumPy, Matplotlib, Jupyter Notebook

## Important methodology note

The final baseline uses this definition:

> **Late delivery = actual customer delivery date is later than estimated delivery date, among delivered orders with both dates available.**

This project is an analytical portfolio case study. The benchmark-based “addressable late orders” figures are opportunity estimates, not causal forecasts.
