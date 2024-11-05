# LITA_PROJECT--Customer-Segmentation-for-a-Subscription-Service
This is a documentation of data validation, cleaning, querying, transformation, and visualization I carried out while working on the Customer Data of  Ladies in Tech Africa's final project.  
## Topic:  Customer Segmentation and Trend.
---

[Project Overview](#project-overview)

[Data Collected](#data-collected)

[Tools Used](#tools-used)

[Data Cleaning and Preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

[Data Visualization Visualization-and-Inferences](#data-visualization-and-inferences)


### Project Overview
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
---
![X 2 1](https://github.com/user-attachments/assets/f0aa2a83-3c01-4bb0-961e-116d650e4463)

![X 2 2](https://github.com/user-attachments/assets/896f09e6-6ec5-4612-b60a-c76dea7ab84c)

![X 2 3](https://github.com/user-attachments/assets/71ff1ed4-8825-4c39-a722-231e2fa566ba)

![X 2 4](https://github.com/user-attachments/assets/d63a9f31-72b5-45ab-8ca0-2d25f0322e6e)

![X 2 5](https://github.com/user-attachments/assets/678b84c0-eb77-474a-a321-e05a12d6701a)

![X 2 6](https://github.com/user-attachments/assets/173925d4-98c4-4427-99aa-d779367f2042)

#### 2.	Average subscription duration.

![X 2 4](https://github.com/user-attachments/assets/b46b1474-3dfe-4655-961b-f9b5cab3b17d)

![x 2 7](https://github.com/user-attachments/assets/c81a440a-7e0e-4fdd-a701-b9ee5f33e172)

#### 3.	 Most popular subscription types.

![x 2 8](https://github.com/user-attachments/assets/ed447588-7ed9-4357-b8be-d4a09e00745c)
------

### Data Analysis, Visualization, and Inferences (SQL)
---
This includes the lines of queries used while analyzing the data on SQL, and their outputs.

#### 1.	Total number of customers from each region.

```SQL
SELECT COUNT(customerid) AS CustomerCountPerRegion, region from [dbo].[Capstone Customer Data]
group by Region
```

![SQL 2 1](https://github.com/user-attachments/assets/87f5c75e-ffa6-470c-9daf-19afe2338a25)

#### 2.	Most popular subscription type by the number of customers.

```SQL
select top 1 COUNT(customerid) as NumberofSubscribers, SubscriptionType from [dbo].[Capstone Customer Data]
group by SubscriptionType
```

![SQL 2 2](https://github.com/user-attachments/assets/095304d8-eadf-4aa8-b78c-7484361f6ae1)


#### 3. Customers who canceled their subscription within 6 months.

```SQL
	select customername from [dbo].[Capstone Customer Data]
		      where cancelationcount>0
			   and subduration_month <=6
```

![SQL 2 3](https://github.com/user-attachments/assets/3bae0f28-ec48-41fc-bc02-5b163dc11968)


#### 4. Average subscription duration for all customers.

```SQL
select AVG([SubDuration_Month]) 
	    as MonthlyAverageSubDuration
	from [dbo].[Capstone Customer Data]
```

![SQL 2 4](https://github.com/user-attachments/assets/8f4bee73-2575-4493-b999-20e3f10aaafa)


#### 5. Customers with subscriptions longer than 12 months.

```SQL
select customername from [dbo].[Capstone Customer Data]
		      where cancelationcount>0
			   and subduration_month >12
```

![SQL 2 5](https://github.com/user-attachments/assets/2a54cbb5-d9f5-4243-8a36-4b228be9724b)


#### 6. Total revenue by subscription type.

```SQL
select sum(revenue) as TotalRevenue,  [SubscriptionType]   from [dbo].[Capstone Customer Data]
		   group by [SubscriptionType]
```

![SQL 2 6](https://github.com/user-attachments/assets/fbe21e42-2594-4d5a-a9f1-bcc378955782)


#### 7. Top 3 regions by subscription cancellations

```SQL
select  TOP 3  SUM(cancelationcount) as SubCancellations,
region from [dbo].[Capstone Customer Data]
group by region
```

![sql 2 7](https://github.com/user-attachments/assets/184d0b3d-b250-424f-aba0-93051d4b2fd3)


#### 8.  Total number of active and canceled subscriptions.

```SQL
 select count(Canceled) as TotalNumberofActiveandCanceledSub
	     from [dbo].[Capstone Customer Data]
```

![SQL2 8](https://github.com/user-attachments/assets/93e1b110-5706-46f5-b318-07f1b772eeef)
---

### Data Analysis, Visualization, and Inferences (Power BI)
---
This includes all the Visuals made using Power BI.

![PBI 2 1](https://github.com/user-attachments/assets/f3de5b02-0ad5-4ff8-8b37-b7adf106aa2f)

![PBI 2 2](https://github.com/user-attachments/assets/7d2139dd-e24e-420a-8e3d-35d28e589055)

![PBI 2 3](https://github.com/user-attachments/assets/0ff37539-8a48-4b66-acd4-099c52746866)

![PBI 2 4](https://github.com/user-attachments/assets/1511d9ed-e3bd-47ec-9c44-b7037c8a0cb6)

![PBI 2 5](https://github.com/user-attachments/assets/15bdf572-c85c-4f01-a8fc-43d8fc5ae4b5)

![PBI 2 6](https://github.com/user-attachments/assets/23c20294-6609-42bf-aa98-958fc822d4ca)

![PBI 2 7](https://github.com/user-attachments/assets/6fe1ffcd-3bd2-4ea9-a0c8-814d553ea47e)

![PBI 2 8](https://github.com/user-attachments/assets/f57d5fa7-afac-4f0e-8c5f-d7661487bf01)

![PBI 2 9](https://github.com/user-attachments/assets/207e2982-5e85-4d75-b954-2dff1182231d)

![PBI 2 10](https://github.com/user-attachments/assets/ec8e6814-a8a4-4b52-83f9-12510d958f64)

![PBI 2 11](https://github.com/user-attachments/assets/910f7fe4-173f-4262-9796-56f9eae7ccbb)

![PBI 2 12](https://github.com/user-attachments/assets/9f318bb8-84a9-4cc8-9633-1bd977c445ad)




























