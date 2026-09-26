# FINAL DISCUSSION REPORT

## FT300 · FIELD TRAINING (1)

| Field | Information |
|-------|------------|
| **Student Name** | Eman Mahmoud Ahmed Ali Omar |
| **Student ID** | [University ID] |
| **Track / Specialization** | Data Analysis |
| **Submission Date** | September 2026 |
| **Supervisor / Doctor** | Ali Mohamed |
| **Training Organization** | Gulf Plastics Industries (GPI) |
| **Training Period** | 2026-09-16 to 2026-09-18 |
| **Project Title** | Superstore Sales Analysis — Identifying Revenue Drivers, Profit Traps, and Discount Impact from 9,994 Retail Orders |
| **Subtitle** | A data-driven analysis of four years of US retail sales to guide business strategy on product focus, seasonality, and discount policy |

---

## Table of Contents

1. [Abstract](#abstract)
2. [Introduction](#introduction)
3. [Requirements Analysis](#requirements-analysis)
4. [Technologies and Tools](#technologies-and-tools)
5. [System Design / Architecture](#system-design)
6. [Implementation](#implementation)
7. [Challenges and Solutions](#challenges-and-solutions)
8. [Project Results / Final Product](#project-results)
9. [Limitations](#limitations)
10. [Future Work](#future-work)
11. [Conclusion](#conclusion)
12. [References](#references)

---

## Abstract

This report presents a data analysis project that examined 9,994 retail orders spanning four years (2014–2017) from the publicly available Superstore Sales Dataset. The project addresses a common business problem: high sales revenue does not necessarily translate to high profit, and discount policies may inadvertently destroy margins. Using Python, pandas, matplotlib, and seaborn, the analysis answered three focused questions — which product categories and regions drive the most revenue and profit, how sales and profit have trended over time, and how discount levels relate to profitability. Key findings include that Technology is the clear profit engine (50.8% of total profit on 36.4% of sales), Furniture is a revenue trap (32.3% of sales but only 2.5% profit margin), sales grew 51.4% from 2014 to 2017 with consistent Q4 seasonality, and orders with discounts above 20% systematically lose money (average profit of -$97.18 per order versus +$66.90 for no-discount orders). The analysis was produced as a fully reproducible Jupyter notebook with six supporting charts, demonstrating practical skills in data cleaning, exploratory analysis, visualization, and stakeholder communication.

---

## 1. Introduction

### 1.1 Background

Retail businesses generate vast amounts of transactional data but often lack the analytical tools to convert that data into actionable strategy. The Superstore Sales Dataset, published on Kaggle, provides 9,994 orders across four years (2014–2017) covering products, regions, customer segments, sales, discounts, and profit. This dataset represents a real-world opportunity to demonstrate how systematic data analysis can reveal business insights that are not immediately obvious from raw numbers.

The importance of this project lies in its practical application: every finding has the potential to inform real business decisions about inventory allocation, marketing focus, and pricing strategy.

### 1.2 Problem Statement

The specific problem this project addresses is the divergence between revenue and profit in retail operations. The company generates substantial revenue across multiple product categories and regions, but without systematic analysis, it is unclear which products and regions actually contribute to profitability. Additionally, discount strategies — commonly used to drive volume — may be eroding margins without the business's awareness. The core question is: **where is the money actually being made, and what practices are destroying it?**

### 1.3 Proposed Solution

The proposed solution is a structured data analysis workflow that (1) cleans and validates the raw dataset, (2) answers three specific business questions using appropriate visualizations and statistical measures, (3) produces clear, number-backed findings suitable for stakeholder presentation, and (4) documents all results in a fully reproducible Jupyter notebook. The solution does not build a software system — it produces an analytical deliverable that business stakeholders can read and act upon.

### 1.4 Project Objectives

1. Clean and validate 9,994 retail orders from the Superstore dataset, handling date parsing, whitespace removal, and data type verification.
2. Identify which product categories and regions generate the most revenue and profit, with a bar chart visualization.
3. Analyze sales and profit trends over 2014–2017, quantifying growth rate and seasonal patterns with a line chart.
4. Determine the relationship between discount levels and profit, computing a correlation coefficient and analyzing profit by discount bracket, with a scatter plot.
5. Produce a reproducible Jupyter notebook that runs from start to finish without errors on a fresh clone.
6. Deliver a 2-minute verbal walkthrough presenting findings with specific numbers and an honest limitation.

### 1.5 Project Scope

**In scope:**
- Analysis of the Superstore Sales Dataset (9,994 rows, 21 columns, 2014–2017)
- Three focused business questions with supporting visualizations
- Data cleaning pipeline (date parsing, whitespace trimming, duplicate removal, type coercion)
- Reproducible Jupyter notebook with all code, charts, and interpretations
- Written findings report and a 2-minute verbal presentation

**Out of scope:**
- Building a web application or software system
- User authentication or access control
- Database design or management systems
- Predictive modeling or machine learning
- Cloud deployment or production infrastructure
- Analysis of data beyond 2017 (the dataset does not contain future data)
- Cost data analysis (shipping, manufacturing, overhead are not in the dataset)

---

## 2. Requirements Analysis

### 2.1 Functional Requirements

1. The system shall load raw sales data from a CSV file and parse dates correctly.
2. The system shall clean categorical data by removing leading and trailing whitespace from category, region, and segment fields.
3. The system shall verify and coerce numeric fields (Sales, Profit, Discount, Quantity) to proper data types.
4. The system shall compute total sales and profit grouped by product category and region.
5. The system shall compute monthly and yearly sales and profit trends.
6. The system shall calculate the correlation between discount percentage and profit.
7. The system shall generate at least four different chart types (bar, line, scatter, boxplot) with titles, axis labels, and legends.
8. The system shall export all charts as PNG images.
9. The system shall produce 5–8 numbered findings, each backed by a specific computed number.
10. The system shall write an honest limitations section identifying what the analysis cannot tell the reader.
11. The system shall run from start to finish without errors when executed in a fresh environment.

### 2.2 Non-Functional Requirements

- **Performance:** The analysis must complete in under 60 seconds on a standard laptop. The dataset is small enough that performance is not a concern, but the code must be efficient (vectorized pandas operations, no unnecessary loops).
- **Reliability:** The notebook must produce identical results when run multiple times. All cleaning steps are documented and deterministic.
- **Usability:** The notebook must be readable by a non-technical stakeholder. Markdown cells provide plain-English interpretations alongside every chart. The README must contain copy-paste runnable instructions.
- **Reproducibility:** The notebook must run top-to-bottom on a fresh clone without errors. All imports are at the top. No hardcoded absolute paths are used.
- **Maintainability:** All code cells have explanatory markdown above them. The notebook structure follows a logical flow: Setup → Load Data → Overview → Question 1 → Question 2 → Question 3 → Additional Analysis → Findings → Limitations → Conclusion.

### 2.3 Target Users

The primary users are **business stakeholders and mentors** who need to understand retail performance from a data perspective without being data scientists themselves. Specifically:
- **Mentor (Ali Mohamed, Gulf Plastics Industries):** Evaluates the analysis quality, methodology, and the intern's understanding of findings during the discussion walkthrough.
- **Business decision-makers:** Need actionable insights about which products to focus on, which regions to prioritize, and how to set discount policies.
- **Intern team members:** Can reuse the notebook as a template for their own analysis projects.

---

## 3. Technologies and Tools

| Technology/Tool | Version | Justification |
|----------------|---------|---------------|
| **Python 3** | 3.14.7 | Primary programming language. Chosen for its extensive data science ecosystem and industry adoption in analytics. |
| **pandas** | 3.0.6 | Data manipulation and analysis. Essential for grouping, aggregating, and transforming tabular data. Chosen because it is the standard library for data analysis in Python. |
| **numpy** | Latest | Numerical computing. Used alongside pandas for mathematical operations and statistical calculations. |
| **matplotlib** | Latest | Foundational plotting library. Chosen for precise control over chart appearance and PNG export. |
| **seaborn** | 0.13.2 | Statistical visualization built on matplotlib. Chosen for its attractive default styles and concise API for complex plots (boxplots, bar charts). |
| **sqlite3** | Built-in | Basic SQL on DataFrames. Used to demonstrate alternative query approaches on the dataset. Included to show versatility. |
| **Jupyter Notebook** | Latest | Interactive computing environment. Chosen because it allows code, visualizations, and plain-English interpretation to coexist in a single reproducible document. |
| **Git / GitHub** | Latest | Version control and publication. Chosen to track progress, enable collaboration, and provide a public portfolio piece. |

---

## 4. System Design / Architecture

### 4.1 System Architecture

This is a **data analysis project**, not a software system. The architecture is a linear analytical pipeline:

```
Raw Data (CSV)
     ↓
Data Cleaning Pipeline (pandas)
     ↓
Cleaned Data (superstore_clean.csv)
     ↓
Analysis Engine (Jupyter Notebook)
     ├── Question 1: Category & Region Analysis → Bar Charts
     ├── Question 2: Time Series Analysis → Line Charts
     ├── Question 3: Discount vs Profit Analysis → Scatter Plots
     └── Additional Analysis: Outlier Detection → Boxplots
     ↓
Findings & Interpretations (Markdown)
     ↓
Visual Outputs (PNG Charts)
     ↓
Deliverables (README, Walkthrough, Report)
```

The notebook serves as both the analytical engine and the documentation. Each section contains code, markdown explanations, and output visualizations in a single document.

### 4.2 System Components

1. **Data Loading Module:** Loads raw CSV with error handling. Falls back to applying minimal cleaning inline if cleaned data is not available.
2. **Data Cleaning Pipeline:** Six documented steps — date parsing, whitespace trimming, duplicate removal, type coercion, column retention, final validation. Outputs `superstore_clean.csv`.
3. **Analysis Engine:** Three question modules, each computing statistics and generating visualizations. A fourth module handles outlier detection.
4. **Visualization Layer:** Matplotlib and seaborn produce charts with consistent styling (whitegrid theme, 150 DPI, labeled axes, titles, legends).
5. **Findings Layer:** Extracts key numbers from analysis sections and compiles them into 5–8 plain-English findings.
6. **Documentation Layer:** README, walkthrough script, and limitations section that translate analysis into stakeholder-facing communication.

### 4.3 Database Design

**Not applicable to this project.** The analysis operates on flat CSV files (tabular data) rather than a relational database. The dataset is loaded directly into pandas DataFrames for analysis. If a database were required, it would be a simple single-table structure with columns for Order ID, Category, Region, Sales, Profit, Discount, and Date. SQLite3 was tested but found unnecessary for this scale of data.

### 4.4 UML Diagrams

**Not applicable in the traditional software engineering sense.** This is a data analysis project, not an object-oriented software system. The analytical pipeline described in Section 4.1 serves as the equivalent architecture diagram. The workflow follows a simple sequential pattern: Load → Clean → Analyze → Visualize → Report. No class diagrams, use case diagrams, or sequence diagrams are needed because there are no classes, actors, or message passing — only data transformations.

---

## 5. Implementation

### 5.1 Data Loading and Cleaning

**Feature → How it works → Technical explanation:**

The data loading module first attempts to load `data/superstore_clean.csv`. If that file is not found, it falls back to loading the raw CSV and applying minimal cleaning inline. Date columns are parsed using `pd.to_datetime()`, categorical columns are stripped of whitespace using `.str.strip()`, and numeric columns are coerced using `pd.to_numeric()`. Duplicate rows are identified and removed. The cleaned dataset is saved to `superstore_clean.csv` for reproducibility.

**Technical explanation:** This approach ensures the notebook is self-contained and reproducible. A reviewer who clones the repo and does not have the cleaned CSV can still run the notebook successfully. All cleaning steps are documented in `notebooks/02_cleaning.ipynb` and consolidated in the main notebook.

### 5.2 Analysis Implementation

Each analysis question follows a consistent pattern:
1. **Compute** — Group by relevant dimensions and aggregate (sum, mean, correlation)
2. **Visualize** — Generate an appropriate chart type with consistent styling
3. **Interpret** — Write 3+ sentences in plain English explaining what the numbers mean for the business

**Question 1** groups by Category and Region, computing sums of Sales and Profit, then produces bar charts showing both metrics side by side. Descriptive statistics (mean, median, std) provide additional context.

**Question 2** groups by Year and Month, producing a time series line chart showing the upward trend and Q4 seasonality. Year-over-year growth rate is calculated as a percentage.

**Question 3** computes the Pearson correlation between Discount and Profit, then bins discounts into four brackets (0%, 0-20%, 20-40%, 40%+) and compares average profit per bracket. A scatter plot shows the individual data points.

### 5.3 Main Features

**Feature 1: Category & Region Analysis**
- **How it works:** Groups 9,994 orders by Category and Region, sums Sales and Profit, produces dual bar charts
- **Result:** Technology leads profit at $145K (50.8%); Furniture is a revenue trap at 2.5% margin
- **Screenshot:** `images/question1_revenue_by_category.png`

**Feature 2: Time Series Analysis**
- **How it works:** Monthly aggregation of Sales and Profit, produces line chart with clear trend and seasonality
- **Result:** 51.4% sales growth 2014→2017, consistent Q4 peaks
- **Screenshot:** `images/question2_sales_over_time.png`

**Feature 3: Discount vs Profit Analysis**
- **How it works:** Computes correlation coefficient, bins discounts, compares average profit per bracket, produces scatter + bar charts
- **Result:** r = -0.220; >20% discount orders average -$97.18 profit
- **Screenshot:** `images/question3_discount_vs_profit.png`

**Feature 4: Outlier Detection**
- **How it works:** IQR method to identify sales outliers, produces boxplot for Sales and Profit distributions
- **Result:** 1,167 outliers (11.7%) totaling $1.48M in sales
- **Screenshot:** `images/additional_sales_boxplot.png`

---

## 6. Challenges and Solutions

| Challenge | Cause | Solution |
|-----------|-------|----------|
| **`superstore_clean.csv` not initially present** | The cleaned data file was missing from the repo; the notebook had to work without it | Implemented a fallback in the notebook that loads raw data and applies minimal cleaning inline. Then generated `superstore_clean.csv` separately and committed it |
| **pandas 3.0 API changes** | Newer pandas version had breaking changes with period indexing and string comparisons | Used `.astype(str)` for Year conversion and explicit integer period handling instead of relying on deprecated APIs |
| **Chart rendering issues with string index labels** | Matplotlib had compatibility issues with PeriodIndex on the x-axis for time series | Converted PeriodIndex to string labels manually using `ax.set_xticklabels()` |
| **Ambiguous discount-profit relationship** | The correlation was moderate (-0.22), not strong — could be misinterpreted as "discounts don't matter" | Added bin-level analysis showing that high-discount orders consistently lose money, making the practical significance clear even when statistical correlation is moderate |
| **Ensuring reproducibility** | Mentor needs to run notebook on fresh clone and get same results | Used relative paths (`data/...`, `images/...`) instead of absolute paths. Added fallback logic. Verified by running Kernel → Restart & Run All |

---

## 7. Project Results / Final Product

The final product is a fully reproducible Jupyter notebook (`Superstore_Analysis.ipynb`) that answers three business questions with six supporting charts and six detailed findings.

### Key Results:

| Result | Value |
|--------|-------|
| Total orders analyzed | 9,994 |
| Date range | 2014-01-03 to 2017-12-30 |
| Total Sales | $2,297,201 |
| Total Profit | $286,397 |
| Top category by profit | Technology ($145,455, 50.8%) |
| Revenue trap category | Furniture ($742,000 sales, 2.5% margin) |
| Sales growth 2014→2017 | 51.4% |
| Discount-profit correlation | r = -0.220 |
| Avg profit, >20% discount | -$97.18 |
| Outliers identified | 1,167 orders (11.7%) |
| Chart types used | 4 (bar, line, scatter, boxplot) |
| Total charts generated | 6 PNG files |

### Visual Evidence:
- `images/question1_revenue_by_category.png` — Bar charts for Sales and Profit by Category
- `images/question1_region_comparison.png` — Bar charts for Sales and Profit by Region
- `images/question1_profit_margin.png` — Profit margin comparison highlighting Furniture's 2.5% trap
- `images/question2_sales_over_time.png` — Line chart of monthly Sales and Profit
- `images/yearly_sales_profit.png` — Yearly bar chart with growth annotation
- `images/question3_discount_vs_profit.png` — Scatter plot + profit by discount bracket
- `images/additional_sales_boxplot.png` — Boxplot for outlier detection

### Deliverables:
- `Superstore_Analysis.ipynb` — Main reproducible notebook (33 cells, all TODOs filled)
- `findings.md` — 6 findings with specific numbers and chart references
- `walkthrough_script.md` — Complete 2-minute presentation script with self-check and mentor Q&A
- `Final_Project_Checklist.md` — 36-item checklist, all items verified
- `README.md` — Fully updated project page with embedded charts and findings
- `data/superstore_clean.csv` — Cleaned dataset (9,994 rows)

---

## 8. Limitations

1. **Limited time span (4 years):** The dataset covers only 2014–2017, making long-term trend conclusions unreliable. The 51.4% growth rate observed may not continue beyond 2017.

2. **No cost data:** The dataset includes Sales and Profit but not the underlying costs (shipping, manufacturing, overhead, marketing). This means we can only analyze gross profit — not true net margin or return on investment by product or region.

3. **Geography at state level:** The dataset provides state-level geographic data but not store-level or customer-level data. This prevents granular location-based strategy decisions (e.g., which specific stores to focus on).

4. **Moderate correlation, not causation:** The discount-profit correlation (r = -0.220) is moderate, meaning discount is one factor among many affecting profit. Other factors like customer segment, product category, and region also play roles. This analysis does not isolate the causal effect of discounts.

5. **No customer segmentation analysis:** While customer data exists (Customer ID, Segment, Name), the analysis does not dive into individual customer profitability or lifetime value. This was out of scope for the three core questions.

6. **Single dataset, single business:** The analysis is based on one dataset from one company (the Superstore dataset). Findings may not generalize to other retail contexts or different product categories.

---

## 9. Future Work

1. **Customer-segment profitability:** Analyze profit by Customer Segment (Consumer, Corporate, Home Office) to identify which customer types are most profitable.

2. **Product-level margin analysis:** Drill down to Sub-Category level to identify specific products that are driving the Furniture revenue trap (e.g., Bookcases vs Chairs vs Tables).

3. **Predictive modeling:** Use historical data to forecast future sales and profit trends, potentially incorporating seasonal decomposition and time series forecasting.

4. **Marketing spend analysis:** If marketing spend data were available, analyze the return on investment of discount campaigns and identify optimal discount levels.

5. **Regional deep-dive:** Analyze Sub-Category performance within each Region to provide more granular recommendations for regional strategy.

6. **Interactive dashboard:** Build a Plotly or Streamlit dashboard that allows stakeholders to filter by Region, Category, and Segment interactively.

7. **A/B testing framework:** Design a framework for testing different discount policies on subsets of orders to measure causal impact on profit.

---

## 10. Conclusion

This project analyzed 9,994 retail orders from the Superstore Sales Dataset spanning 2014–2017 to answer three focused business questions. The analysis revealed that **high revenue does not equal high profit** — this was the central takeaway. Technology emerged as the clear profit engine, generating $836K in sales and $145K in profit (50.8% of total profit), while Furniture was identified as a revenue trap — contributing $742K in sales but only $18K in profit, a margin of just 2.5%. The business is growing, with sales increasing 51.4% from 2014 to 2017 and a consistent Q4 seasonal peak. However, the most actionable finding was that **deep discounts destroy profit** — orders with discounts above 20% averaged -$97.18 in profit, compared to +$66.90 for no-discount orders.

The project demonstrated practical skills in data cleaning, exploratory analysis, statistical computation, data visualization, and stakeholder communication. All results were produced in a fully reproducible Jupyter notebook with six supporting charts, verified against a 36-item quality checklist. The limitations — including the 4-year time span and absence of cost data — were honestly stated and provide clear direction for future work. The deliverables are ready for mentor review and discussion.

---

## 11. References

[1] Vivek468, "Superstore Sales Dataset," Kaggle, 2024. [Online]. Available: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

[2] pandas Development Team, "pandas: Powerful Data Structures for Data Analysis, Statistics and Machine Learning," Python Package, 2024. [Online]. Available: https://pandas.pydata.org/

[3] J. D. Hunter, "Matplotlib: A 2D Graphics Environment," *Computing in Science & Engineering*, vol. 9, no. 3, pp. 90–95, 2007. [Online]. Available: https://matplotlib.org/

[4] M. Waskom, "seaborn: Statistical Data Visualization," *Journal of Open Source Software*, vol. 6, no. 60, p. 3021, 2021. [Online]. Available: https://seaborn.pydata.org/

[5] GitHub, "GitHub: Where the world builds software," GitHub, Inc., 2024. [Online]. Available: https://github.com/emanomar2006git/superstore-sales-analysis

[6] Gulf Plastics Industries (GPI), "Training Organization," Ali Mohamed (Supervisor), 2026.

[7] J. VanderPlas, *Python Data Science Handbook*. Sebastopol, CA: O'Reilly Media, 2016.
