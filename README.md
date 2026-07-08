
Your content is already well structured. Below is a polished, professional version that you can use directly in your GitHub README, Power BI project description, portfolio, or resume.

---

# 🛒 Olist Store Sales & Customer Analytics Dashboard

## OBJECTIVE

As a Data Analyst for Olist Store, the objective of this project is to analyze e-commerce performance, customer purchasing behavior, payment trends, delivery efficiency, and customer satisfaction. The insights generated from this dashboard support business decision-making by identifying operational improvements and customer trends.

### Business Requirements

* Compare the total number of orders placed on weekdays versus weekends.
* Compare the average payment value for weekday and weekend orders.
* Determine the total number of orders with a review score of **5** that were paid using **Credit Card**.
* Calculate the average delivery time (customer perspective) for the **Pet Shop** product category.
* Analyze the average product price and payment value of customers located in **São Paulo**.
* Study the relationship between shipping days and customer review scores.

---

# DOMAIN KNOWLEDGE

Olist is a Brazilian e-commerce marketplace that connects customers with thousands of independent sellers.

The platform generates revenue through several business models:

### Sales Commission

Olist earns a commission on every successful sale completed through the marketplace.

### Transaction Fees

Payment processing fees are charged on every completed order.

### Advertising

Sellers pay for sponsored advertisements and premium product visibility.

### Affiliate Marketing

Partners and influencers receive commissions for referring customers.

### Shipping & Logistics

Revenue is generated through shipping and logistics services.

### Subscription Services

Premium memberships and seller subscriptions provide recurring revenue.

### Returns & Refunds

Processing fees may be collected for returns, cancellations, or restocking.

---

# DATA KNOWLEDGE

## Customers Dataset (99,441 Rows)

| Column                   | Description                           |
| ------------------------ | ------------------------------------- |
| customer_id              | Unique customer ID                    |
| customer_unique_id       | Unique anonymized customer identifier |
| customer_zip_code_prefix | Customer ZIP code                     |
| customer_city            | Customer city                         |
| customer_state           | Customer state                        |

---

## Geolocation Dataset (738,332 Rows)

| Column                      | Description |
| --------------------------- | ----------- |
| geolocation_zip_code_prefix | ZIP code    |
| geolocation_lat             | Latitude    |
| geolocation_lng             | Longitude   |
| geolocation_city            | City        |
| geolocation_state           | State       |

---

## Order Items Dataset (112,650 Rows)

| Column              | Description       |
| ------------------- | ----------------- |
| order_id            | Order ID          |
| order_item_id       | Item number       |
| product_id          | Product ID        |
| seller_id           | Seller ID         |
| shipping_limit_date | Shipping deadline |
| price               | Product price     |
| freight_value       | Shipping cost     |

---

## Order Payments Dataset (103,886 Rows)

| Column               | Description            |
| -------------------- | ---------------------- |
| order_id             | Order ID               |
| payment_sequential   | Payment sequence       |
| payment_type         | Payment method         |
| payment_installments | Number of installments |
| payment_value        | Payment amount         |

---

## Order Reviews Dataset (99,224 Rows)

| Column                  | Description           |
| ----------------------- | --------------------- |
| review_id               | Review ID             |
| order_id                | Order ID              |
| review_score            | Customer rating (1–5) |
| review_comment_title    | Review title          |
| review_comment_message  | Review message        |
| review_creation_date    | Review creation date  |
| review_answer_timestamp | Seller response time  |

---

## Orders Dataset (99,441 Rows)

| Column                        | Description             |
| ----------------------------- | ----------------------- |
| order_id                      | Order ID                |
| customer_id                   | Customer ID             |
| order_status                  | Order status            |
| order_purchase_timestamp      | Purchase timestamp      |
| order_approved_at             | Approval timestamp      |
| order_delivered_carrier_date  | Carrier delivery date   |
| order_delivered_customer_date | Customer delivery date  |
| order_estimated_delivery_date | Estimated delivery date |

---

## Product Category Translation Dataset (71 Rows)

| Column                        | Description       |
| ----------------------------- | ----------------- |
| product_category_name         | Original category |
| product_category_name_english | English category  |

---

## Products Dataset (32,951 Rows)

