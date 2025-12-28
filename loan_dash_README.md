
#  Loan Default Dashboard – Power BI

##  Project Overview

This project is an **interactive Power BI dashboard** that analyzes loan defaults using a Kaggle dataset.  
The dashboard focuses on understanding **borrower risk**, **loan characteristics**, and **default behavior** through clear KPIs and segment-level analysis.

The goal is to **visualize trends, highlight key risk drivers, and provide actionable insights** for loan management, underwriting, and portfolio monitoring.

---

## 📊Key Analysis Areas

- **Borrower characteristics**
  - Credit Score
  - Income
  - Employment Type
  - Number of Dependents
  - Education Level

- **Loan terms & risk drivers**
  - Loan Amount
  - Interest Rate
  - Loan Term
  - Debt-to-Income (DTI) Ratio

- **Default vs Non-Default analysis**
- **Segment-level risk comparison**

---

## Dataset

**Source: Kaggle – Loan Default Dataset**  
(https://www.kaggle.com/datasets/nikhil1e9/loan-default?resource=download)

### Columns Included

- `loan_id` – Unique loan identifier  
- `default` – Loan status (Default / Non Default)  
- `CreditScore` – Borrower credit score  
- `income` – Borrower income  
- `employmenttype` – Employment type  
- `numdependents` – Number of dependents  
- `education` – Education level  
- `loanamount` – Loan amount  
- `interestrate` – Loan interest rate  
- `loanterm` – Loan term in months  
- `dtiratio` – Debt-to-Income ratio  

> **Note:** The dataset does not include loan approval dates or geographic information.

---

##  Dashboard Pages & Features

### Page 1: KPI Overview
- Total Loans
- Total Defaults
- Total Non-Defaults
- Default Rate (%)
- Card visuals for quick executive summary

---

### Page 2: Borrower Profile & Risk
- Default rate by:
  - Credit Score Band
  - Income Band
  - Employment Type
  - Number of Dependents
  - Education Level
- **Visuals:** Clustered & stacked column charts, bar charts
- **Slicers:** Gender, Marital Status, Loan Purpose

---

### Page 3: Loan Terms & Risk Drivers
- Default rate by:
  - Loan Term
  - Loan Amount
  - Interest Rate
  - DTI Ratio
- **Visuals:** Clustered columns, scatter charts
- **Slicers:** Loan Purpose, Employment Type, Credit Score Band

---

### Page 4: Borrower Segments & Default
- Segment-wise default comparison by:
  - Employment Type
  - Education
  - Marital Status
  - Income Band
- **Visuals:** Stacked & clustered column charts

---

### Page 5: Default vs Non-Default Segments
- Side-by-side comparison across:
  - Credit Score
  - Income
  - Employment Type
  - Loan Term
- Optional donut chart for overall default proportion
- Interactive slicers for dynamic filtering

---

### Page 6: Risk Drivers Summary (Optional)
- Scatter charts analyzing:
  - Loan Amount vs Default
  - Interest Rate vs Default
  - DTI Ratio vs Default
- Helps identify key financial risk drivers

---

##  Measures & Calculated Columns

### DAX Measures

```DAX
Total Loans =
COUNT('loan_default'[loan_id])

Total Defaults =
CALCULATE(
    COUNT('loan_default'[loan_id]),
    'loan_default'[default] = "Default"
)

Total Non Defaults =
CALCULATE(
    COUNT('loan_default'[loan_id]),
    'loan_default'[default] = "Non Default"
)

Default Rate (%) =
DIVIDE([Total Defaults], [Total Loans])
````

---

### Calculated Columns

```DAX
Credit Score Band =
IF(
    ISBLANK('loan_default'[CreditScore]),
    "Unknown",
    SWITCH(
        TRUE(),
        'loan_default'[CreditScore] < 580, "Poor",
        'loan_default'[CreditScore] < 670, "Fair",
        'loan_default'[CreditScore] < 740, "Good",
        "Excellent"
    )
)
```

```DAX
Income Band =
IF(
    'loan_default'[income] < 30000, "Low Income",
    IF('loan_default'[income] < 70000, "Medium Income", "High Income")
)
```

```DAX
Loan Term Band =
SWITCH(
    TRUE(),
    'loan_default'[loanterm] <= 36, "<= 36 Months",
    'loan_default'[loanterm] <= 60, "37–60 Months",
    "> 60 Months"
)
```

---

##  Setup Instructions

1. Download the **loan_default CSV dataset** from Kaggle
2. Open **Power BI Desktop**
3. Select **Get Data → Text/CSV** and import the dataset
4. Create the calculated columns and DAX measures listed above
5. Build visuals page by page as described
6. Apply consistent formatting:

   * **Red** = Default
   * **Green** = Non-Default
   * Data labels enabled
   * Slicers for interactive filtering

---

##  Key Dashboard Insights

* Borrowers with **low credit scores** and **high DTI ratios** show higher default rates
* **Income level, employment type, and loan term** significantly impact default behavior
* Segment-based Default vs Non-Default analysis helps identify **high-risk borrower groups**

---

##  Technologies Used

* Power BI Desktop
* DAX (Measures & Calculated Columns)
* CSV dataset from Kaggle

---

##  License

This project and dataset are intended for **educational and portfolio purposes only**.
