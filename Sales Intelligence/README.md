# Sales Insights Data Analysis Project

## Overview

This repository contains a sales data analysis project focusing on insights derived from a SQL database. The database dump is provided in the `db_dump.sql` file. Follow the instructions below to set up the database and perform the data analysis using SQL queries and Power BI.

## Setup Instructions

1. **Database Setup:**
   - Download the `db_dump.sql` file.
   - Import the file into MySQL Workbench.

2. **Data Analysis Using SQL:**
   - Use the provided SQL queries to perform various analyses on the sales data.
   - Queries include showing customer records, total number of customers, transactions for specific markets and currencies, applying INNER JOIN operations, and calculating total revenue for specific time periods and markets.

3. **Data Analysis Using Power BI:**
   - Utilize Power BI for further data analysis.
   - A formula is provided to create a `norm_amount` column, taking into account currency conversion (assuming a conversion rate of 1 USD = 75 INR).

## SQL Queries

```sql
-- Example SQL Queries
-- Show all customer records
SELECT * FROM sales.customers;

-- Show total number of customers
SELECT COUNT(*) FROM sales.customers;

-- Show transactions for Chennai market (market code for Chennai is Mark001)
SELECT * FROM sales.transactions WHERE transactions.market_code= "Mark001";

-- Show transactions where currency is US dollars
SELECT * FROM sales.transactions WHERE currency="USD";

-- Applying INNER JOIN ON the transaction table
-- Show transactions in 2020 join by date table
SELECT sales.transactions.*, sales.date.*
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date WHERE date.year=2020;

-- Show total revenue in year 2020
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date WHERE date.year=2020;


-- Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)




