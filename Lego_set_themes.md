# **LEGO Sets & Themes Dashboard**

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=flat\&logo=powerbi\&logoColor=black)
![Domain](https://img.shields.io/badge/Domain-Consumer%20Products-E91E63?style=flat)
![Analytics](https://img.shields.io/badge/Analytics-Product%20Portfolio-0288D1?style=flat)

## **Overview**

This dashboard analyzes **LEGO set releases** over the years, focusing on **themes**, **release trends**, and **set complexity**. The dataset includes information about each LEGO set, such as its release year, theme, number of pieces, and overall popularity.

By leveraging **Power BI**, this dashboard enables a detailed examination of LEGO's historical performance across multiple themes, providing valuable insights for enthusiasts, collectors, and business analysts interested in the LEGO market.

---

## **Key Features**

* **Release Trends**: Visualize the trend of LEGO sets released by year, helping to identify patterns in set creation and theme popularity.
* **Theme Analysis**: Compare the number of sets released across various themes, providing insights into the most popular and lucrative themes.
* **Set Complexity**: Analyze the average number of pieces per set across different themes, revealing the complexity of each LEGO set.
* **Year-on-Year Growth**: Examine the growth in the number of sets released each year and determine which themes have driven the most releases.

---

## **Dashboard Screenshots**

![LEGO Sets Dashboard Screenshot](https://github.com/karthic180/power-bi-dashboards/blob/main/lego%20set%20themes%20dash.pdf)

---

## **Key Insights**

* **Strong Growth in Set Releases**: LEGO has experienced significant growth in the number of sets released each year, with certain periods seeing dramatic increases in set creation.
* **Top Themes**: Themes like **Star Wars**, **Harry Potter**, and **Technic** have consistently produced the most sets, driving substantial interest in those areas.
* **Complexity Trends**: The average number of pieces per set has increased over time, reflecting changing consumer demands for more detailed and larger sets.
* **Strategic Focus**: Popular themes provide strategic opportunities for merchandising and future set designs.

---

## **Key Measures / DAX**

Here are some of the key DAX measures used in the dashboard to generate insights:

```DAX
Total Sets = COUNT(LEGO[SetID])
Total Themes = DISTINCTCOUNT(LEGO[Theme])
Sets per Year = CALCULATE([Total Sets], YEAR(LEGO[ReleaseYear]))
Top Theme = RANKX(ALL(LEGO[Theme]), [Total Sets], , DESC)
Average Pieces per Set = AVERAGE(LEGO[NumPieces])
```

* **Total Sets**: Counts the total number of LEGO sets in the dataset.
* **Total Themes**: Returns the number of unique themes in the dataset.
* **Sets per Year**: Calculates the number of LEGO sets released each year.
* **Top Theme**: Ranks themes by the total number of sets released.
* **Average Pieces per Set**: Calculates the average number of pieces in each set across all LEGO sets.

---

## **Business Questions Answered**

* **Which LEGO themes generate the most sets and popularity?**

  * Identify which themes have consistently driven the most product releases.

* **How has the volume of LEGO set releases changed over time?**

  * Track the number of LEGO sets released each year and identify any significant spikes or declines.

* **Which themes are top-performing historically and currently?**

  * Identify long-term and recent high-performing themes that continue to attract consumer interest.

---

## **Dataset Information**

The dashboard uses the **LEGO Sets & Themes Dataset** available on Kaggle, which contains detailed information about LEGO sets, including:

* Set ID
* Set Name
* Release Year
* Theme
* Number of Pieces
* Set Complexity

**[View Dataset on Kaggle](https://www.kaggle.com/datasets/jkraak/lego-sets-and-themes-database)**

---

## **How to Use the Dashboard**

1. **Download Power BI**: To interact with the dashboard, you need to have **Power BI Desktop** installed on your system.

   * [Download Power BI Desktop](https://powerbi.microsoft.com/downloads/)

2. **Import the Dataset**: Download the dataset from Kaggle and import it into Power BI.

3. **Explore Visualizations**: Use the interactive filters and visuals in the dashboard to explore different aspects of LEGO set releases, themes, and trends.

4. **Customize**: You can customize the dashboard by adding more measures or adjusting visuals based on your specific interests or requirements.


## **License**

This repository is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more details. Timeline of sets released (1950–2020s)  
- Theme popularity breakdown  
- Parts distribution (min, max, average)  
- Drill‑down filters by year, theme, and set size  

