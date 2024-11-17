
# Introduction
:mega: This project transform raw comapny data from a AdventureWorks, a global manufacturing company that produces cycling equipment and accessories into reports and dashboards to provide more management insights. The objective is to track KPIs, compare regional performance, analyze product-level trends and identify high-value customers.

:computer: Check out the PowerBI reoport here: [AdventureWorks Report](/AdventureWorks Report)

# Background
### The questions I wanted to answer through my PowerBI report were:

Below are the questions I want to answer in my project:

1. Were KPIs met (comparing with previous month)?
2. Which region has the best performance?
3. What are the product-level trends?
4. Who are the high-value customers?

# Tools I Used
- **PowerBI Desktop:**
- **Query Editor:** Essential tool to for  automate data cleaning and ETL process.
- **DAX**: analyzing relational data models.
- **Github:**

# The Analysis
### 1. Comparing with the previous month, were KPIs met?
KPIs are split into 3 categories- revenue, orders and returns. To identify if KPIs are met, I first created current month and previous measure tables on these 3 aspects. Then inserted KPI cards to the canvas. 

Here's an overall view of the KPIs comapring with previous month:
- **Revenue:** a 3.31% increase from $1.77 million to $1.83 million.
- **Orders:** a 0.88% drecrease from 2,165 to 2,146.
- **Returns:** a 1.78% decrease from 169 to 166.
Overall KPIs are met and numbers seem positive.
![KPI](https://github.com/user-attachments/assets/1f8600cd-9e14-4b66-a6e2-fc5e19eca325)

*KPI cards to visualize revenue, orders and returns comparing with last month's data*

I breakdown orders further by category and here are my findings:

- **Accessories:** 
    - Accessories dominants sales by order amount however the 7.19% decrease in revenue and 5.51% decrease in order amount is alarming.
    - The most popular accessory is *30 oz Water Bottle* and it brings a good amount of revenue. 
    - *Sport-100 Helmets* generates great revenue however it also has the highest return rate.

![orders_breakdown](https://github.com/user-attachments/assets/33ae99ec-1adb-4554-943d-bedc9b9883bb)*Matrix with top 10 products filtering and condition formatting to drill KPIs further*

- **Bikes:** 
    - Bikes sale contributes to most of the monthly revenue ($23.6M/$24.9M) It also has the highest profit among all 3 categories. Forcast is showing a steady growth in revenue and so is actual data. Growth in both revenue and order amount shows a promising sign. Meanwhile *Road-750 Black* is showing a high return rate of 4.23% that should be looked into.
    - The *Mountain-200* series are the most popular bikes. It's a road bike and the least favoured bike type is touring bikes.

![KPI](https://github.com/user-attachments/assets/58bb94c6-ea98-4e9c-b046-0fa636e22148)*Matrix with top 10 products filtering and condition formatting to drill KPIs further*

- **Clothing:** 
    - Clothing has the least sale among all 3 categories and generates the least income. However, there is a slow growth in revenue based on forecast and there is a 10.85% increase in order amount and a 11.45% increase in revenue comparing to last month. This shows a positive sign for the clothing category.
    - The *AWC Logo Cap* is most favoured by consumers. It leads order amount and revenue in clothing category with a very low return rate of 1.11%. 
    - *Long-Sleeve Logo Jerseys* in all sizes have high return rates (around 3%). This should raise a flag for review.

![KPI](https://github.com/user-attachments/assets/bec9150b-8544-4e79-a77b-5dce1f73ccf5)*Matrix with top 10 products filtering and condition formatting to drill KPIs further*


### 2. Which region has the best performance?
To understand which region has the best performance, I used total orders measure table combining with terriotry hierarchy to drill down to country leve.
![map](https://github.com/user-attachments/assets/b3d278e6-db5a-47cc-acdc-63d5dcc21556)
*Inveractive map to visualize order amount by continent*

![geo_breakdown_usa](https://github.com/user-attachments/assets/5e1795db-080b-4471-9360-936c5818ef1a)
*Hover to find total orders by country*


### 3. What are the product-level trends?
### 4. Who are the high-value customers?
# What I Learned
### Insights
### Closing Thoughts
