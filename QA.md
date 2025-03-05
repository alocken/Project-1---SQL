What are your risk areas? Identify and describe them.




QA Process:
Describe your QA process and include the SQL queries used to execute it.

*QA Process for Starting with Questions Exercise:*

 Data validation
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


- ensure
- verify
- 

Explanation:

Validation check
