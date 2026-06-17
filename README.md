# Third-Party Vendor Risk Assessment & Monitoring Dashboard

A centralized risk monitoring solution for third-party vendor management — built to replace scattered spreadsheet-based vendor tracking with a single source of truth for risk scoring, compliance gaps, and contract renewals.

## Business Problem

Organizations working with hundreds of third-party vendors (IT services, cloud hosting, payment processing, logistics, consulting) often lack a centralized way to assess and monitor vendor risk. Assessments are manual, risk data is scattered across spreadsheets, and high-risk vendors or expiring contracts can go unnoticed until it's too late. This project builds a structured pipeline — from raw data to a weighted risk model to an interactive dashboard — to close that gap.

## Tools

SQL (SQLite) · Python (pandas, matplotlib, seaborn) · Power BI

## Approach

1. **SQL** — Designed a clean relational schema and loaded 500 vendor records, with queries covering risk distribution, category-level aggregation, and contract expiry windows.
2. **Python** — Performed exploratory analysis: risk score distribution, security-vs-risk correlation, and a full correlation matrix across all risk factors.
3. **Power BI** — Built an interactive dashboard with KPI cards, risk segmentation, compliance breakdowns, and a Top 10 highest-risk vendor view.

## Key Findings

- 127 of 500 vendors (25.4%) are rated High or Critical risk.
- Risk is **not concentrated in any single vendor category** — average risk scores across all 7 categories sit in a tight 40.6–44.2 range, meaning category alone isn't a reliable risk predictor.
- Information Security Score shows a clear negative correlation with Risk Score — weaker security maturity consistently tracks with higher risk.
- 75 contracts are due to expire within the next 90 days.
- Compliance gaps are widespread rather than isolated: 254 vendors (50.8%) are not ISO 27001 certified, 270 (54%) are not PCI DSS compliant, and 244 (48.8%) are not GDPR compliant.

## Repository Contents

- `schema.sql` — database schema
- `sample_queries.sql` — core SQL queries behind the KPIs
- `dashboard_overview.png` — Power BI dashboard
- `chart1_risk_distribution.png`, `chart2_security_vs_risk.png`, `chart3_correlation_heatmap.png`, `chart4_risk_by_category.png` — Python analysis

## Dashboard Preview

![Dashboard](dashboard_overview.png)
