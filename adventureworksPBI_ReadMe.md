# AdventureWorks Power BI Dashboard

##  Project Overview

This project showcases an **end-to-end Power BI solution built using the AdventureWorks dataset**, designed to demonstrate enterprise-style **data modelling, DAX proficiency, and business-focused reporting**.

The report simulates a real-world commercial analytics use case, covering **Internet and Reseller sales**, customer behaviour, product performance, geographic trends, and time intelligence. The focus is on building a **scalable semantic layer** with reusable measures and clear separation between fact and dimension tables.

---

##  Objectives

* Build a clean **star-schema data model** with multiple fact tables
* Create a reusable **semantic layer** using DAX measures
* Deliver insights tailored to different business audiences
* Apply advanced concepts such as **time intelligence**, **currency conversion**, and **many-to-many relationships**

---

##  Data Model

### Fact Tables

* **FactInternetSales** – Online customer sales (B2C)
* **FactResellerSales** – Reseller and wholesale sales (B2B)
* **FactCurrencyRate** – Exchange rates by date and currency

### Dimension Tables

* **DimDate** – Calendar and fiscal date attributes (marked as Date table)
* **DimCustomer** – Customer demographics and attributes
* **DimProduct** – Product details
* **DimProductSubcategory** / **DimProductCategory** – Product hierarchy
* **DimSalesTerritory** – Geographic and regional hierarchy
* **DimCurrency** – Currency codes and descriptions
* **DimSalesReason** – Reason for sale (via bridge table)

### Modelling Approach

* One-to-many relationships from dimensions to fact tables
* Single-direction filter flow to avoid ambiguity
* Shared dimensions across multiple fact tables
* Many-to-many relationship handled via a bridge table for Sales Reason

This approach ensures **performance, clarity, and scalability**.

---

##  Report Pages

###  Executive Overview

**Audience:** Senior stakeholders

* Total Sales, Sales YTD, YoY Growth %, Average Order Value
* Sales trends over time
* Internet vs Reseller sales contribution

###  Sales Performance

**Audience:** Sales & Commercial teams

* Sales by channel and territory
* Top-performing products
* Monthly performance trends

###  Product Performance

**Audience:** Product & Merchandising teams

* Category → Subcategory → Product hierarchy
* Top and bottom products by sales
* Contribution to category sales

###  Customer Analytics

**Audience:** Marketing & CRM

* Total customers and sales per customer
* Customer lifetime value analysis
* High-value customer identification

###  Geography & Territory

**Audience:** Regional managers

* Sales by country and region
* Territory contribution analysis
* Regional growth trends

---

## 📐 Key DAX Measures

Examples of core measures used throughout the report:

* **Total Sales**
* **Sales YTD / Sales PY**
* **Year-over-Year Growth %**
* **Average Order Value**
* **Rolling 12-Month Sales**
* **Customer Lifetime Value**
* **Territory Contribution %**

All business logic is implemented as **measures rather than calculated columns**, ensuring flexibility across visuals and filter contexts.

---

##  Key Insights

* Internet and Reseller channels show distinct seasonal patterns
* A small proportion of customers contribute a significant share of total revenue
* Certain product categories consistently outperform others across territories
* Currency conversion can materially impact reported revenue trends

---

##  Tools & Technologies

* **Power BI Desktop**
* **DAX** (Time Intelligence, Context Transition, Ranking)
* **AdventureWorks Dataset**
* **Star Schema Data Modelling**

---

##  How to Use

1. Download the `.pbix` file from this repository (https://github.com/karthic180/power-bi-dashboards/blob/main/adad.pbix) 
2. Open in Power BI Desktop
3. Explore the report using slicers for Date, Territory, Product, and Currency

---
## PDF ScreenShots
(https://github.com/karthic180/power-bi-dashboards/blob/main/adveantureworks.pdf)

##  Skills Demonstrated

* Enterprise data modelling
* Advanced DAX and time intelligence
* Commercial and customer analytics
* Dashboard design tailored to business audiences
* GitHub documentation and portfolio presentation

---
