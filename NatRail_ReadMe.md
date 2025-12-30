# UK Rail Ticket Analytics Dashboard (Mock)

## Overview

This project analyses over **500,000 UK National Rail ticket transactions** to uncover trends in passenger behaviour, journey performance, revenue, and station activity.  
The dashboard is built end-to-end in **Power BI**, covering data cleaning, modelling, DAX measures, and interactive visual reporting.

The goal is to help stakeholders understand:

- How and where passengers travel  
- Which ticket types and classes drive revenue  
- What causes delays and how they link to refunds  
- How customer purchase behaviour varies across channels and payment methods  

---

## Dataset

The dataset used in this project is publicly available on Kaggle:

**National Rail UK Train Ticket Data**  
 https://www.kaggle.com/datasets/motsimaslam/national-rail-uk-train-ticket-data

The dataset includes:

- Ticket transactions with ticket type, class, and railcard usage  
- Journey details including origin, destination, and distance  
- Delay information and reasons  
- Refunds and related attributes  

---

## Files in This Project

- **Dashboard PDF:**  
https://github.com/karthic180/power-bi-dashboards/blob/main/National%20Rail%20UK%20Train%20Ticket%20Data.pdf
(Snapshot of the Power BI report pages.)

- **Project ReadMe:**  
https://github.com/karthic180/power-bi-dashboards/blob/main/NatRail_ReadMe.md
  High-level explanation of the dashboard structure and pages.

- **Key Insights:**  
https://github.com/karthic180/power-bi-dashboards/blob/main/NatRail_KeyTakeaways.md
  Detailed summary of findings and business insights.

---

## Business Questions Answered

- Which stations generate the highest passenger traffic?  
- How do ticket type and class impact overall revenue?  
- What are the main causes of journey delays?  
- What patterns exist in refund requests, and how can they be reduced?  
- How do purchase channels (online vs station) and payment methods vary by customer behaviour?  

---

## Key Insights Summary

- **Online purchases dominate**, with credit cards as the most common payment method.  
- **Total revenue exceeds £30M**, driven largely by return and Anytime tickets.  
- **Average ticket price is £23.44**, with **First Class averaging around £75**, significantly higher than Standard Class.  
- **Signal failures** are the leading cause of delays and strongly linked to refund requests.  
- Only about **3% of journeys result in refunds**, mostly for delays exceeding 30 minutes.  
- **London King’s Cross** is the busiest departure station, followed by other major UK hubs such as London Euston and Birmingham New Street.  
- **Standard Class accounts for ~90% of journeys**, while First Class, though lower in volume, contributes disproportionately to revenue.  

---

## Tools & Techniques

- **Power BI Desktop** – data modelling, DAX, and report design  
- **Power Query** – data cleaning and transformation  
- **DAX** – calculated measures for KPIs and advanced metrics  
- **Microsoft Excel / CSV** – initial data inspection and validation  

---

## Possible Extensions

- Add **time-series analysis** of delays and refunds by month/season.  
- Incorporate **customer segmentation** if demographic data is available.  
- Build **scenario analysis** (e.g., impact of reducing specific delay causes).  
