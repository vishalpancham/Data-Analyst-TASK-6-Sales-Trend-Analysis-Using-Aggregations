# Task 6: Sales Trend Analysis Using Aggregations

## 📌 Objective
Perform SQL-based analysis on monthly sales performance using aggregate functions and GROUP BY. The goal is to analyze total revenue and order volume month-wise.

---

## 🧰 Tools Used
- DB Browser for SQLite
- SQL (SQLite syntax)

---

## 📂 Dataset (Simulated)
A dummy table named `online_sales` was created with the following fields:
- `order_id`
- `product_id`
- `amount` (sale amount)
- `order_date`

Sample data was inserted manually to test SQL queries.

---

## 🧪 SQL Queries Performed

### ✅ Monthly Revenue & Orders:
```sql
SELECT 
  STRFTIME('%Y-%m', order_date) AS month_year,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM 
  online_sales
GROUP BY 
  month_year
ORDER BY 
  month_year;
