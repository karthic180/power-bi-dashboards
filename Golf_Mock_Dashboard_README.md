
#  Golf Performance Dashboard – Power BI

##  Project Overview

This project is an **interactive Power BI dashboard** focused on analyzing **golf player performance** using statistical and round-level data.  
The dashboard helps visualize **scoring trends, player comparisons, and course difficulty**, enabling deeper insights into competitive performance.

The goal is to **identify strengths, highlight improvement areas, and compare player performance across rounds and courses** using clear, intuitive visuals.

---

##  Key Analysis Areas

- Player scoring trends over time  
- Player-to-player performance comparison  
- Course difficulty and scoring impact  
- Round-by-round performance breakdown  
- Performance consistency analysis  

---

##  Dataset

**Source:** Public golf performance dataset (mock / sample data used for portfolio demonstration)
https://support.minitab.com/en-us/datasets/time-series-data-sets/golf-driver-sales/

> **Note:** This dashboard is built for analytical demonstration purposes and does not represent official PGA or professional tour data.

---

##  Dashboard Pages & Features

### Page 1: KPI Overview
- Average Score  
- Best Round Score  
- Worst Round Score  
- Total Rounds Played  
- Card visuals for quick performance snapshot  

---

### Page 2: Player Performance Trends
- Scoring trends across rounds  
- Performance consistency over time  
- **Visuals:** Line charts, clustered column charts  
- **Slicers:** Player Name, Tournament, Course  

---

### Page 3: Player Comparison
- Side-by-side comparison of selected players  
- Average score, birdies, pars, bogeys comparison  
- **Visuals:** Clustered bar and column charts  
- Dynamic player selection using slicers  

---

### Page 4: Course Difficulty Analysis
- Average score by course  
- Course difficulty comparison  
- Score distribution by course  
- **Visuals:** Bar charts, column charts  

---

### Page 5: Round-Level Breakdown
- Hole-by-hole or round-by-round scoring analysis  
- Identification of high-variance rounds  
- **Visuals:** Table and column visuals  
- Interactive filtering for deep-dive analysis  

---

##  Measures & Calculations (Examples)

### DAX Measures

```DAX
Total Rounds =
COUNT('golf_data'[RoundID])

Average Score =
AVERAGE('golf_data'[Score])

Best Score =
MIN('golf_data'[Score])

Worst Score =
MAX('golf_data'[Score])
````

> Additional measures are used for player comparisons, scoring categories, and course-level analysis.

---

##  Setup Instructions

1. Open **Power BI Desktop**
2. Import the golf dataset using **Get Data**
3. Perform data cleaning and transformations in **Power Query**
4. Create required DAX measures for KPIs and comparisons
5. Build visuals page by page as described
6. Apply consistent formatting:

   * Conditional colors for performance levels
   * Data labels enabled
   * Slicers for interactivity

---

##  Key Dashboard Insights

* Player performance varies significantly across courses
* Scoring trends help identify consistency and improvement opportunities
* Course difficulty plays a major role in overall scoring outcomes
* Player comparison visuals highlight competitive strengths and weaknesses

---

##  Technologies Used

* Power BI Desktop
* Power Query (M Language)
* DAX Measures
* Microsoft Excel (data preparation)

---

##  License

This project is created for **educational and portfolio purposes only**.