| Column                     | Description         |
| -------------------------- | ------------------- |
| product_id                 | Product ID          |
| product_category_name      | Category            |
| product_name_length        | Product name length |
| product_description_length | Description length  |
| product_photos_qty         | Number of photos    |
| product_weight_g           | Weight (grams)      |
| product_length_cm          | Length              |
| product_height_cm          | Height              |
| product_width_cm           | Width               |

---

## Sellers Dataset (3,095 Rows)

| Column                 | Description  |
| ---------------------- | ------------ |
| seller_id              | Seller ID    |
| seller_zip_code_prefix | ZIP code     |
| seller_city            | Seller city  |
| seller_state           | Seller state |

---

# DATA CLEANING

## Customers Dataset

* Removed duplicate records.
* Checked and corrected data types.
* Verified missing values.
* Standardized customer city names using Proper Case.

---

## Geolocation Dataset

* Removed duplicate rows.
* Corrected data types.
* Checked missing values.
* Standardized all "São Paulo" city variations.

---

## Order Items Dataset

* Removed duplicates.
* Corrected data types.
* Checked missing values.

---

## Order Payments Dataset

* Removed duplicates.
* Corrected data types.
* Verified null values.
* Replaced underscores (_) with spaces in payment types.
* Converted payment types into Proper Case.

---

## Order Reviews Dataset

* Removed duplicates.
* Corrected data types.
* Replaced missing Review Titles with **"No Title"**.
* Replaced missing Review Messages with **"No Message"**.

---

## Orders Dataset

* Removed duplicates.
* Corrected data types.
* Converted Order Status into Proper Case.
* Kept null delivery dates for future analysis.

---

## Product Category Translation

* Promoted first row as headers.
* Removed duplicates.
* Corrected data types.
* Replaced underscores with spaces.
* Converted category names into Proper Case.

---

## Products Dataset

* Removed duplicates.
* Corrected data types.
* Fixed incorrect column headers.
* Replaced missing Product Name Length with **0**.
* Replaced missing Description Length with **0**.
* Replaced missing Product Category with **Unknown**.
* Standardized Product Category formatting.

---

## Sellers Dataset

* Removed duplicates.
* Corrected data types.
* Checked missing values.
* Corrected incorrect city value **04482258** to **Rio De Janeiro**.
* Standardized city names.
* Converted Seller City into Proper Case.
* Standardized all São Paulo entries.

---

# DATA MODEL (RELATIONSHIPS)

### Step 1

Merged:

* **Products Dataset**
* **Product Category Translation**

using:

```
product_category_name
```

---

### Step 2

Removed duplicate ZIP codes from the Geolocation table before establishing relationships.

Relationship created using:

```
geolocation_zip_code_prefix
```

---

### Step 3

Created a **Date Table** and connected it with:

```
Orders[order_approved_at]
```

to support time intelligence calculations.

---

# KEY PERFORMANCE INDICATORS (KPIs)

* Total Orders
* Total Sales
* Average Payment Value
* Average Product Price
* Average Delivery Days
* Review Score Analysis
* Weekday vs Weekend Orders
* Credit Card Orders with 5-Star Reviews
* São Paulo Customer Insights
* Shipping Days vs Review Score Analysis

---

# TOOLS USED

* Microsoft Excel
* Power BI
* Power Query
* DAX
* Data Modeling
* Data Cleaning
* Interactive Dashboard Design

---

# DASHBOARD FEATURES

* Interactive slicers
* Dynamic KPI cards
* Trend analysis
* City-wise performance
* Product category insights
* Customer review analysis
* Delivery performance analysis
* Payment method analysis
* Sales performance visualization

---

# BUSINESS INSIGHTS

* Weekday orders significantly outperform weekend orders.
* Credit Cards are the most preferred payment method among customers providing 5-star reviews.
* Pet Shop deliveries maintain a competitive average delivery time.
* Customers from São Paulo contribute a significant share of overall sales and payment value.
* Faster deliveries generally receive higher customer review scores, demonstrating the importance of efficient logistics.

---

# CONCLUSION

This Power BI dashboard transforms raw Olist e-commerce data into actionable business insights. By analyzing customer behavior, payment methods, delivery performance, product categories, and sales trends, stakeholders can make informed decisions to improve customer satisfaction, optimize operations, and drive business growth.

---

## ⭐ **Do Visit the Interactive Dashboard — Thank You! 😊**
