# LITA-CAPSTONE---CUSTOMER-DATA--REPORT

LITA CAPSTONE Customer  REPORT
### DESCRIPTION.
#### THE DATASET CONTAINS RECORDS ON CAPSTONE SALES PERFORMANCE BY REGION, QUANTITY SOLD, UNIT COST, ORDERDATE AND PRODUCTS SOLD BETWEEN 2023-2024.

### PROJECT OVERVIEW

This data Analysis project aims to give insights on the sales performance of the CAPSTONE DATASET AND THE SUBSCRIPTION DATASET project for a period of two years (2023-2004) . This analysis will help to make data-driven decisions for growth strategies.

### SUMMARY
This is an exploration of the CAPSTONE sales dataset to uncover key insights such as top-selling products, motnly sales data and regional performance.

### GOAL
The goal is to produce an interactive and understandable analysis for an informed growth strategy for the Capstone and Package subscription company.

### DATA SOURCES
The primary source of Data used here is an Excel data file, CSV file.

### TECHNOLGY USED
- Excel sheet
- excel SUM and AVERAGE functions
- Excel pivot table
- SQL SERVER (My SQL)
- POWER BI
  
### TOOLS USED
- Microsoft Excel [(Download here)] https://1drv.ms/x/c/45b106d15656cf28/EYXe7GV0cORIk3pJQxx0qfMBEP0vvfRZWVw60YwZD1uWkA?e=2UVmOq
- Data cleaning
- Data Visualization
- Calcutions
- Analysis
- SQL- (structured query language) for data querrying
- Github- for porfolio Building
  
### SKILLS
- Data Cleaning
- Data EXPLORATION
- Data Analysis
- Data Visualisation

### DATA CLEANING AND PREPARATION
On the initial phase of Data cleaning and preparations, I performed the following action; Data loading and inspection Handling missing variables Data cleaning and formatting

### EXPLORATORY DATA ANALYSIS
EDA involved the exploration of the data to answer some questions about the Data such as:

- to retrieve the total number of customers from each region.
- to find the most popular subscription type by the number of customers.
- to find customers who canceled their subscription within 6 months.
- to calculate the average subscription duration for all customers.
- to find customers with subscriptions longer than 12 months.
- to calculate total revenue by subscription type.
- to find the top 3 regions by subscription cancellations.
- to find the total number of active and canceled subscription
- 
### DATA ANALYSIS AND VISUALISATION - MS EXCEL
### DATA ANALYSIS - SQL
#### SQL QUERIES 
**Here are the revised SQL queries based on the single table structure:**

1. **Total number of customers from each region:**

   ```sql
   SELECT region, COUNT(*) AS total_customers
   FROM customers
   GROUP BY region;
   ```

2. **Most popular subscription type:**

   ```sql
   SELECT subscription_type, COUNT(*) AS total_customers
   FROM customers
   GROUP BY subscription_type
   ORDER BY total_customers DESC
   LIMIT 1;
   ```

3. **Customers who canceled within 6 months:**

   ```sql
   SELECT *
   FROM customers
   WHERE end_date IS NOT NULL
   AND end_date BETWEEN CURDATE() - INTERVAL 6 MONTH AND CURDATE();
   ```

4. **Average subscription duration:**

   ```sql
   SELECT AVG(DATEDIFF(end_date, start_date)) AS avg_duration
   FROM customers
   WHERE end_date IS NOT NULL;
   ```

5. **Customers with subscriptions longer than 12 months:**

   ```sql
   SELECT *
   FROM customers
   WHERE end_date IS NOT NULL
   AND DATEDIFF(end_date, start_date) > 365;
   ```

6. **Total revenue by subscription type:**

   ```sql
   SELECT subscription_type, SUM(revenue) AS total_revenue
   FROM customers
   GROUP BY subscription_type;
   ```

7. **Top 3 regions by subscription cancellations:**

   ```sql
   SELECT region, COUNT(*) AS total_cancellations
   FROM customers
   WHERE end_date IS NOT NULL
   GROUP BY region
   ORDER BY total_cancellations DESC
   LIMIT 3;
   ```

8. **Total active and canceled subscriptions:**

   ```sql
   SELECT
       SUM(CASE WHEN end_date IS NULL THEN 1 ELSE 0 END) AS active_subscriptions,
       SUM(CASE WHEN end_date IS NOT NULL THEN 1 ELSE 0 END) AS canceled_subscriptions
   FROM customers;
   ```

DATA VISUALISATION - POWER BI
![Customer data visualisation](https://github.com/user-attachments/assets/f5c31789-3946-457a-b343-8ffc3c74aaf5)

