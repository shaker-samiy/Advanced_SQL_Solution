# Advanced_SQL_Solution

``` sql
# Creating a quert to select the city with smallest length
WITH smallest_city AS (
SELECT * FROM stations
WHERE LENGTH(city) = 3
       ORDER BY city
        LIMIT 1 
),
# Creating a query to select the city with greatest length
greatest_city AS
(
    SELECT * FROM station
WHERE LENGTH(city) = 21
       ORDER BY city
        LIMIT 1
)
# union the two names and the lengths of the two cities in one output
       SELECT city, length(smallest_city.city) FROM
       smallest_city
       UNION 
       SELECT city, length(greatest_city.city) FROM
       greatest_city
       ;
```
