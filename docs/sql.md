# SQL
Leveraging the Power of SQL: Essential Commands for ETL Processes

## Introduction:

In data engineering and ETL processes, SQL (Structured Query Language) commands play a pivotal role in manipulating and transforming data. SQL offers a versatile set of commands that enable data engineers to extract data from various sources, apply transformations, and load it into target destinations. In this article, we will explore some of the most useful SQL commands for ETL processes, highlighting their applications and benefits.

## Useful commands
### SELECT - Extracting Data:
The foundational SQL command "SELECT" is used to extract data from one or more tables. It allows you to specify the columns you want to retrieve, apply filters using the "WHERE" clause, and sort data using "ORDER BY."

~~~~
SELECT customer_id, order_date, order_amount
FROM orders
WHERE order_date >= '2023-01-01'
ORDER BY order_amount DESC;
~~~~
### JOIN - Combining Data:
The "JOIN" command allows you to combine data from multiple tables based on related columns. Joins are crucial for integrating data from various sources during the ETL process.

~~~~
SELECT orders.order_id, customers.customer_name, orders.order_date
FROM orders
JOIN customers ON orders.customer_id = customers.customer_id;
~~~~

### GROUP BY - Aggregating Data:
The "GROUP BY" command is used to group rows based on specific columns and apply aggregate functions like SUM, AVG, COUNT, etc. It is instrumental in summarizing data during the transformation phase of ETL.

~~~~
SELECT product_category, SUM(sales_amount) AS total_sales
FROM sales
GROUP BY product_category;
~~~~

### CASE - Conditional Transformation:
The "CASE" statement allows you to apply conditional logic and perform transformations based on specific conditions. It is useful for handling data discrepancies or applying custom business rules during data transformation.

~~~~
SELECT order_id, order_date,
  CASE
    WHEN order_amount > 1000 THEN 'High Value'
    WHEN order_amount > 500 THEN 'Medium Value'
    ELSE 'Low Value'
  END AS order_category
FROM orders;
~~~~
### INSERT - Loading Data:
The "INSERT" command is used to load data into a target table from other tables, temporary tables, or external data sources. It is a fundamental SQL command for the "Load" phase of ETL.
~~~~
INSERT INTO target_table (column1, column2, column3)
SELECT column1, column2, column3
FROM source_table
WHERE condition;
~~~~
### UPDATE - Modifying Data:
The "UPDATE" command allows you to modify existing data in a table based on specified conditions. It is useful when updating records during the ETL process.
~~~~
UPDATE customers
SET customer_status = 'Active'
WHERE last_purchase_date >= '2023-01-01';
~~~~
### DELETE - Removing Data:
The "DELETE" command is used to remove specific rows from a table based on specified conditions. It is essential for data cleanup and maintenance during ETL.
~~~~
DELETE FROM customers
WHERE customer_status = 'Inactive';
~~~~

### Common Table Expressions (CTEs):
Common Table Expressions, commonly known as CTEs, are temporary result sets that allow you to create complex, reusable, and more readable SQL queries. CTEs are defined using the "WITH" clause and can reference themselves or other CTEs within the same query.

~~~~
WITH revenue_cte AS (
  SELECT product_category, SUM(sales_amount) AS total_revenue
  FROM sales
  GROUP BY product_category
)
SELECT product_category, total_revenue, total_revenue * 0.1 AS tax_amount
FROM revenue_cte;
~~~~
#### Benefits:

- Improves query readability by breaking down complex logic into smaller, manageable parts.
- Enhances code maintainability by allowing developers to reuse CTEs across multiple queries.
- Optimizes query performance by enabling the database optimizer to treat CTEs as materialized subqueries.
  
### Subqueries:
Subqueries, also known as nested queries, are queries embedded within another query. They enable you to perform operations on a subset of data or retrieve data from related tables.
~~~~
SELECT order_id, order_date, order_amount
FROM orders
WHERE order_amount > (SELECT AVG(order_amount) FROM orders);
~~~~
#### Benefits:
- Provides a concise and straightforward way to filter data based on complex conditions or aggregate functions.
- Enables you to retrieve data from related tables using subqueries in joins, improving data integration.

### Temporary Tables:
Temporary Tables are tables that exist temporarily for the duration of a session or a specific query. They are useful for storing intermediate results during complex data transformations.
~~~~
CREATE TEMPORARY TABLE temp_sales AS (
  SELECT product_id, SUM(quantity) AS total_quantity
  FROM sales
  GROUP BY product_id
);

SELECT product_id, total_quantity
FROM temp_sales
WHERE total_quantity > 1000;
~~~~
#### Benefits:

Reduces complexity in the main query by breaking down data transformation steps into separate temporary tables.
Improves query performance by reducing the need for complex joins and calculations in a single query.

## Conclusion:

SQL commands are indispensable tools for data engineers and analysts involved in ETL processes. From data extraction and transformation to loading and maintenance, SQL empowers users to handle diverse data scenarios efficiently. By mastering these essential SQL commands, data professionals can streamline their ETL workflows, ensure data accuracy, and gain valuable insights to drive informed decision-making.

As SQL continues to be a primary language for data manipulation, exploring its advanced features and applying best practices will enable data teams to unlock the full potential of their data, making a significant impact on their organization's success.

## Cheatsheet
[SQL basics cheatsheet](https://learnsql.com/blog/sql-basics-cheat-sheet/sql-basics-cheat-sheet-a3.pdf)
  
