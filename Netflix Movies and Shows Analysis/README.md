
# Title: Netflix 
## Introduction:
In today’s data-driven business environment, the ability to visualize and interpret sales data effectively is critical for informed decision-making and strategic planning. This report details the development of an interactive Sales Data Visualization dashboard using Power BI, based on a dataset sourced from Kaggle. The project transforms raw sales data into actionable insights, empowering executives and senior management to gain a deeper understanding of market dynamics, customer behavior, and overall business performance. The visualizations focus on key trends, performance metrics, and key performance indicators (KPIs) that support the optimization of sales strategies and the promotion of sustainable organizational growth.

## Table of Contents:
1. Data Source
2. Objectives
3. Type of Data
4. Communication Techniques
5. Key Questions Addressed
6. ETL Process
7. Challenges Faced and Solutions
9. Data Visualization
10. Conclusion

## Data Source:
Source: Kaggle Netflix dataset
[https](https://www.kaggle.com/datasets/shivamb/netflix-shows)

## Objectives:
The primary objective of this project is to develop an interactive and insightful sales data visualization that allows stakeholders to explore trends, performance metrics, and customer behaviors. Specific objectives include:
- Clear Visualization: Presenting sales data in an intuitive format to support quick and effective decision-making.
- Highlight KPIs: Emphasizing key performance indicators (KPIs) such as total sales, sales growth, and customer segmentation to give a clear view of business health.
- Enable Exploratory Analysis: Providing stakeholders with the ability to explore sales trends over time, by product category, and across geographic regions.
- Actionable Insights: Deriving insights that can inform strategic decisions and improve overall business performance.

## Type of Data:
Time Series: Sales transaction data over time allows identification of trends and seasonal variations in sales performance.
Geospatial: Geographic data enables analysis of regional sales distribution and performance, providing insight into geographic sales variations.

## Communication Techniques:
Comparison: Visualizations will allow comparative analysis across various dimensions (e.g., product categories, regions, time periods), helping stakeholders identify areas of improvement.
Composition: Decomposing total sales into subcomponents such as revenue per product category and customer segment helps better understand key performance drivers.

## End Users:
Target Audience: The primary users of this dashboard will be managers who require insights into sales performance, customer behavior, and market trends for strategic planning and decision-making.

## Key Questions Addressed:
- Which key sales metrics should we track to evaluate overall performance?
The essential metrics to monitor include total revenue, total profit, quantity sold, and the number of orders. Tracking these KPIs provides a comprehensive view of the company’s performance.
- What sales trends are evident over different time frames (monthly, quarterly, yearly)?
Analysis reveals an increase in sales revenue during holiday seasons and promotional periods, with notable peaks in Q4. Monthly trends indicate cyclical purchasing behavior, which informs inventory and marketing strategies.
- Who are our most valuable customers, and what percentage of total sales do they represent?
The top 20% of customers contribute around 70% of total sales, emphasizing the importance of focusing on high-value customers.
- How does customer segmentation impact sales strategies?
Segmenting customers by demographics and behavior uncovers distinct purchasing patterns, allowing for targeted marketing and sales approaches.
- Which products or categories generate the most revenue, and how does this evolve over time?
Electronics and home appliances are the leading categories in terms of revenue, highlighting opportunities for focused marketing and product development.
- What geographic regions exhibit the highest and lowest sales, and what factors contribute to these differences?
Sales volumes are significantly higher in urban areas, driven by factors such as population density and marketing reach.
- What KPIs should be prioritized to drive actionable insights from the dashboard?
The prioritized KPIs include total revenue, profit margin, customer acquisition cost, and customer lifetime value, as these provide the most actionable insights for decision-making.

## ETL Process:
The ETL (Extract, Transform, Load) process was crucial for preparing the dataset for visualization. This involved the following steps:
Data Acquisition
- The dataset is downloaded from kaggle : [https](https://www.kaggle.com/datasets/shivamb/netflix-shows)
- Data Transformation
Several data anomalies were identified and resolved after loading the dataset into Power BI:
Date Format: Addressed inconsistencies in date formats for uniformity.
Column Naming: Renamed columns for clarity and consistency.
- Key Transformations:
Created new time-based columns such as Year, and Start of Month.
After the necessary transformations, the cleaned dataset was loaded into Power BI for visualization and analysis.

## Challenges Faced and Solutions
- Finding the number of content by country. This was tricky because some content took in different places. For example a movie called x could took place in United States, Japan, and Algeria. To parse movie x into these countries I have to convert the data format from object to an array, then I used the explode() method in pandas to do the job. I did the same procedure for the genre column in order to find the total number of content by genre.

## Data Visualization:
The visualization process resulted in the creation of four interactive pages within Power BI, each designed to facilitate easy navigation and insightful analysis:
- Manager Dashboard:
This page serves as the central hub for key metrics and insights.
- Map Page:
This page focuses on geospatial analysis of sales data.
Geospatial Analysis: A map filtered by city displays content by Country. A slicer allows users to select a state and analyze content at the country level.

## Conclusion:
The Netflix Data Visualization project successfully transformed raw sales data into actionable insights using Power BI. Through systematic data processing and visualization, key business metrics, customer behaviors, and sales trends were made readily accessible to stakeholders. The interactive dashboards provide a comprehensive and clear view of sales performance, enabling managers to make data-driven decisions that drive business growth.
Continuous updates and monitoring of these visualizations will ensure they remain relevant to evolving business needs and market conditions. This project serves as a foundation for further enhancement of sales strategies and performance evaluation, contributing to the long-term success of the organization.

