# SQL Data Analytics Project

An end-to-end SQL Server (T-SQL) analysis of a retail sales data warehouse. It starts with exploring the data, moves through advanced analytics, and ends with two reusable report views for customers and products.

## About This Project

This project follows the structure and dataset from the course **SQL Mastery for Data Analytics and Business Intelligence** by Baraa Khatib Salkini. I worked through the course and wrote several of the queries in my own way, using different approaches from the course versions. The full workflow, from exploration to final reports, is documented here as a learning and portfolio project.

## Project Roadmap

The project follows a two-phase roadmap:

**Phase 1: Exploratory Data Analysis (EDA)**
1. Database Exploration
2. Dimensions Exploration
3. Date Exploration
4. Measures Exploration
5. Magnitude Analysis
6. Ranking Analysis (Top N / Bottom N)

**Phase 2: Advanced Analytics**
7. Change-Over-Time (Trends)
8. Cumulative Analysis
9. Performance Analysis
10. Data Segmentation
11. Part-to-Whole (Proportional) Analysis
12. Reporting (final report views)

## Dataset

Three flat files in `datasets/flat-files/`, modelled as a star schema in the `gold` schema:

| Table | Type | Description |
|---|---|---|
| `gold.fact_sales` | Fact | Order-level sales: order number, dates, sales amount, quantity, price |
| `gold.dim_customers` | Dimension | Customer details: name, country, gender, birthdate |
| `gold.dim_products` | Dimension | Product details: name, category, subcategory, product line, cost |

`dim_products` has 295 products across 4 categories: Components, Bikes, Clothing and Accessories.

## Repository Structure

```
sql-data-analytics-project/
├── datasets/
│   └── flat-files/
│       ├── dim_customers.csv
│       ├── dim_products.csv
│       └── fact_sales.csv
├── scripts/
│   ├── 01_database_exploration.sql
│   ├── 02_dimensions_exploration.sql
│   ├── 03_date_range_exploration.sql
│   ├── 04_measures_exploration.sql
│   ├── 05_magnitude_analysis.sql
│   ├── 06_ranking_analysis.sql
│   ├── 07_change_over_time_analysis.sql
│   ├── 08_cumulative_analysis.sql
│   ├── 09_performance_analysis.sql
│   ├── 10_data_segmentation.sql
│   ├── 11_part_to_whole_analysis.sql
│   ├── 12_report_customers.sql
│   └── 13_report_products.sql
├── docs/
│   └── project_roadmap.png
└── README.md
```

## What Each Script Does

| # | Script | Purpose |
|---|---|---|
| 01 | Database exploration | Lists tables and columns using `INFORMATION_SCHEMA` |
| 02 | Dimensions exploration | Unique countries, categories, subcategories and products |
| 03 | Date range exploration | First and last order dates; customer age range |
| 04 | Measures exploration | Total sales, quantity, average price, orders, products, customers |
| 05 | Magnitude analysis | Customers by country and gender; revenue by category and customer |
| 06 | Ranking analysis | Top and bottom products and customers |
| 07 | Change over time | Monthly sales, customers and quantity |
| 08 | Cumulative analysis | Yearly sales with running total |
| 09 | Performance analysis | Product sales vs. average and vs. previous year (`LAG`) |
| 10 | Data segmentation | Product cost ranges; customer segments (VIP, Regular, New) |
| 11 | Part-to-whole | Each category's share of total sales |
| 12 | Customer report | View combining customer metrics, segments and KPIs |
| 13 | Product report | View combining product metrics, segments and KPIs |

## SQL Concepts Used

- Joins (`LEFT JOIN`, `JOIN`)
- Aggregations and grouping (`SUM`, `AVG`, `COUNT DISTINCT`)
- Common Table Expressions (CTEs)
- Window functions (`SUM() OVER`, `AVG() OVER`, `LAG`)
- `CASE` expressions for segmentation
- Date functions (`DATEDIFF`, `YEAR`, `MONTH`)
- Views for reusable reporting

## Final Reports

**`gold.report_customers`** brings together, for each customer: age and age group, segment (VIP / Regular / New), total orders, sales, quantity and products, recency, average order value, and average monthly spend.

**`gold.report_products`** brings together, for each product: category, subcategory and cost, performance segment (High-Performer / Mid-Range / Low-Performer), total orders, sales, quantity and customers, recency, average selling price, average order revenue, and average monthly revenue.

## How to Run

1. Install SQL Server and SQL Server Management Studio (SSMS).
2. Create a database and a `gold` schema.
3. Import the three CSV files from `datasets/flat-files/` as `gold.dim_customers`, `gold.dim_products` and `gold.fact_sales`.
4. Run the scripts in `scripts/` in numeric order.

## Credits

Dataset and project structure: **SQL Mastery for Data Analytics and Business Intelligence** by Baraa Khatib Salkini.
