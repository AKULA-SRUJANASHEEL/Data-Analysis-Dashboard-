# 🛒 Olist E-Commerce Sales Analytics Dashboard

## 📌 Project Overview

The **Olist E-Commerce Sales Analytics Dashboard** is an interactive Business Intelligence solution developed to analyze sales performance, customer purchasing behavior, payment trends, product performance, and delivery efficiency. The dashboard provides data-driven insights that help improve customer satisfaction, optimize business operations, and support strategic decision-making.

---

# 🎯 Project Objective

As a Data Analyst for **Olist Store**, the objective of this project is to analyze key aspects of e-commerce performance and customer behavior by transforming raw transactional data into meaningful business insights.

### Business Objectives

* Analyze **Weekday vs Weekend Sales Performance**
* Evaluate **Customer Payment Behavior**
* Monitor **Order Delivery Performance**
* Analyze **Customer Review Scores**
* Identify **City-wise Sales Performance**
* Measure the relationship between **Shipping Time and Customer Satisfaction**
* Support strategic business decisions using interactive dashboards

---

# 🏪 Domain Knowledge

## About Olist

Olist is one of Brazil's largest e-commerce marketplaces, connecting thousands of sellers with customers through a centralized online platform. The company earns revenue by facilitating online sales, payment processing, logistics, and value-added seller services.

---

## Revenue Sources

### Product Sales Commission

Olist earns commission on every successful product sold through its marketplace.

### Payment Processing Fees

A small transaction fee is charged for processing online payments.

### Advertising Revenue

Sellers can purchase sponsored listings and promotional advertisements to increase product visibility.

### Shipping & Logistics

Revenue is generated through delivery and logistics services provided to sellers.

### Subscription Services

Premium seller accounts provide additional tools and marketing features.

### Affiliate Marketing

Third-party affiliates earn commissions by driving customer traffic and sales.

---

## Business Operations

The e-commerce order lifecycle consists of:

### Customer Registration

Customers create accounts and browse products.

### Product Selection

Customers search, compare, and purchase products.

### Payment Processing

Payments are completed through multiple payment methods such as:

* Credit Card
* Debit Card
* Boleto
* Voucher

### Order Fulfillment

Sellers prepare products and hand them over to logistics partners.

### Shipping & Delivery

Orders are shipped and delivered to customers.

### Customer Review

Customers rate their shopping experience, delivery service, and product quality.

---

# 📊 Dashboard KPIs

## Sales Performance

* Total Orders
* Total Revenue
* Average Order Value
* Average Payment Value
* Monthly Sales Trend

---

## Customer Analysis

* Total Customers
* Customer Distribution by State
* Customer Distribution by City
* Repeat Customers
* Customer Purchase Behavior

---

## Payment Analysis

* Payment Method Distribution
* Average Payment Value
* Installment Analysis
* Credit Card Usage
* Weekend vs Weekday Payments

---

## Product Performance

* Top Selling Categories
* Product Price Analysis
* Freight Cost Analysis
* Product Category Distribution

---

## Delivery Performance

* Average Delivery Days
* Estimated vs Actual Delivery
* On-Time Delivery Rate
* Delayed Deliveries
* Pet Shop Delivery Analysis

---

## Customer Satisfaction

* Review Score Distribution
* 5-Star Reviews
* Shipping Days vs Review Score
* Customer Feedback Analysis

---

# 📂 Dataset Description

The project uses multiple relational datasets from the Olist Brazilian E-commerce Public Dataset.

| Dataset                      | Description                                   |
| ---------------------------- | --------------------------------------------- |
| Customers Dataset            | Customer demographic and location information |
| Geolocation Dataset          | Geographic coordinates based on ZIP codes     |
| Orders Dataset               | Order lifecycle and delivery details          |
| Order Items Dataset          | Product-level order details                   |
| Order Payments Dataset       | Payment information for each order            |
| Order Reviews Dataset        | Customer ratings and review comments          |
| Products Dataset             | Product specifications and categories         |
| Product Category Translation | Portuguese to English category mapping        |
| Sellers Dataset              | Seller information and locations              |

---

# 🧹 Data Cleaning

The datasets were cleaned and standardized to improve data quality and ensure accurate reporting.

### Customers Dataset

* Removed duplicate records
* Checked null values
* Corrected data types
* Standardized customer city names

### Geolocation Dataset

* Removed duplicate ZIP codes
* Corrected data types
* Standardized "São Paulo" naming

### Orders Dataset

* Removed duplicate records
* Corrected date formats
* Standardized Order Status
* Preserved missing delivery dates for future analysis

### Order Items Dataset

* Removed duplicates
* Checked null values
* Corrected data types

### Order Payments Dataset

* Cleaned Payment Type values
* Replaced underscores with spaces
* Applied proper capitalization

### Order Reviews Dataset

* Replaced missing Review Title with **"No Title"**
* Replaced missing Review Message with **"No Message"**
* Removed duplicate records

### Products Dataset

* Corrected column names
* Replaced missing Product Category with **"Unknown"**
* Filled missing numeric values with 0
* Standardized Product Category names

### Product Category Translation

* Used first row as column headers
* Removed duplicate records
* Standardized category names

### Sellers Dataset

* Corrected incorrect city values
* Standardized city names
* Removed duplicate records
* Corrected data types

---

# 🔗 Data Modeling (Relationships)

The following relationships were established to create an optimized data model:

### Step 1

Merged **Products Dataset** with **Product Category Translation** using:

* **product_category_name**

to obtain English product category names.

### Step 2

Removed duplicate records from the **Geolocation Dataset** based on:

* **geolocation_zip_code_prefix**

to establish a one-to-many relationship with Customers and Sellers datasets.

### Step 3

Created a **Date Table** using DAX and connected it with:

* **order_approved_at**

from the Orders Dataset for time intelligence analysis.

---

# 💡 Business Insights

The dashboard enables business users to:

* Compare weekday and weekend purchasing behavior.
* Analyze customer payment preferences.
* Monitor delivery performance across product categories.
* Evaluate customer satisfaction through review scores.
* Identify high-performing cities and states.
* Understand shipping impact on customer reviews.
* Improve operational efficiency through data-driven insights.

---

# 🛠 Tools & Technologies

* Microsoft Excel
* SQL (MySQL)
* Power BI
* Tableau

---

# 📈 Skills Demonstrated

* Data Cleaning & Transformation
* Data Modeling
* SQL Querying
* Data Visualization
* Dashboard Development
* KPI Design
* Customer Analytics
* Sales Analytics
* E-Commerce Analytics
* Trend Analysis
* Business Intelligence
* Interactive Reporting
