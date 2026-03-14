# 🛍️ Customer Behavior Analysis — End-to-End Data Analytics Project

> **Tools:** Python (Pandas, NumPy) · PostgreSQL · Power BI · Jupyter Notebook  
> **Dataset:** 3,900 customer transactions · 18 features · 4 product categories

---

## 📌 Project Overview

Performed a full-cycle data analytics project on a retail customer shopping dataset — from raw data ingestion and cleaning to SQL-based business analysis and an interactive Power BI dashboard.

The goal was to uncover **what drives customer spending**, identify **high-value segments**, and provide actionable insights to support business decision-making.

---

## 📂 Dataset Description

| Feature | Details |
|---|---|
| Records | 3,900 customer transactions |
| Columns | 18 (demographics, purchase behavior, shipping, ratings) |
| Categories | Clothing, Footwear, Accessories, Outerwear |
| Target Metrics | Purchase Amount (USD), Review Rating, Subscription Status |

**Key columns:** `customer_id`, `age`, `gender`, `item_purchased`, `category`, `purchase_amount`, `review_rating`, `subscription_status`, `shipping_type`, `discount_applied`, `previous_purchases`, `frequency_of_purchases`

---

## 🔄 Project Workflow

### 1. 🐍 Data Cleaning & Feature Engineering (Python)
- Loaded 3,900 records using **Pandas**
- Imputed 37 missing `review_rating` values using **category-wise median** — a smarter approach than global mean imputation
- Standardized all column names (lowercase + underscores)
- Engineered 2 new features:
  - **`age_group`** — segmented customers into Young Adult / Adult / Middle-Aged / Senior using `pd.qcut`
  - **`purchase_frequency_days`** — mapped text frequency labels (Weekly, Monthly, etc.) to numeric day values
- Identified and dropped the redundant `promo_code_used` column (100% correlated with `discount_applied`)
- Loaded the cleaned dataset into **PostgreSQL** via SQLAlchemy for SQL analysis

### 2. 🗄️ SQL Business Analysis (PostgreSQL)
Wrote 10 business-focused queries covering revenue analysis, customer segmentation, and product performance:

| # | Business Question | Technique Used |
|---|---|---|
| 1 | Revenue by gender | GROUP BY + SUM |
| 2 | High spenders who used discounts | Subquery + WHERE |
| 3 | Top 5 products by review rating | GROUP BY + ORDER BY |
| 4 | Standard vs Express shipping spend | Conditional aggregation |
| 5 | Subscriber vs non-subscriber revenue | Multi-metric aggregation |
| 6 | Products with highest discount rates | CASE + percentage calculation |
| 7 | Customer segmentation: New / Returning / Loyal | CTE + CASE |
| 8 | Top 3 products per category | CTE + Window Function (ROW_NUMBER) |
| 9 | Repeat buyers and subscription likelihood | Filtered aggregation |
| 10 | Revenue contribution by age group | GROUP BY + engineered feature |

### 3. 📊 Power BI Dashboard
Built an interactive dashboard with:
- KPIs: Total Revenue, Avg Purchase Amount, Avg Review Rating
- Revenue breakdown by gender, category, and age group
- Subscriber vs non-subscriber spend comparison
- Seasonal and shipping type performance filters
- Dynamic slicers for category, season, and subscription status

---

## 📈 Key Insights

- **68% of customers are male**, but female customers show higher average purchase amounts in the Accessories category
- **Subscribed customers** generate significantly higher total revenue compared to non-subscribers, despite similar average spend per transaction
- **Loyal customers** (10+ previous purchases) represent a small segment but drive disproportionate revenue
- **Blouse** is the single most purchased item (171 orders), with Clothing dominating at 1,737 out of 3,900 transactions
- Customers who used discounts and still spent above average — a key segment for targeted promotions
- **Middle-Aged customers** are the top revenue-contributing age group

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python + Pandas | Data loading, cleaning, feature engineering |
| NumPy | Numerical operations |
| PostgreSQL | Database storage and SQL analysis |
| SQLAlchemy | Python-to-PostgreSQL connection |
| Power BI | Interactive dashboard and visualization |
| Jupyter Notebook | Analysis and documentation |
| GitHub | Version control |

---


## 💡 Skills Demonstrated

`Data Cleaning` · `Exploratory Data Analysis` · `Feature Engineering` · `SQL (CTEs, Window Functions, Subqueries)` · `PostgreSQL` · `Power BI` · `Data Storytelling` · `Business Intelligence`
