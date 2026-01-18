
#  Bank Customer Churn, Rewards & Campaign Analytics (Power BI)

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat\&logo=powerbi\&logoColor=black)
![Domain](https://img.shields.io/badge/Domain-Banking%20%26%20Financial%20Services-1565C0?style=flat)
![Analytics](https://img.shields.io/badge/Analytics-Customer%20Churn%20%7C%20Campaign%20Analytics-6A1B9A?style=flat)
![Skills](https://img.shields.io/badge/Skills-DAX%20%7C%20Star%20Schema%20%7C%20Time%20Intelligence-black?style=flat)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-success?style=flat)

---

##  Overview

This Power BI project delivers an **end-to-end banking analytics solution** focused on **customer churn, rewards programme performance, and campaign effectiveness**.

Using a **scalable semantic layer**, the dashboard enables stakeholders to:

* Monitor customer engagement and churn risk
* Evaluate loyalty programme performance
* Measure campaign reach, conversion, and impact
* Analyse spend behaviour across customers, merchants, and regions

The solution mirrors **real-world banking and rewards analytics** used by commercial, marketing, and CRM teams.

---
##  Screenshots
https://github.com/karthic180/power-bi-dashboards/blob/main/banking.pdf
## PBI
https://github.com/karthic180/power-bi-dashboards/blob/main/banking.pbix

##  Dataset Used

**Primary Dataset (Base Customer Data):**
 Maven Analytics – Bank Customer Churn
[https://mavenanalytics.io/data-playground/bank-customer-churn](https://mavenanalytics.io/data-playground/bank-customer-churn)

**Alternative Dataset (Same Schema / Industry Standard):**
 Kaggle – Bank Customer Churn Modelling
[https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling](https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling)

### Dataset Features

* Customer demographics (Age, Gender, Geography)
* Account attributes (Balance, Credit Score, Tenure)
* Engagement indicators (Active Member, Number of Products)
* Churn flag (Exited / Retained)

The dataset is **extended and modelled** to simulate a **bank rewards and campaign analytics use case**, incorporating:

* Transactions
* Campaign impressions
* Bank programmes
* Merchants & retailers
* Time intelligence

---

##  Objectives

* Identify **churn risk and retention opportunities**
* Measure **programme and campaign effectiveness**
* Understand **customer spend behaviour**
* Deliver **stakeholder-ready KPIs** using reusable DAX measures
* Demonstrate **enterprise-style Power BI modelling**

---

##  Data Model (Star Schema)

### Fact Tables

* **FactTransactions** – customer transaction-level data (amount, channel, retailer, date)
* **FactCampaignImpressions** – campaign exposure, impressions, customers reached

### Dimension Tables

* **DimCustomers** – demographics, age band, region
* **DimProgrammes** – bank programme & tier (Core / Premium)
* **DimCampaigns** – campaign type (Email, Display, In-App, CLO)
* **DimMerchants** – merchant attributes
* **DimRetailers** – retailer and category
* **DimDates** – calendar & fiscal attributes (marked as Date table)
* **DimChannels** – transaction & campaign channels

### Modelling Principles

* One-to-many relationships (Dimensions → Facts)
* Single-direction filters for performance
* Shared dimensions across multiple fact tables
* All logic implemented as **measures**, not calculated columns

---

##  Dashboard Pages (1–5)

### **1️ Overview**

**Audience:** Executives & Senior Stakeholders
**KPIs**

* Total Transaction Value
* Total Transactions
* Total Customers
* Campaign Conversion Rate

**Key Insights**

* Overall commercial health
* Channel contribution snapshot

---

### **2️ Programme Performance**

**Audience:** Commercial & Partnerships

**Visuals**

* Revenue YTD by Programme Tier
* Programme adoption by Age Band

**Insights**

* Premium programmes generate higher revenue per customer
* Programme engagement varies strongly by demographic

---

### **3️ Campaign Engagement**

**Audience:** Marketing

**Visuals**

* Total Impressions
* Customers Reached
* Campaign Conversion Rate
* Incremental Revenue by Campaign Type

**Insights**

* Email & In-App outperform Display
* Some campaign types deliver negative incremental value

---

### **4️ Retailer Performance**

**Audience:** Partner & Merchant Teams

**Visuals**

* Spend by Retailer
* Channel usage by Retail Category

**Insights**

* Spend concentration among a small set of retailers
* Channel preference varies by category

---

### **5️ Spend Trends**

**Audience:** CRM & Analytics

**Visuals**

* Revenue YTD by Region
* Revenue YTD by Age Band

**Insights**

* London & South East lead revenue
* Strong performance from 25–44 age segments

---

##  Key DAX Measures

```DAX
Total Customers =
DISTINCTCOUNT ( DimCustomers[CustomerID] )
```

```DAX
Total Transactions =
COUNTROWS ( FactTransactions )
```

```DAX
Total Transaction Value =
SUM ( FactTransactions[amount_gbp] )
```

```DAX
Average Transaction Value =
DIVIDE ( [Total Transaction Value], [Total Transactions] )
```

```DAX
Revenue YTD =
TOTALYTD (
    [Total Transaction Value],
    DimDates[Date]
)
```

```DAX
Total Impressions =
SUM ( FactCampaignImpressions[impressions] )
```

```DAX
Customers Reached =
DISTINCTCOUNT ( FactCampaignImpressions[customer_id] )
```

```DAX
Campaign Conversion Rate =
DIVIDE (
    [Total Transactions],
    [Total Impressions]
)
```

```DAX
Churn Rate % =
DIVIDE (
    CALCULATE ( COUNT ( DimCustomers[CustomerID] ), DimCustomers[Exited] = 1 ),
    [Total Customers]
)
```

---

##  Business Insights

* A small customer segment contributes a disproportionate share of revenue
* Premium programmes significantly outperform core tiers
* Campaign ROI varies widely by channel and campaign type
* Regional and demographic patterns highlight clear growth opportunities
* Inactive customers show materially higher churn risk

---

## Tools & Skills Demonstrated

* Power BI Desktop
* DAX (CALCULATE, RANKX, Time Intelligence)
* Star schema & semantic layer design
* Customer churn & lifecycle analytics
* Campaign and commercial performance analysis
* Stakeholder-focused dashboard storytelling

---

##  Use Cases

* Banking & financial services analytics
* Rewards & loyalty programme optimisation
* Marketing campaign performance analysis
* Customer retention & churn monitoring

---
