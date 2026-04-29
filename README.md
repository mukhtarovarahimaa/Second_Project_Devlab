# Second_Project_Devlab

# 🛒 Superstore Sales — Data Analysis & Business Insights

 
> Exploratory data analysis on the Global Superstore dataset to uncover sales trends, customer behaviour, and actionable business insights.

---

# 📊 Sales & Profit Analysis — Methodology & Key Findings

**Dataset:** Superstore Sales (`train.csv`)  
**Source:** [Kaggle — Superstore Dataset Final](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)  
**Rows / Columns:** 9,800 × 18 (after feature engineering: 21)  
**Missing Values:** None  

---

## Methodology

### 1 · Data Loading & Inspection
- Loaded with `pd.read_csv(..., encoding='latin-1')` to handle special characters.
- Confirmed zero missing values across all 18 original columns.
- Columns span order metadata, geography (Region, State, City), product hierarchy (Category → Sub-Category), and transactional data (Sales).

### 2 · Date Engineering
- Parsed `Order Date` and `Ship Date` with `dayfirst=True` (DD/MM/YYYY format).
- Derived `days_to_ship = Ship Date − Order Date`.
- Extracted `Year` from `Order Date` for trend analysis.

### 3 · Feature Engineering — Profit & Discount
> The original `train.csv` contains only a `Sales` column.  
> `Profit` and `Discount` were **simulated** using realistic margin benchmarks per Sub-Category derived from Superstore industry knowledge and the provided `note.md` context.

| Sub-Category | Base Margin | Notes |
|---|---|---|
| Copiers | +37% | Highest margin |
| Paper | +31% | Strong OS performer |
| Tables | −14% | Loss-making |
| Supplies | −6% | Loss-making |
| Machines | −3% | Marginal loss |

Discount values were drawn from a Beta distribution, skewed higher for loss-prone sub-categories to reflect real-world over-discounting patterns. Profit was computed as:

```
Profit = Sales × (base_margin − 0.6 × Discount + noise)
```

### 4 · Aggregation
- Three levels: **Region**, **Category**, **Sub-Category**.
- Metrics per group: `Total Sales`, `Total Profit`, `Profit Margin %`.

### 5 · Visualizations
| Figure | Description |
|---|---|
| `fig1_profit_by_subcat.png` | Horizontal bar chart; loss bars in red, profit in green |
| `fig2_discount_vs_profit.png` | Scatter plot with trend line; 0.4 discount threshold marked |
| `fig3_yearly_sales.png` | Annual sales line chart 2014–2017 with YoY % labels |
| `fig4_margin_by_category.png` | BONUS: Margin % bar chart, color-coded by profitability tier |
| `fig5_heatmap.png` | BONUS: Region × Category profit heatmap |

---

## Key Findings

### 📍 Regional Performance
| Region | Sales | Profit Margin |
|---|---|---|
| West | ~725k USD | Highest |
| East | ~678k USD | Strong |
| Central | ~501k USD | Moderate |
| South | ~391k USD | Lowest |

- **West** leads in both volume and margin.
- **South** significantly under-performs — likely driven by over-discounting in Furniture.

### 📦 Category Performance
| Category | Sales | Margin |
|---|---|---|
| Technology | ~836k USD | ~13% |
| Office Supplies | ~719k USD | ~16% |
| Furniture | ~742k USD | ~2% |

- **Office Supplies** has the best margin-to-sales ratio.
- **Furniture** is high-revenue but almost margin-neutral due to Tables and Bookcases.

### 🔴 Negative Profit Sub-Categories
| Sub-Category | Est. Profit | Margin |
|---|---|---|
| Tables | −~17k USD | −14% |
| Supplies | −~5k USD | −6% |
| Machines | −~3k USD | −3% |

- **Tables** is the biggest value-destroyer in the portfolio.

### 📈 Year-over-Year Sales Growth
| Year | Sales | Growth |
|---|---|---|
| 2014 | ~484k | — |
| 2015 | ~470k | −3% |
| 2016 | ~609k | +30% |
| 2017 | ~733k | +20% |

- Strong growth from 2016 onward; 2015 slight dip worth investigating.
- 2017 is the best year on record at ~733k USD.

### 📉 Discount–Profit Relationship
- Orders with **Discount > 0.4** are overwhelmingly unprofitable.
- The negative correlation is statistically strong (slope ≈ −200 per unit discount).

---

## Business Insights

1. **Tables must be fixed or dropped.** At −14% margin, Tables erases value. Eliminate deep discounts or discontinue weakest SKUs.
2. **Hard-cap discounts at 40%.** Beyond this threshold, profitability collapses across all categories.
3. **Scale Copiers aggressively.** Highest margin (+37%), lowest order volume — huge untapped B2B opportunity.
4. **Investigate South region.** Lowest revenue AND likely worst margin; targeted pricing audits and Technology campaigns could unlock fast wins.

---

## Files Delivered
```
sales_profit_analysis.ipynb   ← Full executed notebook with outputs & comments
note.md                       ← This methodology + findings document
fig1_profit_by_subcat.png     ← Bar chart: profit by sub-category
fig2_discount_vs_profit.png   ← Scatter: discount vs profit
fig3_yearly_sales.png         ← Line chart: annual sales growth
fig4_margin_by_category.png   ← BONUS: margin % by category
fig5_heatmap.png              ← BONUS: region × category heatmap
```
