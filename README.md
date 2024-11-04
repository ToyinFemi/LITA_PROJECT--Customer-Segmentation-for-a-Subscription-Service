# LITA_PROJECT--Customer-Segmentation-for-a-Subscription-Service
This is a documentation of data validation, cleaning, querying, transformation, and visualization I carried out while working on the Customer Data of  Ladies in Tech Africa's final project.  
## Topic:  Customer Segmentation and Trend.
---
### Overview
---
This analysis involves analyzing customer data for a subscription service to identify segments and trends. The analysis is aimed at understanding customer behavior, tracking subscription types, and identifying key trends in cancellations and renewals.
### Data Collected
---
The dataset includes the following key columns:

- CustomerID: A unique identification number given to each subscriber.
- CustomerName: The name of each subscriber.
- Region: The geographical area where the service is  being used.
- SubscriptionType: The type of subscription used by each customer.
- SubscriptionStart: The start date of all subscriptions.
- SubscriptionEnd: The end date of all subscriptions.
- Canceled: This indicates if a subscription has been canceled by a subscriber or not. 
- Revenue: The total amount of money paid by each subscriber.

The following are the calculated columns made in Excel:
- SubDuration(Month)
Formula used: = DATEDIF(SubscriptionStart,SubscriptionEnd,"M")

- CancelationCount
Formula used: = =IF(Canceled,1,0)

- RenewalCount
Formula used: ==IF(Canceled,0,1)

- SubscriptionCount
----

### Tools Used
---
1. Microsoft Excel: For Data Cleaning, Analysis, and Visualization.
2. Structured Query Language(SQL): For Querying of Data.
3. Power BI: For Data Transformation, and Virtualization. 

### Data Cleaning and Preparations
---
The following actions were performed to clean and prepare the data:

- Data Loading and Inspection on Microsoft Excel, SQL, and Power BI.
- Data Cleaning and Formatting on Microsoft Excel and Power BI.
- Handling and Calculating missing variables on Microsoft Excel, SQL, and Power BI.

### Exploratory Data Analysis
---
- Subscription patterns.
- Average subscription duration.
- The most popular subscription types.
- Total number of customers from each region.
- Most popular subscription type by the number of customers.
- Customers who canceled their subscription within 6 months.
- Average subscription duration for all customers.
- Customers with subscriptions longer than 12 months.
- Total revenue by subscription type.
- Top 3 regions by subscription cancellations.
- Total number of active and canceled subscriptions.
- Key customer segments and trends. 
- Cancellation and subscription trends. 

### Data Analysis, Visualization, and Inferences (Microsoft Excel)
---
This includes all the pivot tables made using Microsoft Excel.
#### 1.	Subscription Trend.






