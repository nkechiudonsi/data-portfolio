# Sales & Customer Analytics — Whispers of Beauty Inc.

> **Impact:** 15% increase in sales · 20% boost in customer retention · 50% faster report generation · 95% data accuracy

## Project Overview

This project showcases the end-to-end data analytics work performed as Junior Data Analyst at **Whispers of Beauty Inc.** (Sept 2012 – Jan 2019), a retail beauty business. The work involved identifying market trends, cleaning operational data, and delivering BI dashboards that shaped business decisions.

---

## Business Problem

The company was generating sales data but had no systematic way to:
- Identify top-performing products and customers
- Detect seasonal trends early enough to act on them
- Trust the data — inconsistencies in entry meant decisions were based on unreliable figures

---

## My Approach

### 1. Data Cleaning & Validation Pipeline
- Standardized product naming conventions across 4 years of historical data
- Removed duplicates, corrected outliers, and filled missing values using R and Python
- Established a repeatable cleaning script run monthly — reducing prep time from hours to minutes

### 2. SQL Analysis
Key queries developed:
- Customer lifetime value (CLV) segmentation
- Month-over-month sales growth by product category
- Churn risk identification (customers with declining purchase frequency)

### 3. Visualization & Reporting
- Built Tableau dashboards showing sales trends, regional performance, and customer segments
- Reduced weekly report generation time by **50%** through automated data refresh pipelines
- Presented insights to management monthly

---

## Key Results

| Metric | Before | After |
|---|---|---|
| Data accuracy | ~70% (estimated) | **95%** |
| Report generation time | ~4 hours/week | **~2 hours/week** |
| Sales growth (year-on-year) | Flat | **+15%** |
| Customer retention rate | Baseline | **+20%** |

---

## Tools & Technologies

![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)

---

## Repository Structure

```
sales-analysis/
├── data/
│   └── sample_sales_data.csv       # Anonymised sample dataset
├── notebooks/
│   └── sales_analysis.ipynb        # Full EDA and trend analysis
├── sql/
│   ├── customer_segmentation.sql
│   ├── monthly_growth.sql
│   └── churn_risk.sql
├── reports/
│   └── sales_dashboard_mockup.png  # Dashboard screenshot
└── README.md
```

---

## Sample Analysis Preview

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load and clean sales data
df = pd.read_csv('data/sample_sales_data.csv')
df['date'] = pd.to_datetime(df['date'])
df['revenue'] = df['quantity'] * df['unit_price']

# Monthly revenue trend
monthly = df.groupby(df['date'].dt.to_period('M'))['revenue'].sum()

monthly.plot(kind='line', figsize=(10, 4), title='Monthly Revenue Trend')
plt.ylabel('Revenue (NGN)')
plt.tight_layout()
plt.savefig('reports/monthly_trend.png')
```

---

*Part of [Nkechi Udonsi's Data Portfolio](../../README.md)*
