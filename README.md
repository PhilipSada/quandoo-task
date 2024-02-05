# Quandoo Task
## Question 1:
Write an SQL query (or queries) to identify the most important cities for our company.
You may use any tool you like for consolidating the data sets, like Jupyter Notebook with SQL
package, but please share the SQL with us.
## Solution
Pandasql package was used in Jupyter Notebook to write the SQL queries. Below are the SQL queries to identify the most important cities for the company.
#### Total Revenue in each city
```sql
    SELECT m.city,
           r.country,
           ROUND(SUM(r.revenue),2) as total_revenue
    FROM reservations r
    JOIN merchants m ON r.merchant_id = m.merchant_id
    GROUP BY m.city, r.country
    ORDER BY total_revenue DESC
    LIMIT 5; 
```
#### Total number of reservations in each city
```sql
    SELECT m.city,
           r.country,
           COUNT(r.reservation_id) as total_reservations
    FROM reservations r
    JOIN merchants m ON r.merchant_id = m.merchant_id
    GROUP BY m.city, r.country
    ORDER BY total_reservations DESC
    LIMIT 5; 
```
#### Total number of merchants in each city
```sql
    SELECT m.city,
           r.country,
           COUNT(DISTINCT r.merchant_id) as total_merchants
    FROM reservations r
    JOIN merchants m ON r.merchant_id = m.merchant_id
    GROUP BY m.city, r.country
    ORDER BY total_merchants DESC
    LIMIT 5; 
```
#### Total number of customers in each city
```sql
    SELECT m.city, 
           r.country,
           COUNT(DISTINCT r.customer_id) as total_customers
    FROM reservations r
    JOIN merchants m ON r.merchant_id = m.merchant_id
    GROUP BY m.city, r.country
    ORDER BY total_customers DESC
    LIMIT 5; 
```


## Question 2:
- Please summarize the most important observations based on the csv files.
- What in your opinion are important metrics for our business?
We use Tableau for reporting and visualizations, but you are free to use a different tool that you
are more comfortable with. In case you do use a different tool, please point us to the URL to
download a trial version.

## Solution
Tableau was used to summarize the most important observations based on the csv files and show important metrics for the business. 
Here is the link to the tableau dashboard
