# LITA Capstone Project 
## Project 1- Sales Performance Analysis for LITA Store.
[Business Overview](#business-overview)

[Rationale of the project](#rationale-of-the-project)

[Aim of the Project](#aim-of-the-project)

[Data Description](#data-description)

[Scope of the project](#scope-of-the-project)

[Tools Used](#tools-used)

[SQL Queries Used](#sql-queries-used)

[Insights](#insights)

[Recommendations](#recommendations)

[Conclusion](#conclusion)


----

## Business Overview

This project focuses on analyzing the sales performance of a retail store. The aim is to identify top-selling products, assess regional contributions to revenue, and track monthly sales trends to improve business strategies.

## Rationale of the Project

Understanding sales performance helps the business optimize inventory, target high-performing regions, and identify seasonal trends. By identifying these key drivers of revenue, the business can make data-driven decisions to improve overall sales and profitability.

## Aim of the Project

The goal is to create an interactive Power BI dashboard that highlights top products, regional sales distribution, and monthly sales trends to support strategic decisions in inventory and marketing.

## Data Description

Sales Performance Data: Includes data on products sold (quantity and revenue), regional sales distribution, and monthly trends.

## Scope of the Project

1. Sales Overview: Total quantity sold and total revenue.


2. Top Products: Top-selling products by quantity and revenue.


3. Regional Performance: Sales contributions by region and monthly sales trends.



## Tools Used

- Excel: Initial data exploration and generating summary statistics like total sales by product, region, and month.

- SQL: Querying the dataset to extract insights on top products, monthly sales, and regional contributions.

- Power BI: Creating an interactive dashboard that visualizes the sales overview, top-performing products, and regional breakdowns.


## SQL Queries Used

1. Total Sales by Product Category: SELECT ProductCategory, SUM(TotalSales) FROM Sales GROUP BY ProductCategory


2. Sales Transactions by Region: SELECT Region, COUNT(TransactionID) FROM Sales GROUP BY Region


3. Highest-Selling Product by Total Sales: SELECT ProductName, SUM(TotalSales) AS Revenue FROM Sales GROUP BY ProductName ORDER BY Revenue DESC LIMIT 1


4. Total Revenue per Product: SELECT ProductName, SUM(TotalSales) FROM Sales GROUP BY ProductName


5. Monthly Sales Totals: SELECT MONTH(OrderDate) AS Month, SUM(TotalSales) FROM Sales GROUP BY Month


6. Top 5 Customers by Purchase Amount: SELECT CustomerID, SUM(TotalSales) FROM Sales GROUP BY CustomerID ORDER BY SUM(TotalSales) DESC LIMIT 5


7. Sales Contribution by Region: SELECT Region, (SUM(TotalSales) / (SELECT SUM(TotalSales) FROM Sales)) * 100 AS Percentage FROM Sales GROUP BY Region


8. Products with No Sales in Last Quarter: SELECT ProductName FROM Sales WHERE OrderDate < DATE_SUB(CURDATE(), INTERVAL 3 MONTH)



## Insights

1. Top Products by Quantity and Revenue: Hats and shoes are the top-selling items, indicating high customer demand.


2. Regional Performance: The West region has the highest sales, suggesting a focus area for marketing.


3. Monthly Sales Trends: Certain months show peak sales, indicating potential seasonality that the business can leverage.



## Recommendations

1. Inventory Management: Stock popular items like hats and shoes to meet demand.


2. Regional Marketing Strategy: Focus marketing efforts on high-demand regions, especially the West.


3. Seasonal Promotions: Run promotions during low-performing months to boost revenue.

## Conclusion
The insights gained from the sales analysis can guide inventory management, regional marketing strategies, and seasonal promotion planning. By focusing on top products and high-demand regions, the business can increase efficiency, reduce stockouts, and potentially boost overall revenue.



------ 

## Project 2- Customer Segmentation Analysis for LITA Subscription Service

[Business Overview](#business-overview)

[Rationale of the project](#rationale-of-the-project)

[Aim of the Project](#aim-of-the-project)

[Data Description](#data-description)

[Scope of the project](#scope-of-the-project)

[Tools Used](#tools-used)

[SQL Queries Used](#sql-queries-used)

[Insights](#insights)

[Recommendations](#recommendations)

[Conclusion](#conclusion)


## Business Overview

This project analyzes customer data for a subscription service to understand customer behavior, track subscription patterns, and identify trends in cancellations and renewals. The goal is to improve customer retention and optimize marketing efforts.

## Rationale of the Project

By analyzing customer segmentation, the business can identify key trends that impact churn and customer loyalty. This allows for targeted retention strategies, tailored promotions, and a better understanding of customer demographics.

## Aim of the Project

The objective is to develop a Power BI dashboard that provides insights into customer segments, subscription types, cancellation trends, and regional distribution of customers to support retention and growth strategies.

## Data Description

Customer Segmentation Data: Contains customer demographics, subscription types, regions, cancellation status, and subscription duration.

## Scope of the Project

1. Customer Segmentation Overview: Insights on subscription types, customer distribution by region, and churn rate.


2. Cancellation Trends: Analysis of cancellation rates by region and subscription type.


3. Subscription Patterns: Insights on popular subscription types and average duration.


## Tools Used

- Excel: Used for calculating subscription statistics, such as average duration and most popular subscription types.

- SQL: Employed to query customer data for insights on subscription types, cancellations, and regional patterns.

- Power BI: Used to build an interactive dashboard that visualizes customer segments, subscription trends, and cancellations.


## SQL Queries Used

1. Total Number of Customers by Region: SELECT Region, COUNT(CustomerID) FROM Customers GROUP BY Region


2. Most Popular Subscription Type: SELECT SubscriptionType, COUNT(CustomerID) FROM Customers GROUP BY SubscriptionType ORDER BY COUNT(CustomerID) DESC LIMIT 1


3. Customers Who Canceled within 6 Months: SELECT CustomerID FROM Customers WHERE Canceled = TRUE AND SubscriptionDuration <= 6


4. Average Subscription Duration: SELECT AVG(SubscriptionDuration) FROM Customers


5. Customers with Subscriptions Longer than 12 Months: SELECT CustomerID FROM Customers WHERE SubscriptionDuration > 12


6. Total Revenue by Subscription Type: SELECT SubscriptionType, SUM(Revenue) FROM Customers GROUP BY SubscriptionType


7. Top 3 Regions by Subscription Cancellations: SELECT Region, COUNT(CustomerID) FROM Customers WHERE Canceled = TRUE GROUP BY Region ORDER BY COUNT(CustomerID) DESC LIMIT 3


8. Total Number of Active and Canceled Subscriptions: SELECT Canceled, COUNT(CustomerID) FROM Customers GROUP BY Canceled



## Insights

1. Most Popular Subscription Type: Basic subscriptions are most common, indicating a preference for entry-level options.


2. Churn Rate: Moderate churn rate, suggesting room for retention strategy improvements.


3. Regional Analysis: The West and North regions have high subscription counts, but North also shows a higher cancellation rate.



## Recommendations

1. Retention Strategy for Basic Subscribers: Develop targeted retention strategies for Basic subscribers to reduce churn.


2. Cancellation Reduction Strategy: Address issues in regions with high cancellations, such as the North, by analyzing customer feedback.


3. Loyalty Program for Long-Term Subscribers: Implement loyalty rewards for customers who maintain subscriptions beyond 12 months to encourage long-term retention.


## Conclusion
This analysis provides actionable insights to enhance customer retention through targeted retention strategies, customer feedback analysis, and loyalty programs. By addressing regional cancellation trends and catering to the demand for entry-level subscriptions, the business can strengthen customer relationships and reduce churn.


---




