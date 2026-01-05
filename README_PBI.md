## Power BI Dashboards Collection
A curated collection of Power BI dashboards covering a variety of domains such as video games, finance, telecom, airlines, LEGO, rail, golf, and restaurant analytics. Each dashboard includes dataset links, PDF previews, key DAX measures, business insights, and answers to important business questions, helping users explore data trends, performance metrics, and actionable insights across industries.
---

## **Table of Contents**

1. [Global Video Game Market Analysis Dashboard](#global-video-game-market-analysis-dashboard)
2. [Golf Performance Dashboard](#golf-performance-dashboard)
3. [UK Rail Dashboard](#uk-rail-dashboard)
4. [LEGO Sets & Themes Dashboard](#lego-sets-themes-dashboard)
5. [UK Broadband Performance Dashboard](#uk-broadband-performance-dashboard)
6. [Airlines Dashboard](#airlines-dashboard)
7. [Loan Analytics Dashboard](#loan-analytics-dashboard)
8. [Orders & Sales Dashboard](#orders-sales-dashboard)

---

<p>
  <img src="https://img.shields.io/badge/Domain-Video%20Games-4CAF50?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Sales%20Performance%20%26%20Trends-03A9F4?style=flat" />
  <a href="https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings"></a>
<img src="https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=kaggle&logoColor=white" /></a>
 <img src="https://img.shields.io/badge/Analytics-Type_Time_Series-6A1B9A?style=flat" />
<img src="https://img.shields.io/badge/Model-Star_Schema-00599C?style=flat" />
<img src="https://img.shields.io/badge/Granularity-Platform_&_Region-455A64?style=flat" />
<img src="https://img.shields.io/badge/Insight-Lifecycle_Analysis-2E7D32?style=flat" />

</p>

**Dashboard PDF:** [Video Game Dashboard PDF](add-your-link-here)
**Dataset:** [Video Game Sales Dataset](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)

###  Key Measures / DAX

```DAX
Total Global Sales = SUM(VideoGame[Global_Sales])
Total NA Sales = SUM(VideoGame[NA_Sales])
Total EU Sales = SUM(VideoGame[EU_Sales])
Top Platform = RANKX(ALL(VideoGame[Platform]), [Total Global Sales], , DESC)
Top Publisher = RANKX(ALL(VideoGame[Publisher]), [Total Global Sales], , DESC)
Avg Rating = AVERAGE(VideoGame[Rating])
Sales Over Time = CALCULATE([Total Global Sales], DATESYTD(VideoGame[Year_of_Release]))
```

###  Key Business Questions Answered

* Which platforms generate the highest global sales?
* What genre trends dominate over the years?
* How do regional preferences impact global sales?
* Which publishers are the most successful globally and regionally?
* How long is the lifecycle of a gaming platform from launch to peak sales?

###  Key Insights Summary

* North America remains the largest market, followed by Europe and Japan.
* PlayStation 2 and Nintendo Wii show long, sustained sales lifecycles.
* Action and Shooter genres dominate globally; RPGs are especially strong in Japan.
* Electronic Arts, Activision, and Nintendo consistently lead publisher performance.
* Regional trends reveal distinct preferences: Europe favors Sports/Action, Japan favors RPGs.

---

## Golf Performance Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Sports-4CAF50?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Player%20Performance-03A9F4?style=flat" />
  <img src="https://img.shields.io/badge/Analytics-Type_Performance_Tracking-2E7D32?style=flat" />
<img src="https://img.shields.io/badge/Grain-Round_Level-455A64?style=flat" />
<img src="https://img.shields.io/badge/Metric-Player_Ranking-0288D1?style=flat" />
<img src="https://img.shields.io/badge/Use_Case-Coaching_Insights-6A1B9A?style=flat" />

</p>

**Dashboard PDF:** [Golf Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/golf%20dashboard%20snap.pdf)
**Dataset:** [Golf Dataset](https://support.minitab.com/en-us/datasets/time-series-data-sets/golf-driver-sales/)

###  Key Measures / DAX

```DAX
Total Rounds = COUNT(Golf[RoundID])
Avg Score = AVERAGE(Golf[Score])
Best Player = RANKX(ALL(Golf[PlayerName]), [Avg Score], , ASC)
Score Improvement = [Avg Score Previous Period] - [Avg Score]
Avg Driving Distance = AVERAGE(Golf[DrivingDistance])
```

###  Key Business Questions Answered

* Which players have the best performance across rounds?
* How does scoring trend over time for individual players?
* Which courses or holes impact performance most?
* How can training strategies be optimized based on performance metrics?

###  Key Insights Summary

* Player scoring trends are clearly visible, highlighting improvement areas.
* Competitive strengths and weaknesses are evident in player-to-player comparisons.
* Course difficulty significantly influences scoring outcomes.
* Round-level insights support coaching and performance optimization.

---

## UK Rail Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Transportation-1976D2?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Revenue%20%26%20Delays-4CAF50?style=flat" />
  <img src="https://img.shields.io/badge/Analytics-Operational_Performance-D32F2F?style=flat" />
<img src="https://img.shields.io/badge/KPI-On--Time_Performance-455A64?style=flat" />
<img src="https://img.shields.io/badge/Domain-Public_Sector-37474F?style=flat" />
<img src="https://img.shields.io/badge/Metric-Revenue_&_Refunds-2E7D32?style=flat" />

</p>

**Dashboard PDF:** [UK Rail Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/National%20Rail%20UK%20Train%20Ticket%20Data.pdf)
**Dataset:** [National Rail Dataset](https://www.kaggle.com/datasets/motsimaslam/national-rail-uk-train-ticket-data)

###  Key Measures / DAX

```DAX
Total Revenue = SUM(Rail[Revenue])
Total Journeys = COUNT(Rail[JourneyID])
Avg Ticket Price = AVERAGE(Rail[TicketPrice])
Refund Rate = DIVIDE(CALCULATE([Total Journeys], Rail[RefundFlag]=1), [Total Journeys])
OnTime Performance = DIVIDE(CALCULATE([Total Journeys], Rail[DelayMinutes]<=0), [Total Journeys])
```

###  Key Business Questions Answered

* Which stations generate the highest revenue and traffic?
* What causes delays and refunds most frequently?
* How do ticket prices and classes impact revenue?
* What is the overall performance of rail operations in terms of timeliness?

###  Key Insights Summary

* London King’s Cross is the busiest departure station (>50,000 journeys).
* Signal failures are the leading cause of delays and refunds.
* Online purchases dominate (58%) with credit cards most common.
* Revenue exceeds £30M, mainly from Anytime and Return tickets.
* Average ticket price: £23.44; First Class averages £75. Refunds occur in ~3% of journeys.

---

## LEGO Sets & Themes Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Consumer%20Products-E91E63?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Themes%20%26%20Releases-FFC107?style=flat" />
  <a href="https://www.kaggle.com/datasets/jkraak/lego-sets-and-themes-database"> 
  <img src="https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=kaggle&logoColor=white" /></a>
  <img src="https://img.shields.io/badge/Analytics-Type_Product_Portfolio-0288D1?style=flat" />
<img src="https://img.shields.io/badge/Dimension-Time_&_Theme-455A64?style=flat" />
<img src="https://img.shields.io/badge/Insight-Release_Trends-2E7D32?style=flat" />
<img src="https://img.shields.io/badge/Use_Case-Merchandising_Strategy-6A1B9A?style=flat" />

</p>

**Dashboard PDF:** [LEGO Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/lego%20set%20themes%20dash.pdf)
**Dataset:** [LEGO Sets & Themes Dataset](https://www.kaggle.com/datasets/jkraak/lego-sets-and-themes-database)

### Key Measures / DAX

```DAX
Total Sets = COUNT(LEGO[SetID])
Total Themes = DISTINCTCOUNT(LEGO[Theme])
Sets per Year = CALCULATE([Total Sets], YEAR(LEGO[ReleaseYear]))
Top Theme = RANKX(ALL(LEGO[Theme]), [Total Sets], , DESC)
Average Pieces per Set = AVERAGE(LEGO[NumPieces])
```

###  Key Business Questions Answered

* Which LEGO themes generate the most sets and popularity?
* How has LEGO set release volume changed over time?
* Which themes are top-performing historically and currently?

###  Key Insights Summary

* Strong growth in set releases over time.
* Top-performing themes identified for strategic focus.
* Set complexity has increased, reflecting evolving consumer demand.

---
## UK Broadband Performance Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Telecom-9C27B0?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Speed%20%26%20Cost-FF9800?style=flat" />
  <img src="https://img.shields.io/badge/Analytics-Infrastructure_Performance-D32F2F?style=flat" />
<img src="https://img.shields.io/badge/Comparison-Urban_vs_Rural-455A64?style=flat" />
<img src="https://img.shields.io/badge/KPI-Cost_per_Mbps-2E7D32?style=flat" />
<img src="https://img.shields.io/badge/Domain-Telecom_Regulatory-37474F?style=flat" />

</p>

**Dashboard PDF:** [UK Broadband Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/BB%20PBI%20Mock.pdf)
**Dataset:** [UK Broadband Performance Dataset](https://www.data.gov.uk/dataset/dfe843da-06ca-4680-9ba0-fbb27319e402/uk-fixed-line-broadband-performance)

###  Key Measures / DAX

```DAX
Avg Download Speed = AVERAGE(Broadband[DownloadSpeed])
Avg Upload Speed = AVERAGE(Broadband[UploadSpeed])
Cost per Mbps = DIVIDE(AVERAGE(Broadband[MonthlyCost]), [Avg Download Speed])
Top Provider = RANKX(ALL(Broadband[Provider]), [Avg Download Speed], , DESC)
Urban vs Rural Speed Ratio = DIVIDE([Avg Download Speed], CALCULATE([Avg Download Speed], Broadband[Area]="Rural"))
```

###  Key Business Questions Answered

* Which broadband providers deliver the fastest speeds and best value?
* How does broadband performance differ between urban and rural areas?
* Are there regions with consistently low speeds or high costs?
* How can cost-to-speed ratio inform provider comparisons?

###  Key Insights Summary

* Urban broadband speeds are nearly 3× faster than rural speeds.
* Virgin Media leads in speed and value.
* Some providers charge premium prices without proportional performance.
* East Midlands ranks highest for balanced cost and speed.
* Upload speeds remain consistently low across all providers, impacting remote work.

---

## Airlines Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Aviation-0288D1?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Passenger%20Satisfaction-4CAF50?style=flat" />
  <img src="https://img.shields.io/badge/Analytics-Customer_Experience-0288D1?style=flat" />
<img src="https://img.shields.io/badge/Metric-Satisfaction_Score-455A64?style=flat" />
<img src="https://img.shields.io/badge/Dimension-Time_&_Route-6A1B9A?style=flat" />
<img src="https://img.shields.io/badge/Use_Case-Service_Quality_Analysis-2E7D32?style=flat" />

</p>

**Dashboard PDF:** [Airline Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/Airline_MOCK.pdf)
**Dataset:** [Airline Satisfaction Dataset](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)

###  Key Measures / DAX

```DAX
Total Passengers = SUM(Airline[Passengers])
Total Flights = COUNT(Airline[FlightID])
Avg Satisfaction Score = AVERAGE(Airline[SatisfactionScore])
Flights by Year = CALCULATE([Total Flights], YEAR(Airline[FlightDate]))
Satisfaction by Airline = CALCULATE([Avg Satisfaction Score], ALLEXCEPT(Airline, Airline[AirlineName]))
```

###  Key Business Questions Answered

* How have passenger and flight volumes changed over time?
* Which airlines deliver the highest passenger satisfaction?
* How do satisfaction scores vary by route, class, and service quality?
* What long-term trends exist in airline operations and customer experience?

###  Key Insights Summary

* Multi-year passenger and flight trends reveal periods of growth and recovery.
* Airline performance varies significantly by region and service class.
* Satisfaction is closely linked to punctuality, in-flight services, and route popularity.
* Passenger volume and satisfaction data support operational and service planning.

---

## Loan Analytics Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Finance-3F51B5?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Default%20Risk-FF9800?style=flat" />
  <a href="https://www.kaggle.com/datasets/nikhil1e9/loan-default">
    <img src="https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=flat&logo=kaggle&logoColor=white" /></a>
  <img src="https://img.shields.io/badge/Analytics-Risk_Analytics-D32F2F?style=flat" />
<img src="https://img.shields.io/badge/KPI-Default_Rate-455A64?style=flat" />
<img src="https://img.shields.io/badge/Metric-Revenue_at_Risk-2E7D32?style=flat" />
<img src="https://img.shields.io/badge/Use_Case-Credit_Underwriting-6A1B9A?style=flat" />

</p>

**Dashboard PDF:** [Loan Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/loan%20dash%20pbi.pdf)
**Dataset:** [Loan Default Dataset](https://www.kaggle.com/datasets/nikhil1e9/loan-default?resource=download)

###  Key Measures / DAX

```DAX
Total Loans = COUNT(Loan[LoanID])
Total Defaults = CALCULATE([Total Loans], Loan[DefaultFlag] = 1)
Default Rate = DIVIDE([Total Defaults], [Total Loans])
Avg Loan Amount = AVERAGE(Loan[LoanAmount])
Revenue at Risk = SUMX(FILTER(Loan, Loan[DefaultFlag]=1), Loan[LoanAmount])
```

###  Key Business Questions Answered

* Which borrower characteristics are most associated with loan default?
* How do credit score, income, and employment length influence default risk?
* Which loan purposes and terms carry higher default rates?
* How can lenders segment customers for better underwriting decisions?
* What KPIs best represent overall portfolio health?

###  Key Insights Summary

* Credit score, income, and employment length are the strongest predictors of default.
* Clear segmentation of default vs non-default borrowers across demographics.
* Certain loan purposes exhibit significantly higher default rates.
* Portfolio KPIs highlight total loans, defaults, and default rate.
* Interactive slicers allow deep exploration of borrower behavior and risk patterns.

---

## Orders & Sales Dashboard

<p>
  <img src="https://img.shields.io/badge/Domain-Restaurant%20Analytics-brown?style=flat" />
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Focus-Sales%20Performance-03A9F4?style=flat" />
  <img src="https://img.shields.io/badge/Analytics-Commercial_Performance-0288D1?style=flat" />
<img src="https://img.shields.io/badge/KPI-Avg_Order_Value-455A64?style=flat" />
<img src="https://img.shields.io/badge/Dimension-Geo_&_Time-6A1B9A?style=flat" />
<img src="https://img.shields.io/badge/Use_Case-Demand_Analysis-2E7D32?style=flat" />

</p>

**Dashboard PDF:** [Orders Dashboard PDF](https://github.com/karthic180/power-bi-dashboards/blob/main/OrdersDash.pdf)
**Dataset:** [Restaurant Orders Dataset](https://github.com/karthic180/power-bi-dashboards/blob/main/restusrnat%20orders.xlsx)

###  Key Measures / DAX

```DAX
Total Revenue = SUM(Orders[Revenue])
Total Orders = DISTINCTCOUNT(Orders[OrderID])
Avg Order Value = DIVIDE([Total Revenue], [Total Orders])
Revenue by State = CALCULATE([Total Revenue], ALLEXCEPT(Orders, Orders[State]))
Top Menu Item = RANKX(ALL(Orders[Item]), [Total Orders], , DESC)
Monthly Sales = CALCULATE([Total Revenue], DATESMTD(Orders[OrderDate]))
```

###  Key Business Questions Answered

* Which restaurants generate the most revenue and why?
* How do sales and order volume vary across months?
* Which states and cities contribute the highest sales?
* How do order values differ across customer segments and restaurant tiers?
* Which menu items or cuisines drive higher order values?
* Where are the strongest geographic hotspots for demand?

###  Key Insights Summary

* Revenue is concentrated among a small group of high-performing restaurants.
* Geographic analysis highlights hotspots like San Antonio, Austin, Amarillo, and San Diego.
* Order values vary widely ($15–$300+), reflecting segment, tier, and order type differences.
* Menu analysis enables ingredient frequency and cuisine type insights.
* Monthly sales trends highlight seasonal patterns and peak demand periods.

---



