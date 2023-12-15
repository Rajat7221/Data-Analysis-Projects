Sales Insights Data Analysis Project
Instructions to setup mysql on your local computer


SQL database dump is in db_dump.sql file above. Download db_dump.sql file to your local computer and import it to MySQL Workbench.

Data Analysis Using SQL
1. Show all customer records
2. 
SELECT * FROM sales.customers;
3. Show total number of customers
SELECT count(*) from sales.customers;
select * from sales.transactions;

4. Show transactions for Chennai market (market code for chennai is Mark001
Select * from sales.transactions where transactions.market_code= "Mark001";

5.  Show transactions where currency is US dollars
Select * from sales.transactions where currency="USD";

6. Applying INNER JOIN ON the transaction table

7. Show transactions in 2020 join by date table
SELECT sales.transactions.* , sales.date.*
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date where date.year=2020;

8. Show total revenue in year 2020,
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date where date.year=2020;

9. show total revenue in year 2020, January Month,
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date where date.year=2020 and date.month_name="January";

10. Show total revenue in year 2020 in Chennai
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date where date.year=2020 and transactions.market_code="Mark001";

11. Show transactions in 2019 by date : Looks like the sales in 2019 were higher in 2019 and dropped in 2020
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date where date.year=2019;

12. Show distrinct product codes that were sold in chennai
Select distinct product_code from sales.transactions where market_code="Mark001";


13. Let's check if there are any other duplications in currency units by checking the distinct currency
Select distinct currency from sales.transactions ;
/*
'INR'  -- I copied these values from result grid below to check the actual nature of the duplicate INR values and we can see there exists some minor difference between both of them.
'INR\r'
*/

14. Let's check how many such transactions exists with this mutation 'INR\r'
SELECT count(*) from transactions where transactions.currency = 'INR\r';   -- Ooops! We can see there are many such transactions around 150000
Select count(*) from transactions where transactions.currency = 'INR';    -- 279 records 
Select count(*) from transactions where transactions.currency = 'USD';    --  2 records 
Select count(*) from transactions where transactions.currency = 'USD\r';  --  2 records 
select * from transactions where transactions.currency = 'USD\r' or transactions.currency = 'USD' ; -- We can see the two of them are duplicates and we need to remove them .
/* We'll keep the records with \r as in INR\r and USD\r as they represent the real world format where \r is used often to represnt new line character
We'll remove the recrds USD AND INR.
*/

Select SUM(transactions.sales_amount)
from transactions
INNER JOIN date
ON transactions.order_date=date.date WHERE date.year = 2020 and date.month_name = "January" and transactions.currency = "INR\r" or transactions.currency = "USD\r" ;


Data Analysis Using Power BI
Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
