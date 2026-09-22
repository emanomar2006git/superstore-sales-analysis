# Walkthrough Script — Superstore Sales Analysis (2 minutes)

> Target: 1:45–2:15. Audience: mentor who has read the README and skimmed the notebook. Goal: prove you understand your findings, not just that you ran code. Practice out loud, timed, at least twice.

---

### Opening (15–20 seconds)

> "This is my analysis of the Superstore sales dataset from Kaggle — 9,994 orders from 2014 to 2017, with products, regions, and customer segments.
>
> The three questions I focused on were:
> 1. Which product categories and regions generate the most revenue and profit?
> 2. How have sales and profit changed over time?
> 3. How does discount level relate to profit?"

---

### Body — Question 1 (30–40 seconds)

> "For my first question — categories and regions — I grouped by Category and Region and summed Sales and Profit.
>
> The main finding is **Technology generated $836,154, 36.4% of total sales and 50.8% of total profit, but Furniture generated $742,000 in sales with only $18,451 in profit — a 2.5% margin**. You can see this in the bar chart [point to chart], which shows Technology and Office Supplies are profit leaders while Furniture is a revenue trap."

---

### Body — Question 2 (30–40 seconds)

> "My second question was sales and profit over time. I used a line chart of monthly sales and profit from 2014 to 2017.
>
> The finding here is **Sales grew 51.4% from $484,247 in 2014 to $733,215 in 2017, with a clear Q4 peak each year — Q4 2017 hit $280,054**. This was expected because holiday seasonality drives retail, but the profit growth rate of 88.7% exceeded the sales growth rate, suggesting improving efficiency."

---

### Body — Question 3 (30–40 seconds)

> "For my third question — discount vs profit — I used a scatter plot of discount % versus profit and computed the correlation.
>
> The result was **Orders with discounts above 20% averaged -$97.18 profit vs $66.90 for no-discount orders, correlation r = -0.220**. The business implication is that deep discounts destroy profit and should be capped at 20% or tied to product margin."

---

### Closing (15–20 seconds)

> "To summarize the key takeaway: **High revenue does not equal high profit — Furniture is a revenue trap at 2.5% margin, while Technology is the profit engine at 50.8% of total profit**.
>
> One limitation to keep in mind is **the dataset spans only 4 years, so trend conclusions are short-term, and cost data is not included, so we can't assess true net margin**.
>
> Everything is in my GitHub repo at https://github.com/emanomar2006git/superstore-sales-analysis. Thank you."

---

## Self-Check Before Delivery

- [x] Total time is between 1:45 and 2:15 (time yourself!)
- [x] Each finding includes a specific number
- [x] Each chart reference is supported by a chart that actually appears in the notebook
- [x] At least one limitation is stated
- [x] I can explain any chart in my own words without reading
- [x] I have anticipated the mentor's likely questions (see below)

## Mentor Questions After the Walkthrough (practice these)

- "What was the most surprising thing you found?" — Furniture's 2.5% margin despite high sales
- "If you had another week, what would you investigate next?" — Customer-segment profitability, product-level margins
- "Which finding are you least confident in?" — The discount-profit correlation is moderate (-0.22), not perfect
- "Explain your main chart to me as if I'm a non-technical colleague." — Bar charts showing categories side by side for sales vs profit
- "What does this limitation mean for the conclusions?" — The 51.4% growth rate may not continue beyond 2017
