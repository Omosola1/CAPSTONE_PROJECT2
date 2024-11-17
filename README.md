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

[Results and Findings](#results-and-findings)

[Recommendations](#recommendations)

[Conclusion](#conclusion)


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

### Data Cleaning and Preparations
---
 
 **For Data Cleaning**

To achive a proper Data Cleaning and preparations, I perform the following action:
1. Data loading and Inspection
2. Handling missing variables
3. Data Cleaning and formatting

The Capstone Customer Data Contains '70,000' raw data, how we were left witn a smaller dataset after cleaning the data by removing the duplicates.


### Exploratory Data Analysis

**Excel**   
   
   In order to give a proper data analysis of the information gotten from the dataset we explore it through:
   - By creating a New column for '**SubscriptionDuration**'. The new colomn is calculated by Subtracting **SubscriptionStart** from **'SubscriptionEnd'** (UnitPrice*Quantity).
   - Average  SubscriptionDuration was calculated using '**Averageif**'.
   - Most Popular Subscription was calculated using '**Countif**'.

```
SQL QUERIES

SQL Query: SELECT region, COUNT(customer_id) AS customer_count FROM customer_data GROUP BY region; Insight: Shows the distribution of customers across different regions, helping identify regions with a high customer base. Most Popular Subscription Type


SQL Query: SELECT subscription_type, COUNT(customer_id) AS subscription_count FROM customer_data GROUP BY subscription_type ORDER BY subscription_count DESC; Insight: Identifies the most popular subscription types, allowing us to focus on high-demand services. Customers Who Canceled Within 6 Months


SQL Query: SELECT customer_id, subscription_type FROM customer_data WHERE DATEDIFF(month, subscription_start_date, cancellation_date) <= 6; Insight: Helps identify potential dissatisfaction by tracking early cancellations, informing retention strategies. Average Subscription Duration


SQL Query: SELECT AVG(DATEDIFF(month, subscription_start_date, subscription_end_date)) AS avg_duration FROM customer_data; Insight: Reveals the average length of subscriptions, helping assess customer retention. Customers with Subscriptions Over 12 Months


SQL Query: SELECT customer_id, subscription_type FROM customer_data WHERE DATEDIFF(month, subscription_start_date, CURRENT_DATE) > 12; Insight: Identifies loyal customers with long-term subscriptions. Total Revenue by Subscription Type


SQL Query: SELECT subscription_type, SUM(revenue) AS total_revenue FROM customer_data GROUP BY subscription_type; Insight: Shows which subscription types are the most profitable. Top 3 Regions by Cancellations


SQL Query: SELECT region, COUNT(cancellation_date) AS cancellations FROM customer_data GROUP BY region ORDER BY cancellations DESC; Insight: Indicates regions with the highest cancellation rates for targeted retention campaigns. Total Active vs. Canceled Subscriptions


SQL Query: SELECT SUM(CASE WHEN cancellation_date IS NULL THEN 1 ELSE 0 END) AS active_subscriptions, SUM(CASE WHEN cancellation_date IS NOT NULL THEN 1 ELSE 0 END) AS canceled_subscriptions FROM customer_data; Insight: Provides an overview of current active vs. canceled subscriptions.

```



### Data Analysis
---



![PROJECT2 EXCEL](https://github.com/user-attachments/assets/b34628b2-e8eb-449d-a9e1-164cc3d224fe)

     
 c. **For data Visualization**
   - Pivot table is  use to summarize 'SubscriptionType by Revenue', 'SubscriptionType by Count of Revenue', 'SubscriptionType by SubscriptionDuration', 'SubscriptionStart by SubscriptionDuration', '*Cancelled by Revenue'  'SubscriptionEnd Month by Revenue' and 'Average Revenue per SubscriptionType'.

![PROJECT 2 PIVOT 1](https://github.com/user-attachments/assets/756e3d15-9eba-4164-8b3d-a0a85de9068c)


![PROJECT 2 PIVOT jpg 22](https://github.com/user-attachments/assets/fc2d5e25-8673-4a4d-93f7-fa99faa3c803)





  



### Data Visualization                  
💹📊📉





CONTACT ADDRESS:
Number 35 Olajesu street Agodo ,Ikotun. Lagos 🏠

📧
``` Email 
omo_sola@yahoo.com
```



