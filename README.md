# CAPSTONE_PROJECT2
CAPSTONE PROJECT2 (CUSTOMER DATA)

## Project 2: Customer Segmentation for a Subscription Service

[Project Overview](#project-overview)

[Data](#data)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)

### Project Overview
---
This project aims to analyze customer data for a subscription service to identify meaningful segments and trends in customer behavior. By understanding subscription patterns, cancellations, renewals, and key subscription types, the project will provide insights that can help optimize customer acquisition, retention strategies, and overall service offerings.              

### Data
---
- **Data Sources**
  
  The Data is Capstone Project and this is a data that was freely downloaded from Ladies in Tech Africa (LITA) Canvas.

- **Data Summary**

   There are 6 Colomns in the dataset, which are the key indicators that give us insight into of the Customer data

  a .**SubscriptionType**-  SubscriptionType refers to the specific plan or model that a customer chooses when subscribing to a service

  b. **SubscriptionStart** - The SubscriptionStart refers to the date when a customer first subscribes to a service or plan.

  c. **SubscriptionEnd** -  The SubscriptionEnd is the date when the customer's current subscription expires.

  d. **SubscriptionDuration** - SubscriptionDuration is the total length of time a customer has been subscribed to the service, calculated as the difference between the SubscriptionStart and SubscriptionEnd dates

  e. **Cancelled** -  Cancelled refers to the status of a subscription that has been terminated before its SubscriptionEnd date

  f. **Revenue** -  is the total amount of money generated from subscriptions during a given period.
  
### Tools Used
---
1. Microsoft Excel [Download Here](https://wwwmicrosoft.com)

2. SQL - Structured Query Language for Querying the data [Download Here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)

3. Microsoft PowerBI for Visualisation [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
   
 
 4. Github For Portfolio Building  🗃️
  
  - Building up your portfolio as an Data Analyst

 b. **For Analysis**
   
   In order to give a proper data analysis of the information gotten from the dataset we explore it through:
   - By creating a New column for '**SubscriptionDuration**'. The new colomn is calculated by Subtracting **SubscriptionStart** from **'SubscriptionEnd'** (UnitPrice*Quantity).
   - Average  SubscriptionDuration was calculated using '**Averageif**'.
   - Most Popular Subscription was calculated using '**Countif**'.


![PROJECT2 EXCEL](https://github.com/user-attachments/assets/b34628b2-e8eb-449d-a9e1-164cc3d224fe)

     
 c. **For data Visualization**
   - Pivot table is  use to summarize 'SubscriptionType by Revenue', 'SubscriptionType by Count of Revenue', 'SubscriptionType by SubscriptionDuration', 'SubscriptionStart by SubscriptionDuration', '*Cancelled by Revenue'  'SubscriptionEnd Month by Revenue' and 'Average Revenue per SubscriptionType'.

![PROJECT 2 PIVOT 1](https://github.com/user-attachments/assets/756e3d15-9eba-4164-8b3d-a0a85de9068c)


![PROJECT 2 PIVOT jpg 22](https://github.com/user-attachments/assets/fc2d5e25-8673-4a4d-93f7-fa99faa3c803)


2. SQL - Structured Query Language for Querying the data [Download Here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)

   - **For Analysis**

 We wrote queries to extract key insights by. 
-  retrieve the total sales for each product category.
- find the number of sales transactions in each region.
- find the highest-selling product by total sales value.
- calculate total revenue per product.
- calculate monthly sales totals for the current year.
- find the top 5 customers by total purchase amount.
- calculate the percentage of total sales contributed by each region.
- identify products with no sales in the last quarter. 

3. Microsoft PowerBI for Visualisation [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)
 
  a. **For Data Cleaning**

   The Dataset is upload into Power Bi and cleaned
   
  b. **For Analysis**
   
   In order to give a proper data analysis of the information gotten from the dataset we explore it through:

   - Creating New measures for: Average Sales, Product Count and Quantity count.
 
  c. **For data Visualization**

  - Created a dashboard that visualizes the insights found in Excel and SQL. The
     dashboard includes a sales overview, top-performing products, and 
     regional breakdown using Text box, Cards, Map, Charts and a Slicer

![PROJECT2 POWERBI](https://github.com/user-attachments/assets/b8f9b9bc-4c10-46a4-ace2-110d69c87ec3)


4. **Github For Portfolio Building ** 🗃️
  
  - Building up your portfolio as an Data Analyst

### Data Cleaning and Preparations
---
To achive a proper Data Cleaning and preparations, I perform the following action:
1. Data loading and Inspection
2. Handling missing variables
3. Data Cleaning and formatting

### Exploratory Data Analysis
---
EDA involves the examining the Data From the retail store in order to get some fact such as  ;

- Sales performance of the retail store
- What is the overall sales trend in the store
- Total sales by product, region, and month
- Average sales per product
- Total revenue by region
- Highest Selling Products
  
### Data Analysis
---
Here I include all basic lines of queries and some of the DAX expressions used during this analysis;

```SQL
select * from [dbo].[LITA_PROJECTA]

----- retrieve the total sales for each product category----

SELECT Product, SUM ([Total_Sales]) AS TotalSales
FROM [dbo].[LITA_PROJECTA]
GROUP BY Product

----find the number of sales transactions in each region----
SELECT Region, COUNT(OrderID) AS Number_Of_Transactions
FROM [dbo].[LITA_PROJECTA]
GROUP BY Region
ORDER BY Number_Of_Transactions DESC;

----find the highest-selling product by total sales value----

SELECT Product, SUM([Total_Sales]) AS TotalSales
FROM [dbo].[LITA_PROJECTA]
GROUP BY Product
ORDER BY TotalSales DESC; 

----calculate total Sales per product----

SELECT Product, SUM(CAST(Quantity AS INT) * CAST(UnitPrice AS DECIMAL(10, 2))) AS TotalSales
FROM [dbo].[LITA_PROJECTA]
GROUP BY Product
ORDER BY TotalSales DESC;

---- calculate monthly sales totals for the current year.---

SELECT OrderDate, SUM(Total_sales) AS monthlySales
FROM [dbo].[LITA_PROJECTA]
WHERE OrderDate between '2024-01-01' and '2024-12-31'
GROUP BY OrderDate
Order by OrderDate

----find the top 5 customers by total purchase amount----

SELECT TOP 5
    [Customer_Id], 
    SUM([Total_Sales]) AS TotalPurchase
FROM 
    [dbo].[LITA_PROJECTA]
GROUP BY 
    [Customer_Id]
ORDER BY 
    TotalPurchase DESC;

	----calculate the percentage of total sales contributed by each region----

	WITH RegionSales AS    
	(SELECT  Region, 
    SUM([Total_Sales]) AS RegionSales
    FROM [dbo].[LITA_PROJECTA]
    GROUP BY Region),
TotalSales AS (
    SELECT SUM([Total_Sales]) AS OverallTotalSales
    FROM [dbo].[LITA_PROJECTA])
SELECT 
    rs.Region,
    rs.RegionSales,
    (rs.RegionSales * 100.0 / ts.OverallTotalSales) AS PercentageOfTotalSales
FROM RegionSales rs
CROSS JOIN 
    TotalSales ts;
```

### Data Visualization                  
💹📊📉
Tables	
CHARTS

CONTACT ADDRESS:
Number 35 Olajesu street Agodo ,Ikotun. Lagos 🏠

📧
``` Email 
omo_sola@yahoo.com
```



