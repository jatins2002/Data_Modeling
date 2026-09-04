# 📊 Power BI Data Modeling Project

## 📌 Project Overview

This project focuses on building a structured and scalable **analytical data model in Microsoft Power BI** using multiple business datasets.

The goal was to transform operational data related to **sales, customers, products, inventory, marketing campaigns, sales targets, geography, and order processing** into an analytics-ready model for reporting and business intelligence.

The project helped me understand practical concepts such as:

- Fact and Dimension Tables
- Star Schema
- Table Relationships
- Relationship Cardinality
- Data Transformation
- DAX Measures
- Row-Level Security (RLS)
- OLTP vs OLAP concepts

---

## 📸 Power BI Data Model

<p align="center">
  <img src="images/Screenshot 2026-09-05 023955.png" alt="Power BI Data Model" width="1000">
</p>

The model integrates multiple business processes into a unified analytical structure, allowing dimensions such as **Customer, Product, Date, Geography, Campaign, and Order attributes** to support analysis across different fact tables.

---

## 🏗️ Data Model Architecture

The model contains multiple **fact and dimension tables**.

### 📈 Fact Tables

#### `fact_sales`

The central sales fact table used for analyzing:

- Sales transactions
- Customers
- Products
- Quantity
- Discounts
- Order information

#### `fact_inventory`

Contains product-level inventory information and units available.

#### `fact_campaign_spend`

Stores marketing campaign performance data such as:

- Impressions
- Clicks
- Spend

#### `fact_promotion`

Connects marketing campaigns with promoted products.

#### `fact_sales_target`

Stores sales/revenue targets that can be compared against actual business performance.

#### `fact_order_process`

Contains information related to the order lifecycle, including:

- Order dates
- Invoice dates
- Payment dates
- Delivery dates
- Order processing duration

---

## 📐 Dimension Tables

### `dim_date`

Calendar dimension used for time-based analysis.

Example attributes:

- Date
- Year
- Month

### `dim_customer`

Contains descriptive customer information such as:

- Customer
- Region
- City
- Account Manager
- Contact Information
- Payment Terms

### `dim_products`

Contains product-related information such as:

- Product
- Brand
- Category
- Subcategory
- Supplier

### `dim_geo`

Provides geographical attributes including:

- City
- Region

### `dim_campaign`

Contains marketing campaign information.

### `dim_order_flag`

Contains descriptive order attributes such as:

- Order Channel
- Priority
- Status

---

## 🔗 Table Relationships

The analytical model primarily uses **one-to-many (1:*) relationships** between dimension and fact tables.

Example:

```text
dim_customer
     1
     │
     │
     *
 fact_sales
```

Similarly:

```text
dim_date ────────────→ fact_sales

dim_products ────────→ fact_sales

dim_geo ─────────────→ fact_sales

dim_campaign ────────→ fact_campaign_spend
```

This structure allows dimensions to filter transactional data while keeping the analytical model organized.

---

## 🧮 DAX Measures

A dedicated measures table was created to keep business calculations organized.

The model includes measures for metrics such as:

- Total Sales
- Total Orders
- Total Customers
- Total Active Customers
- Average Order Value
- Year-over-Year Performance

Using a dedicated measures table improves the organization and maintainability of the Power BI model.

---

## 🔐 Row-Level Security (RLS)

The project also contains a **security mapping table**.

This can be used to implement Row-Level Security based on user and region.

Conceptually:

```text
User
  ↓
Security Mapping
  ↓
Region
  ↓
Customer / Sales
  ↓
Filtered Report
```

This enables users to see only the data associated with their permitted region.

---

## 🔄 Data Modeling Workflow

```text
Raw Business Data
        ↓
    Power Query
        ↓
Data Cleaning & Transformation
        ↓
Identify Facts & Dimensions
        ↓
Relationship Design
        ↓
    Data Model
        ↓
   DAX Measures
        ↓
Row-Level Security
        ↓
Analytics / Reporting
```

---

## 💡 OLTP to OLAP Concept

The source data represents operational business processes such as:

```text
Customers
Orders
Products
Invoices
Payments
Shipments
Inventory
Campaigns
```

These operational datasets were organized into an analytical structure suitable for reporting and business analysis.

In simple terms:

```text
Operational Data
      ↓
Transformation
      ↓
Analytical Model
      ↓
Business Analysis
```

---

## 🛠️ Tools & Technologies

| Technology | Usage |
|---|---|
| Power BI | Data modeling and analytics |
| Power Query | Data transformation |
| DAX | Business measures |
| Excel | Source dataset |
| Star Schema | Analytical modeling |
| RLS | Data security |

---

## 🎯 Key Learnings

Through this project, I strengthened my understanding of:

- Identifying fact and dimension tables
- Designing analytical data models
- Creating relationships between tables
- Understanding relationship cardinality
- Working with multiple fact tables
- Building reusable dimensions
- Organizing DAX measures
- Implementing Row-Level Security
- Understanding OLTP and OLAP modeling concepts
- Preparing data models for business intelligence

---

## 📂 Repository Structure

```text
power-bi-data-modeling/
│
├── README.md
│
├── data-modeling.pbix
│
├── data_set.xlsx
│
└── images/
    └── data-model.png
```

---

## 👨‍💻 Author

**Jatindra Kumar Soni**

Data Analyst | SQL | Python | Power BI | Excel | Data Modeling
