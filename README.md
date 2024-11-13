# lita_Assignment_project2
## Analysis of customer data
### Project 2: Customer Segmentation for a Subscription Service
---
 This project involves me analyzing customer data for a subscription service to identify 
segments and trends. my goal is to analyse customer behavior, track subscription types, 
and identify key trends in cancellations and renewals. The final deliverable is a Power BI 
dashboard that presents your analysis.
### Tools used
---
The following tools where used to analyze the data to ensure all duplicate are removed and the data was cleaned.
- Excel: was used to analysed the average and  sum all the revenue generated from each packages
- 
-Microsoft Excel [Download Here](https://docs.google.com/spreadsheets/d/14zqyQQfBVyXfTJU0UmmOIEyLFd8bvWs35y6NqxZIMow/edit?gid=1543531996#gid=1543531996).

- Power BI: This is done using graphical representation and analysis of the customer data.
- 
  ![image](https://github.com/user-attachments/assets/640a66a1-a090-4c2e-9879-e8a6caff6988)

- Structured Query Language: This was used to analysed the data to show some specific functions based on what was needed

```Create database Costumerproject

Select * from [dbo].[Customer Data]
------retrieve the total number of customer for each region------
Select Region, count (customerid) as region_customers from[dbo].[Customer Data]
group by Region

------ find the most popular subcription type by the number of customers------
select subscriptiontype, count (customerid)as cust_subscription from [dbo].[Customer Data]
group by SubscriptionType
order by cust_subscription desc

----------- customer who cancelled their subscription within 6month------
Select * from[dbo].[Customer Data]
where DATEDIFF(month, SubscriptionStart, subscriptionend) <=6

----------- calculated the average subcription duration for all customer-------
Select AVG(Datediff(year,subscriptionstart, subscriptionend)) As average_duration 
from[dbo].[Customer Data]

------------find customers with Subcription longer than 12 weeks---------
Select customerid, SubscriptionType,subscriptionstart, subscriptionend
From[dbo].[Customer Data]
where Datediff ( month, subscriptionstart, subscriptionend) > 12
