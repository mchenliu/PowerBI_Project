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

```DAX
Total Revenue = 
    SUMX(
        'Sales Data',
        'Sales Data'[OrderQuantity] * 
        RELATED(
            'Product Lookup'[ProductPrice])
        )

Previous Month Revenue = 
CALCULATE(
    [Total Revenue],
    DATEADD('Calendar Lookup'[Date],
    -1,
    MONTH)
)

Total Orders = 
DISTINCTCOUNT(
    'Sales Data'[OrderNumber]
)

Previous Month Orders = 
CALCULATE(
    [Total Orders],
    DATEADD(
        'Calendar Lookup'[Date],
        -1,
        MONTH))

Total Returns = 
COUNT('Returns Data'[ReturnQuantity]
)

Previous Month Returns = 
CALCULATE(
    [Total Returns],
    DATEADD(
        'Calendar Lookup'[Date],
        -1,
        MONTH))

Return rate = 
CALCULATE(
   [Quantity Returned]/[Quantity Sold]
)
```
*DAX for measure tables*


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

Product-level trends were identified by comparing target and sales metrics with product name slicer.

- **Product Sales Analysis:**

AdventureWorks sets a 10% growth target for orders, revenue, and profit. The *30 oz Water Bottle* remains the most popular accessory, but all sales metrics are currently falling short of the target. In the bikes category, the *Mountain-200 series* leads as the best-selling product. Within this series, the *Silver 38 and Black 42* models are top performers, though the *Silver 42* model is lagging behind expectations. *AWC Logo Cap* meets all targets and despite the high return rate, *Long-Sleeve Logo Jerseys* are also meeting all targets.
```DAX
Order Target = 
[Previous Month Orders] *1.1

Revenue Target = 
[Previous Month Revenue] *1.1

Profit Target = 
[Previous Month Profit] *1.1

Adjusted Profit = 
[Adjusted Revenue] - [Total Cost]
```
*DAX for measure tables*

![water_bottle](https://github.com/user-attachments/assets/2dc06d68-22cf-4d86-9fec-f7a96435e79c)
![200-black](https://github.com/user-attachments/assets/e65d2b91-6065-4982-a495-202cb0dc6186)
![200-silver](https://github.com/user-attachments/assets/93cca50b-bdb5-46dc-9c37-d6d105d8ff1c)
![silver 42](https://github.com/user-attachments/assets/abaa0f2b-1853-4d42-bad5-bcc8add8fc84)
![awc](https://github.com/user-attachments/assets/0d5812e7-e0b5-4bd5-8d3f-d51231b48eeb)
![Jersey](https://github.com/user-attachments/assets/ddee1d80-5624-48d3-b966-de3b2f79e7b7)

*Gauge charts with conditional formatting highlight how each product performs relative to its target*

- **Product Profit Estimation:**

The area chart with an adjustable price slicer and date hierarchy allow management to analyze how price changes impact product profitability, aiding in decisions around promotions and pricing strategies.

![Area chart](https://github.com/user-attachments/assets/f57de69d-9121-4f22-aaec-6ae1ff61422c)
*Area chart to visulize profit changes on price adjustments*

- **Product Metrics Analysis:**

The area chart, combined with a product metric slicer and date hierarchy, provides management with insights into specific items based on selected metrics. For example, the *30 oz Water Bottle* shows steady profit from 2021 to 2022, with a notable spike in returns on June 1, 2022.
![Profit](https://github.com/user-attachments/assets/51da72cb-372b-41f9-b71e-1effb8a97d0a)
![return](https://github.com/user-attachments/assets/ca68b671-7645-40fc-97c0-008cb168ec14)
*Area chart to visulize product metrics*

### 4. Who are the high-value customers?
High-value customers were identified by combining customer lookup, total orders, and total revenue tables, with an additional year slicer for analysis.

**Findings:**

- *Mr. Maurice Shan* is the top revenue contributor ($12,400) with six orders from 2020-2022, followed closely by *Mrs. Janet Munoz* ($12,015).
- Notably, high-value customers from 2020-2021, such as *Mr. Larry Vazquez*, *Mr. Clarence Gao*, *Mr. Aaron Wright*, and *Mrs. Bonnie Nath*, are absent in 2022, potentially indicating shifts in the customer profile or other market changes.
- The *number of unique customers grew* from 2,630 to over 17,000 between 2020 and 2022, although *revenue per customer declined* by $1,000, as shown in a line chart.
  
```DAX
Total Customers = 
DISTINCTCOUNT(
    'Sales Data'[CustomerKey]
)

Average Revenue Per Customer = 
DIVIDE(
    [Total Revenue],
    [Total Customers]
)

Full Name (Customer Detail) = 
IF(
    HASONEVALUE(
        'Customer Lookup'[CustomerKey]),
    MAX(
        'Customer Lookup'[Full Name]
    ),
    "Multiple Customers")
```
*DAX for measure tables*

![Top customers](https://github.com/user-attachments/assets/5a5d9161-effb-447d-9d0c-3f5bf09f266e)

*Matrix with filter to show top 100 customers*

![Top customers2](https://github.com/user-attachments/assets/c1bc2cb1-50ec-4c21-9639-d7936eebdac1)

*Year filter added to show changes in customers*

![Revenue per customer](https://github.com/user-attachments/assets/84692b0f-edf5-4720-91cb-a7a3585e0fe3)
*Line chart showing decreasing trend in revenue per customer*

# What I Learned
- :thermometer: **Technical Skills:** Although the raw data provided by the course wasn’t as "dirty" as real-world data, I learned to process data using the Query Editor, establish relationships between tables, create hierarchies, use DAX to build measure tables, and visualize insights through various chart types.

- :thought_balloon: **Ask These Key Questions:** Before starting a project, I learned to ask three essential questions: What type of data am I working with? What message do I want to convey through this report? Who are the end users, and what do they need from this report?

- :star: **Storytelling with Data:** Effective storytelling involves three steps: Why is this analysis important? What insights does the data reveal? What actions should be taken based on these insights?

- :zap: **Dashboard Design:** A well-designed dashboard should serve a clear purpose for a specific audience, using concise and relevant metrics and visuals that offer an intuitive user experience. Presenting information as clearly as possible should always be a priority.


### Insights
1. Were KPIs met compared to the previous month?
    Overall, KPIs were achieved, supported primarily by steady revenue from bike sales. Although revenue and orders from clothing remain the smallest, they show a steady growth trend. However, management should pay attention to a declining trend in accessory sales.
    
2. Which region demonstrates the best performance?
   The majority of orders originate from *the U.S. and Australia*, indicating strong performance in these regions.
3. What are the product-level trends?
    AdventureWorks has set a 10% growth target across products. While some high-revenue items, such as the *30 oz Water Bottle*, are falling short of targets, they continue to show steady profit growth. Other top-selling products, including the *Mountain-200 Black*, *Mountain-200 Silver*, and *AWC Logo Cap*, are surpassing their targets. Despite a high return rate, the *Long-Sleeve Logo Jersey* has also met its targets.

4. Who are the high-value customers?
    *Mr. Maurice Shan* and *Mrs. Janet Munoz* were the top revenue contributors from 2020 to 2022. Notably, there was a shift in high-value customer profiles after 2021, indicating potential changes in the market. Additionally, there is a growing trend in the number of unique customers, though revenue per customer has been declining from 2020 to 2022.
