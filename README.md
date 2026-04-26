# Second_Project_Devlab

# 🛒 Superstore Sales — Data Analysis & Business Insights

> **Devlab Data Analyst Internship Project**  
> Exploratory data analysis on the Global Superstore dataset to uncover sales trends, customer behaviour, and actionable business insights.

---

## 📌 Project Overview

This project performs a full end-to-end exploratory data analysis (EDA) on the Global Superstore sales dataset. The goal is to understand revenue drivers, compare customer segments, and identify regional and seasonal patterns — all translated into concrete business recommendations.

**Dataset:** [Superstore Sales — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)  
**Records:** 9,800 rows × 18 columns  
**Period:** 2014 – 2017

---

## 📁 Project Structure

```
superstore-analysis/
│
├── train.csv                      # Raw dataset
├── superstore_analysis.ipynb      # Main analysis notebook
└── README.md                      # Project documentation
```

---

## 🔍 Analysis Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | **Data Loading** | Import libraries, load dataset |
| 2 | **Data Cleaning** | Date parsing, delivery days, null handling |
| 3 | **Time Trends** | Monthly/yearly/quarterly/seasonal patterns |
| 4 | **Category Analysis** | Sales by category & sub-category |
| 5 | **Region & Segment** | Heatmaps, ship mode distribution |
| 6 | **Customer Analysis** | Top 10 customers, delivery boxplot, sales histogram |
| 7 | **Deep Dive** | Sub-category × region matrix, YoY growth |
| 8 | **Business Insights** | Summary KPIs + 6 strategic recommendations |

---

## 📊 Key Findings

| Metric | Value |
|--------|-------|
| Total Sales | ~$2.26M |
| Unique Orders | 4,922 |
| Unique Customers | 793 |
| Avg. Order Value | ~$458 |
| Avg. Delivery Time | ~4 days |

### 🔑 Business Insights

1. **Technology** category generates the highest average sale ($456) with the fewest orders → premium upselling opportunity.
2. **West & East** regions lead in revenue; **Central** region is underperforming.
3. **Consumer** segment has the most orders, but **Corporate** yields higher average order value → B2B channel investment recommended.
4. **Standard Class** shipping accounts for >50% of all orders → fast shipping incentives could drive segment migration.
5. **Q4 (Oct–Dec)** is the peak sales period → campaigns should start earlier in the year.
6. **Top 10 customers** represent a disproportionate share of revenue → a VIP loyalty programme is strongly advised.

---

## 🛠️ Tech Stack

- **Python 3.x**
- `pandas` — data manipulation
- `numpy` — numerical operations
- `matplotlib` — custom visualisations
- `seaborn` — statistical plots

---



## 🎯 Skills Demonstrated

- Data cleaning & preprocessing
- Exploratory data analysis (EDA)
- Time-series and seasonality analysis
- Multi-dimensional segmentation (region, segment, category)
- Business insight extraction from raw data
- Data visualisation with matplotlib & seaborn

---

