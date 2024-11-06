# LITA_CAPSTONE_PROJECT
---
## ANALYSIS  CUSTOMER DATA
---
### PROJECT TITLE: Customer Segmentation for a Subscription Service 
---
#### PROJECT OVERVIEW
---
This project involves analyzing customer data for a subscription service to identify segments and trends. The goal is to understand customer behavior, track subscription types, and identify key trends in cancellations and renewals. The final deliverable is a Power BI dashboard that presents this analysis.
---
#### Data Sources 
---
This Primary Customer Data was provided by the Incubator Hub for Analysis during LITA Data Analysis Training.
#### Tools Used
---
- Microsoft Exel was used to analyze customer data using pivot tables to find subscription patterns,calculate the average subscription duration and identify the most popular.
  
- Structured Query Language for querying Data

- PowerBI for Data Visualization

  #### Data Exploration
  ---
  The Data was used to explore the Following solution that can give insight into better decision making answering questions like
- Retrieve the total number of customers from each region.
- Find the most popular subscription type by the number of customers.
- Find customers who canceled their subscription within 6 months.
- Calculate the average subscription duration for all customers.
- Find customers with subscriptions longer than 12 months.
- Calculate total revenue by subscription type.
- Find the top 3 regions by subscription cancellations.
- Find the total number of active and canceled subscriptions.


  #### Data Analysis
  *Microsoft Excel*
  
  ![image](https://github.com/user-attachments/assets/af629914-c0e3-46ee-b470-be0f4e444986)


  ![image](https://github.com/user-attachments/assets/4dbe4b3e-a71e-474f-94dc-829c55f8c00f)


  ![image](https://github.com/user-attachments/assets/66be636c-20c7-481e-9e6c-feda0dd42a21)


  ![image](https://github.com/user-attachments/assets/a159e4e3-77fa-4d15-ab8d-1d17a77bc4e7)


  These are the Various Queries executed to answer the questions asked under Data Exploration, in their respective numbers.

*SQL Queries*
- Total number of customers from each region.
  
SELECT Region, COUNT(CustomerID) AS NumberOfCustomers
FROM [dbo].[Customer_data2]
GROUP BY Region;

- Most popular subscription type by number of customers

SELECT TOP 1 SubscriptionType, COUNT(CustomerID) AS CustomerCount
FROM [dbo].[Customer_data2]
GROUP BY SubscriptionType
ORDER BY CustomerCount DESC;

- Customers who canceled their subscription within 6months

SELECT CustomerName
FROM [dbo].[Customer_data2]
WHERE Canceled = 1
AND DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) <= 6;

- Average subscription duration for all customers

SELECT AVG(DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd)) AS AverageSubscriptionDuration
FROM [dbo].[CustomerData]

- Customers with subscription longer than 12 months

SELECT CustomerName
FROM [dbo].[CustomerData]
WHERE DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) > 12;

- Total Revenue by subscription type

SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM [dbo].[Customer_data2]


GROUP BY SubscriptionType;```

- Top 3 regions by subscription cancellation

SELECT TOP 3 Region, COUNT(CustomerID) AS Cancellations
FROM [dbo].[Customer_data2]
WHERE Canceled = 1
GROUP BY Region
ORDER BY Cancellations DESC;

- total number of active and cancelled subscription

SELECT 
    SUM(CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,
    SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CanceledSubscriptions
FROM [dbo].[Customer_data2]

  #### Data Visualization
  
