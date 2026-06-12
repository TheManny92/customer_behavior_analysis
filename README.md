# Customer Shopping Behavior Analysis

An end-to-end data analytics project analyzing 3,900 customer transactions to uncover spending patterns, customer segments, product preferences, and subscription behavior.

---

## Overview

This project follows the full data analytics pipeline — from raw data to business insights. The dataset was cleaned and transformed in Python, analyzed using SQL in PostgreSQL, and visualized in an interactive Power BI dashboard. Findings were compiled into a professional report and presentation.

---

## Dataset

| Property | Details |
|---|---|
| Source | Customer shopping transactions |
| Rows | 3,900 |
| Columns | 18 |
| Key Features | Age, Gender, Location, Category, Purchase Amount, Season, Subscription Status, Shipping Type, Review Rating, Discount Applied |
| Missing Data | 37 missing values in Review Rating column |

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (pandas) | Data loading, cleaning, and transformation |
| PostgreSQL | SQL-based business analysis |
| Power BI | Interactive dashboard and visualization |
| Gamma | Presentation |
| Jupyter Notebook | Development environment |
| SQLAlchemy / psycopg2 | Python-to-PostgreSQL connection |

---

## Project Steps

### 1. Data Loading
- Imported the dataset into a pandas DataFrame using `pd.read_csv()`
- Used `df.info()`, `df.describe()`, and `df.shape` for initial exploration

### 2. Data Cleaning
- Identified 37 missing values in the `Review Rating` column
- Imputed missing values using the **median rating per product category**
- Renamed all columns to `snake_case` for consistency
- Dropped the `promo_code_used` column after confirming it was redundant with `discount_applied`

### 3. Data Transformation
- Created an `age_group` column by binning customer ages into segments (Young Adult, Adult, Middle-aged, Senior)
- Created a `purchase_frequency_days` column derived from purchase frequency data

### 4. Database Integration
- Connected Python to a PostgreSQL database using SQLAlchemy and psycopg2
- Loaded the cleaned DataFrame into a PostgreSQL table for SQL analysis

### 5. SQL Analysis
Ten structured business queries were run in PostgreSQL:

- Revenue by Gender
- High-Spending Discount Users
- Top 5 Products by Review Rating
- Shipping Type Comparison (Standard vs. Express)
- Subscribers vs. Non-Subscribers
- Discount-Dependent Products
- Customer Segmentation (New, Returning, Loyal)
- Top 3 Products per Category
- Repeat Buyers & Subscription Likelihood
- Revenue by Age Group

### 6. Power BI Dashboard
Built an interactive dashboard featuring:
- KPI cards (Total Customers, Avg. Purchase Amount, Avg. Review Rating)
- Revenue and Sales by Category
- Revenue and Sales by Age Group
- Subscription Status breakdown
- Filters for Gender, Category, and Shipping Type

### 7. Report & Presentation
- Compiled findings into a structured Word report
- Created a professional presentation using Gamma

---

## Dashboard

![Customer Behavior Dashboard]("C:\Users\DELL\OneDrive\Desktop\Screenshot 2026-06-12 200712.png")

**Key Metrics:**
- 3,900 customers
- $59.76 average purchase amount
- 3.75 average review rating
- 73% of customers are non-subscribers

---

## Key Findings & Recommendations

| Finding | Recommendation |
|---|---|
| 73% of customers are non-subscribers | Offer discounts or free trials to drive subscription sign-ups |
| Young Adults generate the most revenue | Prioritize this segment in campaigns and loyalty programs |
| Adults rank lowest in sales | Use targeted promotions to re-engage this segment |
| Clothing dominates revenue and sales | Prioritize stock and promotions in this category |
| Accessories rank 2nd in revenue | Bundle with Clothing to increase average order value |
| Average review rating is 3.75/5 | Gather post-purchase feedback to identify and fix pain points |

---

## How to Run

### Prerequisites
```
Python 3.x
PostgreSQL
Jupyter Notebook
Power BI Desktop
```

### Setup
```bash
# Install required Python libraries
pip install pandas sqlalchemy psycopg2-binary
```

### Steps
1. Clone or download this repository
2. Open `analysis.ipynb` in Jupyter Notebook
3. Run all cells to load, clean, and transform the data
4. Ensure PostgreSQL is running and update the connection credentials:
```python
username = "your_username"
password = "your_password"
host = "localhost"
port = "5432"
database = "your_database_name"
```
5. Run the SQL queries in PostgreSQL using pgAdmin or psql
6. Open the `.pbix` file in Power BI Desktop to explore the dashboard

---

## Project Structure

```
├── analysis.ipynb          # Python data cleaning and transformation
├── queries.sql             # SQL business analysis queries
├── dashboard.pbix          # Power BI dashboard file
├── report.docx             # Written analysis report
├── presentation.pptx       # Project presentation
├── dataset.csv             # Raw dataset
└── README.md               # Project documentation
```

---

## Author

Emmanuel Adjei-Mensah
Data Analytics Project — 2026
