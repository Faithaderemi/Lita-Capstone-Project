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
  **Microsoft Excel**
  
  ![image](https://github.com/user-attachments/assets/af629914-c0e3-46ee-b470-be0f4e444986)


  ![image](https://github.com/user-attachments/assets/4dbe4b3e-a71e-474f-94dc-829c55f8c00f)


  ![image](https://github.com/user-attachments/assets/66be636c-20c7-481e-9e6c-feda0dd42a21)


  ![image](https://github.com/user-attachments/assets/a159e4e3-77fa-4d15-ab8d-1d17a77bc4e7)


  ![image](https://github.com/user-attachments/assets/a19487cd-5c39-4aa3-b988-da7503e9adf6)


  ![image](https://github.com/user-attachments/assets/5967d0ea-9181-448a-89c8-8d9aa79b6c34)


  ![image](https://github.com/user-attachments/assets/6a674eb3-7f9c-4209-b603-c54cc2fe1a6d)


  ![image](https://github.com/user-attachments/assets/9298a1c3-07ca-4024-948b-be3c7e519cd5)


  ![image](https://github.com/user-attachments/assets/8c2b71dc-fe57-412a-b85f-3e21962688f7)


**SQL Queries**
  
  These are the Various Queries executed to answer the questions asked under Data Exploration, in their respective numbers.

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

SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue FROM [dbo].[Customer_data2]
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
  **POWER BI**

  These are the various Visualizations created with Power BI to give insight into the Data.
  
![Screenshot (9)](https://github.com/user-attachments/assets/79dfafbe-3511-4255-b38b-42c9c0ee28b0)


![Screenshot (10)](https://github.com/user-attachments/assets/b0009a12-6fff-4e16-aeda-0dae32d30ef8)


![Screenshot (11)](https://github.com/user-attachments/assets/217ed432-1383-4859-bcc9-1c7dd8c28503)


![Screenshot (12)](https://github.com/user-attachments/assets/9262ad38-f40c-40a9-903e-aa2c3c8067da)


![Screenshot (13)](https://github.com/user-attachments/assets/dbf5ed15-ff5e-4e12-b5c6-086dbbb8204c)


![Screenshot (14)](https://github.com/user-attachments/assets/7ef3762f-8a19-4d96-bb32-286d04bb0f29)


![Screenshot (3)](https://github.com/user-attachments/assets/b35acb14-deff-45ab-840b-68f7a0a7ec10)


![Screenshot (4)](https://github.com/user-attachments/assets/efa7df64-f12d-4c37-9fb5-956d22c2df32)


![Screenshot (5)](https://github.com/user-attachments/assets/6b4609e2-11c5-452a-ae2a-b8aa338399ed)


![Screenshot (6)](https://github.com/user-attachments/assets/6314f47a-6360-45a8-9ccf-0d968ecf4aa5)


![Screenshot (7)](https://github.com/user-attachments/assets/b614cc0d-d8ee-4141-bfaa-fdba5d136345)


![Screenshot (8)](https://github.com/user-attachments/assets/75f098e8-fc2e-4d72-b909-1878a72ccca3)
