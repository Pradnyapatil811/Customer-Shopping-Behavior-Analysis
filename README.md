# Customer-Shopping-Behavior-Analysis
End-to-end customer shopping behavior analysis using Python (pandas, SQLAlchemy), MySQL, and Power BI across 3,900 transactions to uncover revenue, segmentation, and discount trends.
# Customer Shopping Behavior Analysis

## Project Overview
An end-to-end data analytics project examining **3,900 customer shopping transactions** (`$233,081` total purchase amount; `$59.76` average order value) across product categories, customer segments, shipping modes, and subscription status. The project covers data cleaning and feature engineering in Python, relational querying in MySQL, and interactive visual reporting in Power BI.

## Tech Stack & Workflow
- **Data Cleaning & Feature Engineering (Python / Jupyter Notebook):**
  - Inspected 3,900 rows and 18 initial columns; imputed **37 missing `review_rating` values** using the median rating per `category`.
  - Standardized column headers to `snake_case` and renamed `purchase_amount_(usd)` to `purchase_amount`.
  - Engineered `age_group` into four quartile segments (`Young_Adult`, `Adult`, `Middle_aged`, `Senior`) via `pd.qcut` and mapped `frequency_of_purchases` into numeric `purchase_frequency_days` (`7` to `365` days).
  - Removed redundant `promo_code_used` column and exported the cleaned dataset (`19` columns) to MySQL using `SQLAlchemy` and `PyMySQL`.
- **SQL Analysis (MySQL):**
  - Queried the `customer_behavior.customer` table to analyze revenue by gender (`Male`: `$157,890` vs. `Female`: `$75,191`), age group revenue, subscription impact (`1,053` subscribers vs. `2,847` non-subscribers), shipping type averages (`Express`: `$60.48` vs. `Standard`: `$58.46`), and top-rated items (led by `Gloves` at `3.86` and `Sandals` at `3.84`).
  - Used CTEs and `ROW_NUMBER()` window functions for category-level top-3 product rankings and customer segmentation (`New`, `Returning`, `Loyal`).
- **Visualization & Reporting (Power BI):**
  - Built an interactive Power BI report (`Customer shopping behavior.pbix`) to track key revenue, customer segment, and product performance metrics.

## Repository Structure
- `customer_shopping_behavior.ipynb` — Data cleaning, quartile bucketing, frequency mapping, and MySQL load pipeline.
- `Customer shopping behavior.sql` — Analytical SQL queries covering revenue, discounts, ratings, shipping, subscriptions, and segmentation.
- `Customer shopping behavior.pbix` — Interactive Power BI dashboard.
- `customer_shopping_behavior.csv` — Source dataset (3,900 records).

## Key Takeaways
- **Revenue & Demographics:** Male customers account for `$157,890` of total purchase value compared to `$75,191` for female customers, while average order spend remains nearly consistent across subscribers (`$59.49`) and non-subscribers (`$59.87`).
- **Fulfillment & Ratings:** Express shipping averages `$60.48` per order versus `$58.46` for standard shipping; top review ratings appear among `Gloves` (`3.86`), `Sandals` (`3.84`), and `Boots` (`3.82`).
- **Actionable Business Value:** Segments customers by purchase history and discount sensitivity to support targeted retention campaigns and promotional planning.
