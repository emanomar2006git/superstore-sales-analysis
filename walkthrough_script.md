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

"For my first question — categories and regions — I grouped by Category 
and Region and summed Sales and Profit.

The main finding is that Technology leads in both sales and profit — 
$836,154 in sales and $145,455 in profit, about a 17% margin. But 
Furniture tells a different story: it has the second-highest sales at 
$741,999, yet its profit is only $18,451 — a margin of just 2.5%. You 
can see this in the bar chart [point to chart] — Furniture's orange 
profit bar is tiny compared to its blue sales bar, while Technology's 
two bars are much more proportional."
---

### Body — Question 2 (30–40 seconds)

"My second question was sales and profit over time. I used a line chart 
of monthly sales and profit from 2014 to 2017.

The finding here is that sales grew 51%, from $484,247 in 2014 to 
$733,215 in 2017, while profit grew even faster — 89%, from $49,544 to 
$93,439. There's also a clear seasonal pattern: every year starts low in 
January and peaks around November or December, with the highest point 
in the whole dataset — about $118,000 — in November 2017. This was 
expected given the overall trend, but the strength of the seasonal spike 
every single year was more pronounced than I expected."
---

### Body — Question 3 (30–40 seconds)

"For my third question — discount vs profit — I used a scatter plot of 
discount versus profit and computed the correlation.

The result was that the overall correlation is weak, r = -0.22, but 
grouping orders by discount level shows something sharper: orders with 
20% discount or less average positive profit — around $27 to $67 — but 
orders above 20% discount average negative profit, down to about -$107. 
The business implication is that discounts above 20% should require 
justification, since on average they're actually losing money, not just 
reducing margin."
---

### Closing (15–20 seconds)

"To summarize the key takeaway: sales volume doesn't guarantee profit — 
Furniture and the Central region both generate strong revenue but weak 
profit, largely tied to heavy discounting, while discounts above 20% 
are unprofitable on average across the board.

One limitation to keep in mind is that we don't have cost or marketing 
spend data, so 'profit' here reflects revenue after discount, not true 
operating margin — we can't fully separate the effect of shipping costs 
or overhead.

Everything is in my GitHub repo at 
https://github.com/emanomar2006git/superstore-sales-analysis. Thank you."
---

## Self-Check Before Delivery

- [ ] Total time is between 1:45 and 2:15 (time yourself!)
- [ ] Each finding includes a specific number
- [ ] Each chart reference is supported by a chart that actually appears in the notebook
- [ ] At least one limitation is stated
- [ ] I can explain any chart in my own words without reading
- [ ] I have anticipated the mentor's likely questions (see below)

## Mentor Questions After the Walkthrough (practice these)

- "What was the most surprising thing you found?"
- "If you had another week, what would you investigate next?"
- "Which finding are you least confident in?"
- "Explain your main chart to me as if I'm a non-technical colleague."
- "What does this limitation mean for the conclusions?"
