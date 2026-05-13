# Solar Sales Performance Dashboard

<div align="center">

<h2>Solar Sales Performance Dashboard</h2>
<p><i>Sunniva Solar  |  H1 2024  |  Sales Analytics  |  Revenue Operations</i></p>

![SQL](https://img.shields.io/badge/SQL-Analysis-336791?style=flat-square&logo=postgresql&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-Advanced-217346?style=flat-square&logo=microsoft-excel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Tableau](https://img.shields.io/badge/Tableau-Reporting-E97627?style=flat-square&logo=tableau&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-065F46?style=flat-square)

</div>

---

## Business Context

## Business Context

This project was developed during my time as **Data Analyst at Sunniva Solar**, where I was responsible for building and maintaining the sales performance reporting infrastructure used by sales leadership and operations teams.

**Note on Data:** All performance figures, contract values, rep names, and revenue numbers in this project have been anonymized and adjusted from actual figures to protect company confidentiality. The data structure, KPI framework, analytical methodology, and business insights reflect real work performed in this role. Specific numbers are illustrative only.

The dashboard was designed to give leadership a single source of truth on rep performance, lead source effectiveness, regional trends, cancellation root causes, and revenue forecasting. The findings directly informed rep coaching decisions, territory adjustments, and the launch of the company's formal referral incentive program.

---

## Project Overview

| Detail | Info |
|--------|------|
| **Analyst** | George Anastasakos |
| **Company** | Sunniva Solar |
| **Role** | Data Analyst — Sales Performance & Revenue Operations |
| **Period** | H1 2024 (January – June) |
| **Dataset** | 1,244 sales opportunities across 8 reps, 3 regions, 6 lead sources |
| **Tools** | Excel, SQL, Power BI, Tableau, Google Sheets |
| **Industry** | Residential Solar / Renewable Energy / Direct Sales |

---

## Key Questions Answered

1. Which sales reps are performing above and below expectations — and by how much?
2. Which lead sources generate the highest close rates and installed revenue?
3. What is driving cancellations and how much revenue is being lost?
4. How does performance vary across Southwest, West, and Southeast regions?
5. What is the average system size, price per watt, and install timeline by rep?
6. What is the estimated revenue upside from closing identified performance gaps?

---

## Repository Structure

```
solar-sales-performance/
|
|-- README.md
|
|-- data/
|   |-- opportunity_data_raw.xlsx          <- 1,244 raw CRM opportunity records
|
|-- analysis/
|   |-- Sunniva_Solar_Sales_H1_2024.xlsx  <- Full workbook (5 sheets)
|
|-- sql/
|   |-- 01_rep_performance_summary.sql    <- Close rate, install rate, revenue by rep
|   |-- 02_lead_source_analysis.sql       <- Close rate and revenue by channel
|   |-- 03_cancellation_analysis.sql      <- Cancel reasons and revenue impact
|   |-- 04_regional_breakdown.sql         <- Performance by territory
|   |-- 05_monthly_trend.sql              <- Month-over-month KPI tracking
|
|-- docs/
    |-- sales_recommendations.md          <- Written findings and action plan
```

---

## Methodology

### Data Preparation
- Sourced from Sunniva Solar CRM export and project management system
- Standardized stage dispositions across all 8 reps and 3 regions
- Reconciled install dates with PTO (Permission to Operate) records
- Categorized cancellation reasons into 6 defined root cause buckets
- Validated contract values against signed agreement records

**Calculated Fields Derived:**
- `Close Rate` — Sits to Sold conversion percentage
- `Install Rate` — Sold to Installed conversion percentage
- `Cancellation Rate` — Cancelled / Total Sold
- `Price Per Watt ($/W)` — Contract Value / (System Size kW × 1000)
- `Revenue Per Rep` — Sum of installed contract values per rep
- `Avg Install Timeline` — Days from contract signed to system installed
- `vs Team Average` — Rep and source performance delta vs blended benchmark

### Analysis Approach
- Rep-level KPI benchmarking against team average with variance flagging
- Lead source close rate and revenue comparison across 6 channels
- Regional performance breakdown across Southwest, West, Southeast
- Cancellation root cause analysis by volume and revenue impact
- Loan type distribution and average contract value by financing product
- Revenue opportunity modeling with conservative 45-90 day implementation windows

---

## Key Findings

### Sales Rep Performance

| Rep | Close Rate | Install Rate | Cancel Rate | Avg kW | Avg Contract | Revenue |
|-----|-----------|-------------|-------------|--------|--------------|---------|
| Top Performer | 38% | 87% | 10% | 10.8 kW | $44,200 | Highest |
| Team Average | ~28% | ~88% | ~9% | 9.4 kW | $37,400 | Baseline |
| Lowest Performer | 18% | 92% | 6% | 7.9 kW | $31,800 | Lowest |

> Top performer generates approximately 3x the revenue of the lowest performer on the same lead pool.

---

### Lead Source Performance — Ranked by Close Rate

```
Lead Source         Close Rate    vs Team Avg    Revenue Share
--------------------------------------------------------------
Referral            High          Above avg +    High per sit
Inbound Call        Above avg     Above avg      Moderate
Partner             Above avg     Above avg      Moderate
Door to Door        At avg        Baseline       Highest volume
Event / Canvass     Below avg     Below avg      Low
Digital Lead        Lowest        Below avg -    High volume / low close
```

Referral converts at nearly double the rate of Digital Leads despite receiving a fraction of the investment.

---

### Cancellation Root Cause Analysis

| Cancel Reason | Priority | Revenue Impact | Recommended Action |
|---------------|----------|---------------|-------------------|
| Financing Fell Through | High | Highest | Mandatory credit pre-check at point of sale |
| Changed Mind | High | High | Install SLA enforcement; 48hr post-sign call |
| HOA Denial | Medium | Moderate | HOA screening checklist pre-contract |
| Roof Condition | Medium | Moderate | Roof assessment protocol during site survey |
| Too Expensive | Medium | Moderate | Tiered system sizing options at presentation |
| Company Closure / Move | Low | Low | No retention action viable |

---

### Regional Performance

- Southwest leads in total revenue and system size
- West region shows strongest close rate consistency across reps
- Southeast lags on both metrics — territory and rep quality review required

---

### Key Metrics Summary

| Metric | Value | Benchmark | Status |
|--------|-------|-----------|--------|
| Overall Close Rate | ~28% | 30% target | Monitor |
| Overall Install Rate | ~88% | 90% target | Monitor |
| Cancellation Rate | ~9% | 8% or below | Needs improvement |
| Avg System Size | ~9.4 kW | 10 kW target | Below target |
| Avg Price Per Watt | ~$3.80/W | $3.75 floor | On track |
| Avg Install Timeline | ~68 days | 60-day SLA | Needs improvement |

---

## Strategic Recommendations

| Priority | Category | Finding | Action |
|----------|----------|---------|--------|
| High | Rep Performance | ~20pt close rate gap between top and bottom rep on same leads | Record top rep pitch; build standardized playbook; mandate ride-alongs below avg |
| High | Cancellations | Financing fallthrough is top cancel reason — preventable | Mandatory credit pre-check before signing; same-day lender approvals |
| High | Lead Source | Referral closes nearly 2x Digital at fraction of the cost | Launch formal referral incentive; train all reps on referral ask post-install |
| High | Install Timeline | 68-day avg exceeds 60-day SLA — increases cancel risk | Weekly stalled install review; dedicated project coordinator at 45-day mark |
| Medium | Rep Ramp | Reps under 12 months tenure showing significantly lower close rates | Structured 90-day ramp program; pair new reps with top performers |
| Medium | System Size | Avg system size 0.6 kW below target — utility analysis underutilized | Train reps on 12-month consumption analysis at every appointment |
| Medium | Regional Gap | Southeast lags on close rate and revenue | Audit setter lead quality; review territory coverage; consider headcount |
| Low | Pricing | $/W variance of $0.80 across deals — margin inconsistency | Standardized pricing matrix; floor price of $3.65/W; manager approval below $3.75/W |

---

## Revenue Opportunity Estimate

| Initiative | Basis | Estimated Impact | Timeline |
|-----------|-------|-----------------|----------|
| Reduce cancellation rate to 8% | Save ~10% of current cancels | High | 30-60 days |
| Lift bottom 3 reps to team avg close rate | ~20pt close rate gap | High | 60-90 days |
| Scale referral to 15% of volume | Higher close rate per sit | Moderate | 90 days |
| Increase avg system size by 0.5 kW | ~$1,900 per install uplift | Moderate | 45 days |
| **Total Estimated Revenue Upside** | **Conservative assumptions** | **Significant** | **90 days** |

---

## SQL Samples

### Rep Performance Summary
```sql
SELECT
    sales_rep,
    COUNT(*) AS total_sits,
    SUM(sold) AS contracts_sold,
    ROUND(SUM(sold) * 100.0 / COUNT(*), 1) AS close_rate_pct,
    SUM(installed) AS systems_installed,
    ROUND(AVG(CASE WHEN installed = 1 THEN system_kw END), 2) AS avg_system_kw,
    ROUND(AVG(CASE WHEN installed = 1 THEN price_per_watt END), 2) AS avg_ppw,
    SUM(CASE WHEN installed = 1 THEN contract_value ELSE 0 END) AS total_revenue,
    RANK() OVER (ORDER BY SUM(CASE WHEN installed = 1 THEN contract_value ELSE 0 END) DESC) AS revenue_rank
FROM solar_opportunities
GROUP BY sales_rep
ORDER BY total_revenue DESC;
```

### Lead Source Close Rate Analysis
```sql
SELECT
    lead_source,
    COUNT(*) AS total_sits,
    SUM(sold) AS contracts_sold,
    ROUND(SUM(sold) * 100.0 / COUNT(*), 1) AS close_rate_pct,
    SUM(installed) AS installed,
    SUM(CASE WHEN installed = 1 THEN contract_value ELSE 0 END) AS total_revenue,
    ROUND(SUM(sold) * 100.0 / COUNT(*), 1) - AVG(team_avg_close_rate) AS vs_team_avg
FROM solar_opportunities
GROUP BY lead_source
ORDER BY close_rate_pct DESC;
```

### Cancellation Root Cause Analysis
```sql
SELECT
    cancel_reason,
    COUNT(*) AS cancellations,
    ROUND(COUNT(*) * 100.0 / SUM(COUNT(*)) OVER(), 1) AS pct_of_cancels,
    ROUND(AVG(contract_value), 0) AS avg_contract_lost,
    SUM(contract_value) AS total_revenue_lost
FROM solar_opportunities
WHERE cancelled = 1
    AND cancel_reason IS NOT NULL
GROUP BY cancel_reason
ORDER BY total_revenue_lost DESC;
```

### Monthly Performance Trend
```sql
SELECT
    sale_month,
    COUNT(*) AS total_sits,
    SUM(sold) AS contracts_sold,
    ROUND(SUM(sold) * 100.0 / COUNT(*), 1) AS close_rate_pct,
    SUM(installed) AS systems_installed,
    ROUND(SUM(CASE WHEN installed = 1 THEN system_kw ELSE 0 END), 1) AS total_kw_installed,
    SUM(CASE WHEN installed = 1 THEN contract_value ELSE 0 END) AS monthly_revenue
FROM solar_opportunities
GROUP BY sale_month
ORDER BY sale_month ASC;
```

---

## Tools Used

- **Excel / Google Sheets** — Data cleaning, pivot analysis, KPI modeling
- **SQL** — Performance aggregations, trend analysis, cancellation reporting
- **Power BI / Tableau** — Executive sales performance dashboard *(link coming soon)*

---

## About the Analyst

**George Anastasakos** — Data Analyst with direct experience in solar sales operations, CRM systems, and revenue performance reporting. This project was built from real operational work at Sunniva Solar, where I owned the sales analytics function and reported directly to sales leadership.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/george-anastasakos-010966408/)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Gsakos)

---

<div align="center">
<i>Built with precision. Driven by data. Focused on results.</i>
</div>
