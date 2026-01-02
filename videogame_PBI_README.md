# Global Video Game Market Analysis — Power BI Dashboard

## Project Overview

This project presents a detailed analysis of the global video game market using Power BI. The data visualizations and KPIs offer insights into key metrics such as sales trends, platform performance, publisher success, genre preferences, and regional differences in gaming. The dataset used is sourced from the **Kaggle Video Game Sales with Ratings dataset**.

---

## Dataset Used

The dataset used in this project is the **Video Game Sales with Ratings** dataset available on Kaggle. It contains detailed information about video game sales across different platforms, regions, genres, publishers, and ratings.

You can download the dataset from the following link:

* **Video Game Sales with Ratings Dataset on Kaggle**: [https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)

### Key Columns in the Dataset:

* **Name**: Name of the game
* **Platform**: Platform on which the game was released (e.g., PlayStation, Xbox)
* **Year_of_Release**: Year the game was released
* **Genre**: Game genre (e.g., Action, Adventure, RPG)
* **Publisher**: Publisher of the game
* **NA_Sales**: Sales in North America (in millions)
* **EU_Sales**: Sales in Europe (in millions)
* **JP_Sales**: Sales in Japan (in millions)
* **Global_Sales**: Total sales across all regions (in millions)
* **User_Score**: User rating of the game
* **Critic_Score**: Critic rating of the game

---

## Installation Instructions

1. **Download Power BI Desktop**: [Power BI Download](https://powerbi.microsoft.com/)
2. **Download Dataset**: Download the dataset from Kaggle: [Video Game Sales with Ratings Dataset](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings).
3. **Load Data**: Open Power BI Desktop and import the dataset.

   * **Home → Get Data → Excel** (if dataset is in .xlsx) or **CSV** (for CSV format).
4. **Refresh Data**: Make sure the dataset loads properly and is cleaned in the **Data** view.

---

## Key Pages and Insights

### 1. KPI Summary (Executive Overview)

Provides an overall snapshot of global video game sales, the number of active platforms and publishers, and regional sales distribution.

### 2. Platform Dominance

Shows which platforms dominate global sales and trends over time.

### 3. Console Lifecycle

Tracks how long platforms remain successful and their peak sales years.

### 4. Genre Trends

Analyzes the rise and fall of game genres and how they impact sales.

### 5. Publisher Performance

Compares publishers’ performance across regions.

### 6. Regional Preferences

Explores how gaming preferences vary across different regions.

---

## DAX Measures Used

Here are the DAX measures used in the Power BI project:

### 1. Total Sales

```DAX
Total Sales = 
SUM ( vgsales[Global_Sales] )
```

### 2. Active Platforms

```DAX
Active Platforms = 
DISTINCTCOUNT ( vgsales[Platform] )
```

### 3. Active Publishers

```DAX
Active Publishers = 
DISTINCTCOUNT ( vgsales[Publisher] )
```

### 4. Active Genres

```DAX
Active Genres = 
DISTINCTCOUNT ( vgsales[Genre] )
```

### 5. Platform Market Share %

```DAX
Platform Market Share % = 
DIVIDE (
    [Total Sales],
    CALCULATE ( [Total Sales], ALL ( vgsales[Platform] ) )
)
```

### 6. Platform Launch Year

```DAX
Platform Launch Year = 
MIN ( vgsales[Year_of_Release] )
```

### 7. Platform Peak Sales

```DAX
Platform Peak Sales = 
MAXX (
    VALUES ( vgsales[Year_of_Release] ),
    [Total Sales]
)
```

### 8. Platform Peak Year

```DAX
Platform Peak Year = 
VAR T =
    ADDCOLUMNS (
        VALUES ( vgsales[Year_of_Release] ),
        "Sales", [Total Sales]
    )
RETURN
MAXX ( TOPN ( 1, T, [Sales], DESC ), vgsales[Year_of_Release] )
```

### 9. YoY Growth %

```DAX
YoY Growth % = 
VAR PrevYear = 
    CALCULATE (
        [Total Sales], 
        vgsales[Year_of_Release] = MAX ( vgsales[Year_of_Release] ) - 1
    )
RETURN 
DIVIDE ( [Total Sales] - PrevYear, PrevYear )
```

---

## Visuals Used in the Dashboard

### Page 1: KPI Summary

* **KPI Cards**:

  * Total Sales
  * Active Platforms
  * Active Publishers
* **Line Chart**: Sales trend over years
* **Donut Chart**: Regional sales share (NA, EU, JP)

### Page 2: Platform Dominance

* **Bar Chart**: Platform vs. Total Sales
* **Line Chart**: Platform sales trend over time
* **Platform Market Share** (optional table)

### Page 3: Console Lifecycle

* **Slicer**: Platform selection
* **Line Chart**: Sales trend per platform
* **KPIs**: Platform Launch Year, Peak Sales, Peak Year

### Page 4: Genre Trends

* **Area Chart**: Genre sales trend over time
* **Bar Chart**: Year-on-Year growth by genre

### Page 5: Publisher Performance

* **Bar Chart**: Total sales by publisher
* **Matrix**: Sales by publisher across regions (NA, EU, JP)

### Page 6: Regional Preferences

* **Stacked Bar Chart**: Genre sales by region
* **Heatmap**: Sales by platform across regions (conditional formatting)

---

## Conclusion

This dashboard provides actionable insights into the video game industry, offering a deep dive into platform, publisher, and genre trends. By understanding regional preferences and tracking lifecycle trends, businesses can optimize their strategies for game releases and marketing.

---

### Future Improvements

* Add additional data on **user reviews** and **ratings** to further enhance the analysis.
* **Forecast sales trends** based on historical data to predict future market performance.

---
