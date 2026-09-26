# Key Findings — Superstore Sales Analysis

These findings summarize the analysis in `Superstore_Analysis.ipynb`. Every claim is supported by a specific value computed in the notebook. Charts referenced here are saved as PNGs in `images/`.

---

## Finding 1: Technology Leads in Both Sales and Profit

Technology generated $836,154 in total sales (36% of $2,297,201 total) and $145,455 in profit — the strongest category on both metrics, with a healthy profit margin of ~17%.

**Supporting chart:** `images/question1_revenue_by_category.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 2: Furniture Drives High Sales but Almost No Profit

Furniture ranks 2nd in sales ($741,999) but last in profit ($18,451) — a margin of only ~2.5%, compared to ~17% for Technology and Office Supplies. This is the clearest example of sales and profit diverging in the dataset.

**Supporting chart:** `images/question1_revenue_by_category.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 3: Sales and Profit Grew Steadily, with Profit Outpacing Sales

Sales rose 51% from $484,247 (2014) to $733,215 (2017), while profit rose 89% over the same period ($49,544 to $93,439) — showing improved efficiency, not just volume growth. Clear seasonality repeats every year, peaking around November/December.

**Supporting chart:** `images/question2_sales_over_time.png`
**Source:** Question 2 in `Superstore_Analysis.ipynb`.

---

## Finding 4: Discounts Above 20% Cause Outright Losses

Orders with ≤20% discount average positive profit ($26.50–$66.90), but orders above 20% discount average negative profit (-$77.86 to -$106.71). The overall correlation between discount and profit is -0.22.

**Supporting chart:** `images/question3_discount_vs_profit.png`
**Source:** Question 3 in `Superstore_Analysis.ipynb`.

---

## Finding 5: Central Region Shows the Same Divergence as Furniture

Central ranks 3rd in sales ($501,240), close to East, but has the lowest profit margin of all regions (~7.9%, vs ~15% for West and ~13.5% for East).

**Supporting chart:** `images/question1_revenue_by_category.png`
**Source:** Question 1 in `Superstore_Analysis.ipynb`.

---

## Finding 6: A Small Share of Large Orders Drives Most Revenue

11.7% of orders (1,167 of 9,994) are statistical outliers in Sales, contributing roughly two-thirds of total sales. Furniture has the most outlier orders (467) of any category — more than Technology (400) or Office Supplies (300) — linking directly to its weak profit margin (Finding 2).

**Supporting chart:** `images/additional_sales_boxplot.png`
**Source:** Additional Analysis (Section 7) in `Superstore_Analysis.ipynb`.

---

## Summary Table

| # | Finding | Key Number | Chart |
|---|---------|-----------|-------|
| 1 | Technology leads sales & profit | $836K sales / $145K profit | Q1 |
| 2 | Furniture: high sales, low profit | 2.5% margin vs ~17% others | Q1 |
| 3 | Profit grew faster than sales | +89% profit vs +51% sales | Q2 |
| 4 | Discounts >20% cause losses | -$77 to -$107 avg profit | Q3 |
| 5 | Central: weak margin region | ~7.9% margin | Q1 |
| 6 | Outliers drive most revenue | 11.7% of orders, ~64% of sales | Additional |