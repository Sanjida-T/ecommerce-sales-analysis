E-Commerce Sales Analytics Dashboard (SQL + Power BI)
 Project Overview
This project analyzes e-commerce sales data to uncover insights about revenue performance, customer behavior, and product trends.
The analysis was performed using MySQL for data querying and transformation and Power BI for interactive data visualization.
The goal of this project is to demonstrate how raw transaction data can be transformed into actionable business insights that help companies make better decisions.

 Business Problem
E-commerce companies generate large amounts of transactional data, but without proper analysis it is difficult to understand:
* Which products generate the most revenue
* How customer purchasing behavior changes over time
* Which regions drive the most sales
* Which customers are the most valuable
This project builds a data analysis pipeline using SQL and Power BI to answer these questions and visualize key business metrics.

 Tools & Technologies
* SQL (MySQL Workbench 8) – Data querying and analysis
* Power BI Desktop – Dashboard creation and data visualization
* GitHub – Project documentation and version control

 Dataset Description
The dataset simulates a real-world e-commerce database consisting of multiple related tables.
Database Schema
customers
orders
order_items
products
payments
Table Relationships
customers ? orders
orders ? order_items
products ? order_items
orders ? payments
This structure represents a typical retail transaction database used in analytics systems.

Key Metrics (KPIs)
The dashboard focuses on important business metrics used in retail analytics.
* Total Revenue – Total sales generated
* Total Orders – Number of completed transactions
* Total Customers – Number of unique customers
* Average Order Value (AOV) – Average spending per order
* Total Units Sold – Quantity of products sold
These metrics help businesses evaluate overall performance and growth.

Dashboard Features
The Power BI dashboard includes multiple analytical views:
 Sales Overview
Displays overall company performance through KPI cards and revenue trends.
Visualizations include:
* Revenue trend over time
* Orders by status
* Sales by country

Product Performance
Analyses which products and categories drive the most revenue.
Visualizations include:
* Top products by revenue
* Sales by product category
* Units sold by product

 Customer Insights
Examines customer purchasing behavior and market distribution.
Visualizations include:
* Top customers by revenue
* Customers by country
* Orders per customer
 SQL Analysis Examples
Total Revenue by Product Category
SELECT 
    p.category,
    SUM(oi.quantity * oi.unit_price) AS revenue
FROM order_items oi
JOIN products p 
ON oi.product_id = p.product_id
GROUP BY p.category
ORDER BY revenue DESC;

Top Customers by Spending
SELECT 
    c.full_name,
    SUM(oi.quantity * oi.unit_price) AS total_spent
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
JOIN order_items oi ON o.order_id = oi.order_id
GROUP BY c.full_name
ORDER BY total_spent DESC
LIMIT 5;

Monthly Revenue Trend
SELECT 
    DATE_FORMAT(o.order_date,'%Y-%m') AS month,
    SUM(oi.quantity * oi.unit_price) AS revenue
FROM orders o
JOIN order_items oi 
ON o.order_id = oi.order_id
GROUP BY month
ORDER BY month;

 Key Insights
Some insights discovered during the analysis:
* Certain product categories generate significantly higher revenue than others.
* A small group of customers contributes a large percentage of total sales.
* Sales show clear patterns over time, which can help businesses forecast demand.
* Geographic regions contribute differently to overall revenue.

 
Skills Demonstrated
SQL
* Joins
* Aggregations
* Group By
* Revenue calculations
* Data analysis queries
Power BI
* Data modeling
* Dashboard creation
* KPI metrics
* DAX measures
* Interactive filters
Data Analysis
* Sales trend analysis
* Customer behavior analysis
* Product performance analysis
 Conclusion
This project demonstrates how SQL and Power BI can be used together to transform raw transactional data into meaningful business insights.
The interactive dashboard helps stakeholders monitor sales performance, customer trends, and product success, enabling more informed decision-making.

