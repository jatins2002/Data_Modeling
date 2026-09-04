# 📊 Power BI Data Modeling Project

## 📌 Project Overview

This project focuses on designing a scalable analytical data model in Power BI using multiple business datasets.

The objective was to transform raw operational data related to sales, customers, products, orders, inventory, marketing campaigns, and targets into a structured model suitable for business intelligence and analytical reporting.

The project demonstrates practical understanding of:

- Data Modeling
- Star Schema
- Fact and Dimension Tables
- Table Relationships
- Power Query
- DAX Measures
- Row-Level Security (RLS)
- OLTP to OLAP modeling concepts
- Business Intelligence architecture

---

## 🗂️ Source Data

The source dataset contains multiple business entities, including:

- Customers
- Products
- Orders (2025 & 2026)
- Order Line Items
- Invoices
- Invoice Lines
- Payments
- Shipments
- Inventory
- Campaign Logs
- Campaign Products
- Sales Targets
- Cities
- Regions
- Customer Contacts
- Exchange Rates
- Security/User Mapping

These datasets represent different operational areas of a business and were transformed into an analytical Power BI model.

---

## 🏗️ Data Model

The Power BI model contains multiple fact and dimension tables.

### Fact Tables

#### `fact_sales`
Central transactional sales table used for analyzing:

- Orders
- Revenue
- Quantity
- Discounts
- Customers
- Products
- Geography

#### `fact_inventory`
Stores product inventory information for inventory-level analysis.

#### `fact_campaign_spend`
Contains marketing campaign performance information such as:

- Impressions
- Clicks
- Spend

#### `fact_promotion`
Connects marketing campaigns with promoted products.

#### `fact_sales_target`
Contains revenue targets for comparing actual performance against business targets.

#### `fact_order_process`
Supports order lifecycle and operational analysis using order, invoice, payment, and delivery information.

---

## 📐 Dimension Tables

The model includes reusable dimensions such as:

### `dim_date`
Calendar dimension used for time-based analysis.

Includes attributes such as:

- Date
- Year
- Month

### `dim_customer`
Contains customer-related attributes including:

- Customer
- Region
- Account Manager
- City
- Contact Information
- Payment Terms

### `dim_products`
Contains descriptive product information such as:

- Product
- Brand
- Category
- Subcategory
- Supplier

### `dim_geo`
Provides geographical attributes for location-based analysis.

### `dim_campaign`
Stores marketing campaign attributes.

### `dim_order_flag`
Contains descriptive order characteristics such as:

- Order Channel
- Priority
- Status

---

## 🔗 Relationships

The model primarily uses **one-to-many (1:*) relationships** between dimensions and fact tables.

Example:

dim_customer
      |
      | 1
      |
      *
fact_sales

Similar relationships connect:

dim_date → fact_sales  
dim_products → fact_sales  
dim_geo → fact_sales  
dim_campaign → fact_campaign_spend  

This approach reduces unnecessary duplication and provides consistent filtering across reports.

---

## 🔐 Row-Level Security

The project also includes a security mapping table.

Row-Level Security (RLS) can be used to restrict report data based on the logged-in user's assigned region.

Example:

User
↓
Security Mapping
↓
Region
↓
Customer / Sales
↓
Filtered Report

This allows different users to access only the business data relevant to their assigned region.

---

## 🧮 DAX Measures

A dedicated Measures table was created to organize business calculations.

Examples include measures for:

- Total Sales
- Total Orders
- Total Customers
- Total Active Customers
- Average Order Value
- Year-over-Year performance

Keeping measures in a dedicated table improves model organization and maintainability.

---

## 🔄 Data Modeling Workflow

Raw Data
   ↓
Power Query
   ↓
Data Cleaning & Transformation
   ↓
Fact / Dimension Identification
   ↓
Relationship Design
   ↓
Star Schema
   ↓
DAX Measures
   ↓
Row-Level Security
   ↓
Analytical Power BI Model
   ↓
Dashboard / Business Analysis

---

## 🧠 Key Concepts Demonstrated

### OLTP vs OLAP

The raw datasets represent operational business processes such as:

- Orders
- Payments
- Shipments
- Invoices
- Customers

These were transformed into an analytical model optimized for reporting and analysis.

### Star Schema

The model separates:

**Facts**
- Numeric business events and measurements

from

**Dimensions**
- Descriptive business attributes

This makes analytical queries and Power BI filtering easier to manage.

---

## 🛠️ Tools & Technologies

- Microsoft Power BI
- Power Query
- DAX
- Excel
- Data Modeling
- Star Schema
- Row-Level Security (RLS)

---

## 📸 Data Model

![Power BI Data Model](images/data-model.png)

The model integrates sales, customers, products, geography, marketing, inventory, targets, and order-processing data into a unified analytical structure.

---

## 🎯 Key Learnings

Through this project, I strengthened my understanding of:

- Designing analytical data models
- Identifying fact and dimension tables
- Building star schemas
- Managing table relationships
- Understanding relationship cardinality
- Creating reusable dimensions
- Organizing DAX measures
- Implementing Row-Level Security
- Converting operational data into an analytics-ready model

---

## 👨‍💻 Author

**Jatindra Kumar Soni**

Aspiring Data Analyst | SQL | Python | Power BI | Excel | Data Modeling
