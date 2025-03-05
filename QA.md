What are your risk areas? Identify and describe them.

- Data completeness (e.g., NULL or missing values) - this is when key values were either missing or unavailable to accurately query data.

- Data duplication (e.g., row duplication) - this is when there are multiple representations of the same or single data entry. 

- Outlier values (e.g., dates out of appropriate range or potentially outdated) - this is when there are data entries that are outliers or appear to be out of the appropriate range for use. 

QA Process:
Describe your QA process and include the SQL queries used to execute it.

*QA Process for Starting with Questions Exercise:*

 *Data validation, ensuring, verifying processes and associated queries:*

- checked this assertion to determine how many rows where country were missing (NULL)assertion passes as returns no results: 

```
SELECT  *
FROM    all_sessions
WHERE   country IS NULL
```
- checked this assertion to determine how many rows where cities were missing (NULL) - assertion passes as returns no results: 

```
SELECT  *
FROM    all_sessions
WHERE   city IS NULL
```

- checked the data is returned as expected through a row count grouped by date criteria to confirm no anomalous or unexpected counts:

```
SELECT DISTINCT * FROM (
    SELECT DISTINCT DATE(date) AS date, 
        COUNT(*) AS row_count FROM all_sessions
    WHERE date IS NOT NULL
    GROUP BY 1
    ORDER BY date DESC
)
WHERE date > '2010-01-01'
ORDER BY date; 
```

- checked the distinct number of row values confirmed there are discrepancies between the distinct countries/cities and the count of cities/countries: 

```
SELECT COUNT(distinct country) 
FROM (
SELECT country
FROM all_sessions
    ) tmp


SELECT COUNT(country) FROM all_sessions


SELECT COUNT(distinct city) 
FROM (
SELECT city
FROM all_sessions
    ) tmp


SELECT COUNT(city) FROM all_sessions

```

