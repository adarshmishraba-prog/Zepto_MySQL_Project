# Zepto E-commerce SQL Data Analyst Portfolio Project
Complete Data Analyst Portfolio Project with end-to-end SQL Data Analysis of Zepto e-commerce inventory data using PostgreSQL.

Zepto E-Commerce SQL Data Analyst Portfolio Project

A complete, real-world data analytics portfolio project based on an e-commerce inventory dataset inspired by Zepto, one of India’s leading quick-commerce platforms.
This project simulates the actual workflow of a Data Analyst — from raw data exploration to SQL-based business insights.

📌 Project Overview

This project demonstrates how SQL is used in the retail & e-commerce domain to:

✔️ Build and manage an e-commerce inventory database

✔️ Perform exploratory data analysis (EDA)

✔️ Clean inconsistent data

✔️ Generate business insights related to pricing, inventory, discounts & product availability

It’s ideal for:

📊 Data Analyst Aspirants

🛒 E-commerce / Retail Analytics learners

💼 Anyone preparing for SQL interviews

🧪 Beginners practicing SQL with a realistic dataset

📁 Dataset Overview

The dataset contains product listings scraped from Zepto’s inventory.
It closely represents real-world catalog data, where the same product may appear multiple times with:

different sizes

packaging variations

discounts

stock availability

Columns Included
Column	Description
sku_id	Unique identifier for each product
name	Product name
category	Product category (Fruits, Snacks, Beverages, etc.)
mrp	Maximum Retail Price (in ₹)
discountPercent	Discount applied
discountedSellingPrice	Discounted price (in ₹)
availableQuantity	Units available
weightInGms	Weight in grams
outOfStock	Stock availability flag
quantity	Number of units per package
🔧 Project Workflow
1️⃣ Database & Table Creation
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);

2️⃣ Data Import

CSV imported using pgAdmin or via SQL:

\copy zepto(category,name,mrp,discountPercent,availableQuantity,
            discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');


(Encoding issues were solved by saving the file as CSV UTF-8.)

3️⃣ 🔍 Exploratory Data Analysis

Performed EDA to:

Count total records

View sample rows

Identify missing values

List distinct product categories

Compare in-stock vs out-of-stock items

Detect duplicate product entries (multiple SKUs for same product)

4️⃣ 🧹 Data Cleaning

Key steps:

Removed rows where mrp or discountedSellingPrice = 0

Converted prices from paise → rupees for readability

Validated weight and quantity fields

Ensured boolean consistency in outOfStock column

5️⃣ 📊 Business Insights & SQL Analysis

Extracted several insights useful to retail teams:

⭐ Key Findings

Top 10 best-value products based on highest discount

High-MRP but out-of-stock items

Estimated revenue by product category

High MRP (₹500+) products with minimal discount

Top 5 categories with highest average discounts

Price per gram to identify value-for-money products

Weight segmentation: Low, Medium, Bulk

Total inventory weight by category

🛠️ How to Use This Project

Clone the repository

git clone https://github.com/yourusername/zepto-sql-data-analysis.git
cd zepto-sql-data-analysis


Open the SQL file:

zepto_SQL_data_analysis.sql

Create a database in PostgreSQL

Run the SQL script to:

Create the table

Load the dataset

Perform cleaning

Execute business analysis queries

👤 About This Project

This project is created as part of a Data Analytics portfolio to demonstrate SQL skills in a real e-commerce environment.
It showcases practical tasks such as database creation, cleaning, and deriving business insights.
