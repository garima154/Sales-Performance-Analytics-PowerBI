# 📊 Sales Performance Analytics Dashboard using Power BI

## 📌 Project Overview

The **Sales Performance Analytics Dashboard** is an interactive business intelligence project developed using **Microsoft Power BI** to analyze sales performance, profitability, customer behavior, product performance, and operational trends.

The project transforms raw Superstore sales data into an interactive multi-page dashboard that enables users to monitor key performance indicators (KPIs), identify profitable and underperforming areas, compare regional and category-level performance, and derive actionable business insights.

The dashboard is designed to demonstrate practical skills in:

- Data Cleaning and Transformation
- Exploratory Data Analysis
- Data Modeling
- DAX Measures
- Business Intelligence
- Data Visualization
- Interactive Dashboard Design
- Business Performance Analysis

---

## 🎯 Project Objectives

The main objectives of this project are to:

1. Analyze overall sales and profitability performance.
2. Track sales and profit trends over time.
3. Compare sales performance across different regions.
4. Analyze product and sub-category performance.
5. Identify the top-performing products and customers.
6. Identify products with low or negative profitability.
7. Analyze customer segments and their contribution to sales.
8. Examine the relationship between discounts and profitability.
9. Provide meaningful business insights through interactive visualizations.
10. Build a professional Power BI dashboard suitable for business decision-making.

---

## 🛠️ Tools and Technologies

| Tool / Technology | Purpose |
|-------------------|---------|
| **Microsoft Power BI** | Dashboard development and visualization |
| **Power Query** | Data cleaning and transformation |
| **DAX** | Calculated measures and business metrics |
| **CSV** | Source dataset |
| **GitHub** | Project version control and portfolio presentation |

---

# 📂 Dataset

The project uses the **Sample Superstore** dataset containing transactional sales information.

The dataset includes information related to:

- Orders
- Customers
- Products
- Categories
- Sub-Categories
- Sales
- Quantity
- Discount
- Profit
- Regions
- States
- Cities
- Customer Segments
- Shipping Modes
- Order Dates
- Shipping Dates

### Important Dataset Columns

| Column | Description |
|--------|-------------|
| Order ID | Unique identifier for an order |
| Order Date | Date when the order was placed |
| Ship Date | Date when the order was shipped |
| Customer ID | Unique customer identifier |
| Customer Name | Customer name |
| Segment | Customer segment |
| Country | Country of the customer |
| City | Customer city |
| State | Customer state |
| Region | Sales region |
| Product ID | Unique product identifier |
| Category | Product category |
| Sub-Category | Product sub-category |
| Product Name | Product name |
| Sales | Revenue generated from the sale |
| Quantity | Number of units sold |
| Discount | Discount applied to the product |
| Profit | Profit generated from the transaction |
| Ship Mode | Shipping method |

---

# 🔄 Data Preparation

Before building the dashboard, the raw dataset was cleaned and transformed using **Power Query**.

### Data Preparation Steps

### 1. Data Import

The Superstore CSV dataset was imported into Power BI using:

**Home → Get Data → Text/CSV**

---

### 2. Data Type Validation

The data types of important columns were checked and corrected.

Examples:

- Order Date → Date
- Ship Date → Date
- Sales → Decimal Number
- Profit → Decimal Number
- Discount → Decimal Number
- Quantity → Whole Number

Correct data types are important for accurate calculations and visualizations.

---

### 3. Date Transformation

The Order Date and Ship Date columns were converted into valid date formats.

This allowed the project to perform time-based analysis such as:

- Yearly sales
- Monthly sales
- Monthly profit
- Quarterly trends

---

### 4. Missing Value Handling

The dataset was checked for missing or invalid values.

Where appropriate, missing records were removed or handled during the Power Query transformation process.

---

### 5. Duplicate Validation

Duplicate records were carefully evaluated.

Order ID was **not treated as a unique row identifier**, because a single order can contain multiple products and therefore multiple rows.

This prevents valid transactional records from being incorrectly removed.

---

# 🗓️ Date Dimension / Calendar Table

A dedicated Calendar table was created using DAX to support time-based analysis.

```DAX
Calendar =
CALENDAR(
    MIN(SalesData[Order Date]),
    MAX(SalesData[Order Date])
)