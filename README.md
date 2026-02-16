# E-Commerce-Sales-Performance-Customer-Insights-Analysis

📌 Project Overview

This project analyzes a real-world e-commerce transactional dataset (100,000+ rows) using MySQL to extract business insights related to revenue performance, product intelligence, customer behavior, and operational efficiency.

The goal of this analysis is not just to write SQL queries, but to answer real business questions and simulate how a data analyst would support decision-making in a retail company.

🎯 Business Objectives

This analysis aims to answer:

How is the company performing financially?

Which products and categories generate the most revenue?

Which regions perform best?

How do discounts and taxes impact revenue?

Which sellers and payment methods drive performance?

🗂 Dataset Description

Each row represents a transaction (order line) and contains:

Order information (OrderID, OrderDate, OrderStatus)

Customer details (CustomerID, CustomerName)

Product information (ProductID, ProductName, Category, Brand)

Financial metrics (Quantity, UnitPrice, Discount, Tax, ShippingCost, TotalAmount)

Location data (City, State, Country)

Seller information (SellerID)

The dataset was cleaned and imported into MySQL after converting date formats to comply with SQL standards (YYYY-MM-DD).

🔎 SQL Analysis & Business Reasoning

Below are the key analytical steps and why they were performed.

1️⃣ Company Performance Overview
🔹 Total Revenue
SELECT SUM(TotalAmount) AS total_revenue
FROM orders;


🧠 Why?

To measure the company’s total sales performance.
This is the most fundamental KPI for any retail business.

🔹 Total Orders
SELECT COUNT(*) AS total_orders
FROM orders;


🧠 Why?

To understand transaction volume and operational scale.

🔹 Average Order Value (AOV)
SELECT AVG(TotalAmount) AS avg_order_value
FROM orders;


🧠 Why?

AOV helps determine customer spending behavior and pricing effectiveness.

2️⃣ Revenue by Geography
🔹 Revenue by State
SELECT State,
       SUM(TotalAmount) AS total_revenue
FROM orders
GROUP BY State
ORDER BY total_revenue DESC;


🧠 Why?

To identify high-performing regions and support expansion or marketing allocation decisions.

3️⃣ Product Intelligence
🔹 Top 5 Products by Revenue
SELECT ProductName,
       SUM(TotalAmount) AS product_revenue
FROM orders
GROUP BY ProductName
ORDER BY product_revenue DESC
LIMIT 5;


🧠 Why?

To determine which products generate the most financial impact.

🔹 Top 5 Products by Quantity Sold
SELECT ProductName,
       SUM(Quantity) AS total_units_sold
FROM orders
GROUP BY ProductName
ORDER BY total_units_sold DESC
LIMIT 5;


🧠 Why?

To differentiate between high-demand products and high-revenue products.

This helps identify whether revenue is driven by volume or pricing.

4️⃣ Category & Discount Analysis
🔹 Revenue by Category
SELECT Category,
       SUM(TotalAmount) AS total_revenue
FROM orders
GROUP BY Category
ORDER BY total_revenue DESC;


🧠 Why?

To identify which product segments dominate overall performance.

🔹 Average Discount by Category
SELECT Category,
       AVG(Discount) AS avg_discount
FROM orders
GROUP BY Category
ORDER BY avg_discount DESC;


🧠 Why?

To analyze discount strategy effectiveness and pricing aggressiveness.

🔹 Total Tax Collected by Category
SELECT Category,
       SUM(Tax) AS total_tax
FROM orders
GROUP BY Category
ORDER BY total_tax DESC;


🧠 Why?

To evaluate tax contribution and regulatory impact per segment.

5️⃣ Payment & Seller Performance
🔹 Revenue by Payment Method
SELECT PaymentMethod,
       SUM(TotalAmount) AS total_revenue
FROM orders
GROUP BY PaymentMethod
ORDER BY total_revenue DESC;


🧠 Why?

To understand customer payment preferences and optimize checkout strategies.

🔹 Top Sellers by Revenue
SELECT SellerID,
       SUM(TotalAmount) AS seller_revenue
FROM orders
GROUP BY SellerID
ORDER BY seller_revenue DESC
LIMIT 5;


🧠 Why?

To evaluate seller performance and commission structure.

📊 Key Analytical Skills Demonstrated

Data cleaning & format correction

Aggregation functions (SUM, AVG, COUNT)

GROUP BY segmentation

ORDER BY ranking

Business KPI identification

Translating business questions into SQL logic

🛠 Tools Used

MySQL

MySQL Workbench

Excel (data cleaning)

GitHub

(Power BI / Tableau – optional for visualization)
