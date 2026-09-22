# Key Findings — Superstore Sales Analysis

These findings summarize the analysis in `Superstore_Analysis.ipynb`. Every claim is supported by a specific value computed in the notebook. Charts referenced here are saved as PNGs in `images/`.

---

## Finding 1: Technology is the profit engine

Technology generated **$836,154** in total sales (36.4% of $2.3M total) and **$145,455** in profit (50.8% of total profit), with a **17.4% profit margin**. It is the single most profitable product category.

**Supporting chart:** `images/question1_revenue_by_category.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 2: Furniture is a revenue trap

Furniture has the second-highest sales at **$742,000** (32.3% of total), but only generated **$18,451** in profit — a margin of just **2.5%**. It earns nearly as much revenue as Technology but contributes almost nothing to the bottom line.

**Supporting chart:** `images/question1_profit_margin.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 3: Sales grew 51.4% from 2014 to 2017 with Q4 seasonality

Sales grew from **$484,247** in 2014 to **$733,215** in 2017, a **51.4% increase**. Every year shows a consistent Q4 peak — Q4 2017 reached **$280,054**, nearly double Q1 2014 ($74,448). Q4 orders average **5.3% more** per order than other quarters.

**Supporting chart:** `images/question2_sales_over_time.png`
**Source:** Question 2 in `Superstore_Analysis.ipynb`.

---

## Finding 4: High discounts destroy profit

Orders with **0% discount** averaged **$66.90** in profit. Orders with **>20% discount** averaged **-$97.18** — they lose money. The correlation between discount and profit is **r = -0.220**. The 40%+ discount bracket (933 orders) averaged **-$106.71** in profit per order.

**Supporting chart:** `images/question3_discount_vs_profit.png`
**Source:** Question 3 in `Superstore_Analysis.ipynb`.

---

## Finding 5: West leads in both sales and profit

West is the strongest region across both metrics: **$725,458** in sales (31.6% of total) and **$108,418** in profit (37.9% of total). Central lags in both: $501,240 sales (21.8%) and only $39,706 profit (13.9%).

**Supporting chart:** `images/question1_region_comparison.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 6: 11.7% of orders are sales outliers

**1,167 orders** (11.7% of all orders) have sales above the upper fence of **$499**, totaling **$1,477,483** — nearly two-thirds of total revenue comes from just 12% of orders. Outliers are concentrated in Furniture (467), Technology (400), and Office Supplies (300).

**Supporting chart:** `images/additional_sales_boxplot.png`
**Source:** Additional Analysis in `Superstore_Analysis.ipynb`.

---

## Summary Table

| # | Finding | Key Number | Chart |
|---|---------|-----------|-------|
| 1 | Technology is the profit engine | $836K sales, 50.8% of profit | Q1 |
| 2 | Furniture is a revenue trap | 2.5% margin, $18K profit | Q1 |
| 3 | Sales grew 51.4% with Q4 peaks | $484K→$733K, Q4 $280K | Q2 |
| 4 | High discounts destroy profit | -$97 avg vs +$67, r=-0.22 | Q3 |
| 5 | West leads sales and profit | $725K sales, $108K profit | Q1 |
| 6 | 11.7% of orders are outliers | 1,167 orders, $1.48M sales | Additional |

---

## Limitation

This analysis covers only 4 years (2014-2017), so trend conclusions are short-term. Cost data (shipping, manufacturing, overhead) is not included, so margin analysis is limited to gross profit. Geography is at the state level, not store level, preventing granular location-based strategy.

---

> Generated from `Superstore_Analysis.ipynb`. All numbers verified against notebook output.
