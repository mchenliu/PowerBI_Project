# Introduction
:mega: This project transforms raw data from AdventureWorks, a global manufacturer of cycling equipment and accessories, into insightful reports and dashboards. The primary objective is to track KPIs, compare regional performance, analyze product trends, and identify high-value customers. This project was completed as part of Maven Analytics' [course](https://www.udemy.com/course/microsoft-power-bi-up-running-with-power-bi-desktop).

:computer: Check out the PowerBI reoport here: [AdventureWorks Report](https://github.com/mchenliu/PowerBI_Project/blob/main/AdventureWorks%20Report.pbix)

# Background
### This Power BI report was created to answer the following key business questions:

1. Were KPIs met compared to the previous month?
2. Which region demonstrates the best performance?
3. What are the product-level trends?
4. Who are the high-value customers?

# Tools I Used
- **PowerBI Desktop:** Business intelligence platform for connecting, modeling, and visualizing data.
- **Query Editor:** Essential tool to for  automated data cleaning and ETL processes.
- **DAX**: Data analysis expressions for calculating and analyzing relational data models.
- **Github:** My go-to for version control and tracking my project progress.

# The Analysis
### 1. Were KPIs met compared to the previous month?
KPIs were divided into three categories: revenue, orders, and returns. To assess KPI performance, I compared metrics for the current and previous month:

**Overall, the KPIs show positive growth. KPI cards were used to visualize these comparisons.**

![KPI](https://github.com/user-attachments/assets/1f8600cd-9e14-4b66-a6e2-fc5e19eca325)

*KPI cards to visualize revenue, orders and returns comparing with last month's data*

**Detailed Findings by Product Category**

- **Accessories:**

  Accessories led sales by order volume. However, a 7.19% revenue decline and a 5.51% drop in order volume raise concerns. The *30 oz Water Bottle* is the most popular item, generating substantial revenue, while the *Sport-100 Helmet*, despite high revenue, has the highest return rate.
![orders_breakdown](https://github.com/user-attachments/assets/33ae99ec-1adb-4554-943d-bedc9b9883bb)*Matrix with top 10 products filtering and condition formatting to drill KPIs further*


- **Bikes:**

  Bikes contribute the most to monthly revenue ($23.6M of $24.9M) and have the highest profit margins. Forecasts predict steady growth, supported by actual data. *Road-750 Black* shows a high return rate (4.23%), which requires attention. The *Mountain-200 series* is the most popular bike, while touring bikes are the least favored.

![KPI](https://github.com/user-attachments/assets/58bb94c6-ea98-4e9c-b046-0fa636e22148)*Matrix with top 10 products filtering and condition formatting to drill KPIs further*


- **Clothing:**

  Clothing has the lowest sales and revenue, but shows a 10.85% increase in order volume and an 11.45% revenue growth compared to last month, indicating a positive trend. The *AWC Logo Cap* leads in sales and revenue with a low return rate of 1.11%, while the *Long-Sleeve Logo Jerseys* have a high return rate (around 3%), warranting further investigation.

![KPI](https://github.com/user-attachments/assets/bec9150b-8544-4e79-a77b-5dce1f73ccf5)
*Matrix with top 10 products filtering and condition formatting to drill KPIs further*


### 2. Which region has the best performance?
Using a total orders table combined with territory hierarchy, I identified top-performing regions by analyzing orders at the country level. *The U.S. and Australia* lead in order volume, with additional contributions from *Europe and Canada*.

![map](https://github.com/user-attachments/assets/b3d278e6-db5a-47cc-acdc-63d5dcc21556)
*Map to visualize order amount by continent/country*

![geo_breakdown_usa](https://github.com/user-attachments/assets/5e1795db-080b-4471-9360-936c5818ef1a)
*Slicers added to make the map interative*

### 3. What are the product-level trends?

Gauge charts with conditional formatting highlight products that fell short of targets, while area charts (with drill-down capability) provide a detailed view of trends across categories.

![Behind target](https://github.com/user-attachments/assets/728af285-83ff-43db-92f8-c95117e4f7b7)
*Gauge charts with conditional formatting to show products behind target*

![area chart](https://github.com/user-attachments/assets/634d97ce-5556-4d6d-bf63-541e7a01c384)
*Area charts with drill mode on*

### 4. Who are the high-value customers?
To find out who are the high-value customers. I combined customer lookup table with total orders table and total revenue table. A Year slicer is also added.

Here are my findings about AdventureWorks' high-value customers:
High-value customers were identified by combining customer lookup, total orders, and total revenue tables, with an additional year slicer for analysis.

**Findings:**

- *Mr. Maurice Shan* is the top revenue contributor ($12,400) with six orders from 2020-2022, followed closely by *Mrs. Janet Munoz* ($12,015).
- Notably, high-value customers from 2020-2021, such as *Mr. Larry Vazquez*, *Mr. Clarence Gao*, *Mr. Aaron Wright*, and *Mrs. Bonnie Nath*, are absent in 2022, potentially indicating shifts in the customer profile or other market changes.
- The *number of unique customers grew* from 2,630 to over 17,000 between 2020 and 2022, although *revenue per customer declined* by $1,000, as shown in a line chart.

![Top customers](https://github.com/user-attachments/assets/5a5d9161-effb-447d-9d0c-3f5bf09f266e)

*Matrix with filter to show top 100 customers*

![Top customers2](https://github.com/user-attachments/assets/c1bc2cb1-50ec-4c21-9639-d7936eebdac1)

*Year filter added to show changes in customers*

- There is an *increase in number of unique customers and decrease in revenue per customer* between 2020 and 2022. The number of customers increased from 2,630 to over 17,000 while revenue per customer dropped by $1,000. The line chart is also showing a decreasing trend.
![Revenue per customer](https://github.com/user-attachments/assets/84692b0f-edf5-4720-91cb-a7a3585e0fe3)
*Line chart showing decreasing trend in revenue per customer*

# What I Learned
### Insights
### Closing Thoughts
