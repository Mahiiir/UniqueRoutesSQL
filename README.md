# Unique Routes SQL Challenge

## Problem Statement
Given an input table with columns 'source', 'destination', and 'distance' representing routes between cities and their respective distances, write an SQL query to create an output table that includes each unique route. A route is considered duplicate if there is another route with the same distance in reverse direction (e.g., Mumbai to Bangalore and Bangalore to Mumbai with a distance of 500). The output table should contain only one entry per unique distance, effectively removing duplicates. How would you structure your SQL query to achieve this?

## Solutions
I explored three different methods to solve this SQL challenge, each offering unique insights and optimizations.

### Method 1: Using GREATEST and LEAST functions
In this method, I leveraged the `GREATEST` and `LEAST` functions to handle potential reversals in city pairs. The `GREATEST` function helps return the highest value, and the `LEAST` function returns the lowest value from a set of values, ensuring that each city pair is treated uniformly regardless of order.

### Method 2: Using Self JOIN
This method involves creating two identical tables using a Common Table Expression (CTE). I then performed a JOIN operation where the `source` column of the first table was joined with the `destination` column of the second table. This method also utilized the `ROW_NUMBER()` window function to ensure that each unique route is represented once.

### Method 3: Using SUBQUERY
The SUBQUERY approach is particularly efficient in optimizing the query. It involves nested queries where the inner query serves to isolate unique distances before they are compared in the outer query using comparison operators.

## Conclusion
These methods demonstrate various SQL techniques to effectively handle and manipulate data to derive meaningful results. Each method offers a different perspective on handling duplicates and optimizing SQL queries for better performance.

