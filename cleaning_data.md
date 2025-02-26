What issues will you address by cleaning the data?

updated column titles to remove capitals preventing running SQL as run would return error





Queries:
Below, provide the SQL queries you used to clean your data.

**I used this query for each of the 5 CSV tables to view each column's data identifying areas of needed cleaning. The example is of one of the 5 tables ('all_sessions' CSV table):**

```
SELECT  *
FROM    all_sessions
```

**I used this query to filter invalid entries (example is 'cities' column in the 'all_sessions' table):**

```
SELECT 

```

**I used this query to remove duplicates from tables (example demostrates query for 'analytics' table removing duplicates within visitid):**

```
SELECT DISTINCT     visitid
FROM                analytics
```

**I used this query to locate missing values (example demostrates query for locating missing 'country' column values under 'all_sessions' table):**

SELECT  *
FROM    all_sessions
WHERE   country IS NULL


**I used this query to replace null values with an alternative default value (example demostrates query for                       ):**