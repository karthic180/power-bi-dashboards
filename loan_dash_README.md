**Loan Default Dashboard – Power BI
Project Overview**

This project is a Power BI dashboard that analyzes loan defaults using a Kaggle dataset. The dashboard provides insights into:

Borrower characteristics (Credit Score, Income, Employment, Dependents, Education)

Loan terms and risk drivers (Loan Amount, Interest Rate, Loan Term, DTI)

Default vs Non Default analysis

Segment analysis across borrower and loan profiles

The goal is to visualize trends, highlight risk factors, and provide actionable insights for loan management.

**Dataset**

Source: Kaggle – Loan Default Dataset

**Columns include:**

loan_id – Unique loan identifier

default – Default status (Default / Non Default)

CreditScore – Borrower credit score

income – Borrower income

employmenttype – Employment type

numdependents – Number of dependents

education – Education level

loanamount – Loan amount

interestrate – Loan interest rate

loanterm – Loan term in months

dtiratio – Debt-to-Income ratio

Note: The dataset does not contain loan approval dates or geographic fields.

**Features & Pages**
Page 1: KPI Overview

Total Loans, Total Defaults, Total Non Defaults

Default Rate (%)

Card visuals for quick overview

Page 2: Borrower Profile & Risk

Default rate by Credit Score, Income Band, Employment Type, Dependents, Education

Visuals: Clustered/Stacked Column Charts, Bar Charts

Slicers: Gender, Marital Status, Loan Purpose

Page 3: Loan Terms & Risk Drivers

Default rate by Loan Term, Loan Amount, Interest Rate, DTI

Visuals: Clustered Columns, Scatter Charts

Slicers: Loan Purpose, Employment Type, Credit Score Band

Page 4: Borrower Segments & Default

Segment-wise default comparison for Employment Type, Education, Marital Status, Income Band

Visuals: Clustered/Stacked Column Charts

Page 5: Default vs Non Default Segments

Compare Default vs Non Default across Credit Score, Income, Employment, and Loan Term

Optional donut chart for overall default proportion

Slicers for dynamic filtering

Page 6: Risk Drivers Summary (Optional)

Scatter charts to analyze loan amount, interest rate, DTI vs Default

Helps identify key risk drivers

**Measures & Calculated Columns**
Measures
Total Loans = COUNT('loan_default'[loan_id])

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

Default Rate (%) = DIVIDE([Total Defaults],[Total Loans])

Calculated Columns
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

Income Band =
IF(
    'loan_default'[income] < 30000, "Low Income",
    IF('loan_default'[income] < 70000, "Medium Income", "High Income")
)

Loan Term Band =
SWITCH(
    TRUE(),
    'loan_default'[loanterm] <= 36, "<= 36 Months",
    'loan_default'[loanterm] <= 60, "37–60 Months",
    "> 60 Months"
)

**Setup Instructions**

Download the loan_default CSV dataset from Kaggle.

Open Power BI Desktop.

Click Get Data → Text/CSV and import the dataset.

Create the calculated columns and measures as listed above.

Build visuals page by page as described.

Apply consistent formatting:

Colors: Red = Default, Green = Non Default

Data labels ON

Slicers for filtering
**Dashboard Insights**

Borrowers with low credit scores or high DTI ratios have higher default rates.

Income level, employment type, and loan term significantly affect default risk.

Visualizing Default vs Non Default across segments helps identify high-risk groups.
**Technologies Used
**
Power BI Desktop

DAX for measures and calculated columns

CSV dataset from Kaggle
**License**

Dataset and project for educational purposes only.
