# LITA_CAPSTONE_PROJECT
---
## ANALYSIS FOR CUSTOMER DATA
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

			
  ![image](https://github.com/user-attachments/assets/9ddf37f1-6afd-4caa-93f5-09f0ea5e2d3b)

			

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


![Screenshot (16)](https://github.com/user-attachments/assets/643f1789-ead3-495f-b5d8-359ceb0724d0)
Here are the results of the SQL queries above

  #### Data Visualization
  **POWER BI**

  These are the various Visualizations created with Power BI to give insight into the Data.
  
![Screenshot (9)](https://github.com/user-attachments/assets/79dfafbe-3511-4255-b38b-42c9c0ee28b0)


![Screenshot (10)](https://github.com/user-attachments/assets/b0009a12-6fff-4e16-aeda-0dae32d30ef8)


![Screenshot (11)](https://github.com/user-attachments/assets/217ed432-1383-4859-bcc9-1c7dd8c28503)


![Screenshot (12)](https://github.com/user-attachments/assets/9262ad38-f40c-40a9-903e-aa2c3c8067da)


![Screenshot (13)](https://github.com/user-attachments/assets/dbf5ed15-ff5e-4e12-b5c6-086dbbb8204c)








# PROJECT 2

## ANALYSIS FOR SALES DATA
---
### PROJECT TITLE: Sales Performance Analysis for a Retail Store 
---
#### PROJECT OVERVIEW
---
In this project, the task is to analyze the sales performance of a retail store. 
Sales data will be explored to uncover key insights such as top-selling products, regional 
performance, and monthly sales trends. The goal is to produce an interactive Power BI 
dashboard that highlights these findings.
---
#### Data Sources 
---
This Primary Sales Data was provided by the Incubator Hub for Analysis during LITA Data Analysis Training.
#### Tools Used
---
- Microsoft Exel was used to analyze Sales data using pivot tables to summarize total sales by product, region, and month.
  
- Structured Query Language for querying Data

- PowerBI for Data Visualization

  #### Data Exploration

The Data was used to explore the Following solution that can give insight into better decision making answering questions like

- Retrieve the total sales for each product category.
- Find the number of sales transactions in each region.
- Find the highest-selling product by total sales value.
- Calculate total revenue per product.
- Calculate monthly sales totals for the current year.
- Find the top 5 customers by total purchase amount.
- Calculate the percentage of total sales contributed by each region.
- Identify products with no sales in the last quarter.
  
 #### Data Analysis
  **Microsoft Excel**


![image](https://github.com/user-attachments/assets/b0588e78-e362-41c5-8795-107a61455bd8)



![image](https://github.com/user-attachments/assets/4f054993-4eab-499e-9897-c57d5dc35c8e)



![image](https://github.com/user-attachments/assets/1626b244-79ad-47cd-8c44-eb45be6800d1)



![image](https://github.com/user-attachments/assets/2c9e227b-04f2-4090-ac7f-3fd289f05ff9)



![image](https://github.com/user-attachments/assets/97d8b74e-ba26-4282-ad65-48a1402420cc)



![image](https://github.com/user-attachments/assets/6831696c-a579-45e2-a541-c75efd1ef9a3)


![image](https://github.com/user-attachments/assets/05b35f5f-7f46-4f5f-8dfc-d47031015201)



**SQL Queries**
  
  These are the Various Queries executed to answer the questions asked under Data Exploration, in their respective numbers.


**1. Retrieve the total sales for each product category**

- SELECT product, SUM(TOTALSALESORREVENUE) AS TOTALSALESBYPRODUCT FROM [dbo].[SalesData WD]
GROUP BY Product
order by 2 desc

  **2. Find the number of sales transactions in each region**
     
- select region, count(Orderid) as salestransactionbyregion from [dbo].[SalesData WD]
group by region
order by 2 desc

  **3. Find the highest-selling product by total sales value**

- select top 1 Product, sum(TOTALSALESORREVENUE) as TotalSalesValue from [dbo].[SalesData WD]
group by product
order by 2 desc

  4. calculate total revenue per product.
  
- SELECT PRODUCT, SUM(TOTALSALESORREVENUE) AS TOTALREVENUEBYPRODUCT FROM [dbo].[SalesData WD]
GROUP BY PRODUCT
order by 2 desc

  **5. To get Monthly sales total in current year**
     
- select Product As Productsold, year (OrderDate) as 'Year', month (OrderDate) as 'Months', 
Sum(Totalsalesorrevenue) as salestotalCY from [dbo].[SalesData WD]
where year (orderdate)='2024'
group by Product, Month (OrderDate), year (OrderDate)
order by 3, 4 desc


  **6. Find the top 5 customers by total purchase amount**

- select top 5 Customer_Id, Sum(TotalSalesorRevenue) As TotalPurchaseAmountbyCustomer from [dbo].[SalesData WD]
Group By Customer_Id
order by 2 desc



  **7. Calculate the percentage of total sales contributed by each region**

- SELECT Region, SUM(TotalSalesorRevenue) AS RegionTotalSales,
FORMAT(ROUND((SUM(TotalSalesorRevenue) / CAST((SELECT SUM(TotalSalesorRevenue) FROM [dbo].[SalesData WD]) AS DECIMAL(10,2)) * 100), 1), '0.#') 
AS PercentageOfTotalSales
FROM [dbo].[SalesData WD]
GROUP BY Region
ORDER BY PercentageOfTotalSales DESC

  **8. Identify products with no sales in the last quarter**
   
SELECT Product FROM [dbo].[SalesData WD]
GROUP BY Product
HAVING SUM(CASE 
WHEN OrderDate BETWEEN '2024-06-01' AND '2024-08-31' 
THEN 1 ELSE 0 END) = 0

![Screenshot (17)](https://github.com/user-attachments/assets/adea51b1-8d2c-4533-86a9-92b5145952d7)


![Screenshot (18)](https://github.com/user-attachments/assets/8482c76d-aa73-4821-8983-3429e057dab3)
