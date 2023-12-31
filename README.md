# Aggregate Functions

## Introduction:
One of the fundamental aspects of database management is the ability to effectively analyze and aggregate data within tables. This task serves as a guide to understanding the aggregate functions in SQL, including SUM, COUNT, AVERAGE, MIN, and MAX.

## Problem statement:

1. How many rows are in the SALES table provided?

2. The business is operating in how many regions?

3. What is the total profit generated in the WEST region?

4. What is the average profit generated from the sales of the company’s product?

5. On average, how many days does it take for a customer to get their orders shipped? Create a new column (Days_to_ship)

6. How many products does the company sell?

7. Show the names and cities of the 5 customers who contributed most to the overall profit.

8. Show the sales generated by cities where total sales is greater than 20000

## Result/Discussion:

Number of rows in the sales column from the sample_superstore:


![](Sales_Rows.png)


From the snapshot above, it shows the total number of rows in the SALES table and the syntax used is as follows;

SELECT COUNT(*) FROM SALES;


Total number of regions from the sample_superstore:

![](Distint_Region.png)

The snapshot above shows the number of regions in which the business is operating on and the command used is as folllows;

_SELECT COUNT(DISTINCT region) FROM superstore;_


Total profits generated in the West region:

![](Total_Profit.png)

The snapshot shows the total profits generated in the West region and the command used to acchieved this is as follows;

_Select Sum(profit) As Total_Profit from superstore_

_Where region = 'West';_

Average profit:

![](Average_Profit.png)

The snapshot above shows the average profit generated from the company's product sales and the command used is as follows;

_SELECT AVG(profit) AS Average_profit FROM superstore;_

Average number of days:


Number of products:

![](Products_Number.png)

The above screenshot shows the number of different products the company sells and the command used to achieve the result is as follows;

_SELECT COUNT(distinct `Product Name`) As Number_of_products FROM superstore;_

Top 5 customers:

![](Top_Five.png)

The snapshot above shows the names and cities of the top 5 customers who contributed most to the overall profit of the store. And the syntax used to achieve this result is as follows;

_Select `customer name`, city, sum(profit) from superstore_

_group by `customer name`, city_

_order by sum(profit) desc_

_limit 5;_

Total sales for each City greater than 20000:

![](Cities.png)



The snapshot above shows Show the names and cities of the 5 customers who contributed most to the overall profit of the store. And the syntax used to get the result is as follows;

_SELECT city, SUM(sales) AS total_sales FROM superstore_

_GROUP BY city_

_HAVING SUM(sales) > 20000;_


## Conclusion:

These tasks have provided a comprehensive exploration of the superstore data set through SQL. The total number of rows in the table was determined, followed by identifying the number of regions in which the business operates. Total profit was calculated in the West region and the average profit from product saless, the count of different products sold by the company was determined and lastly, the top 5 customers with overall profit greater than 20000 was determined.
These tasks collectively demonstrate the power of SQL in extracting valuable insights from a dataset for informed decision-making.
