What issues will you address by cleaning the data?

- Updated the countries/cities to remove invalid entries replacing with a single entry speaking to data being unavailable. Selected this process as the data associated with the unavailable data, such as revenue, was still improtant to reflect and not remove from the set. 
- Updated the product price from text (when loaded data, loaded column as text) and also turned the amounts into an anount that reflects actual dollars for readability and accuracy. 
- Update ordered quantity from text to numeric. 
- Viewed all columns in each of the 5 uploaded CSV tables to identify areas of discrepancy and invalid entries - also supported identifying the need to update column titles to remove and upper case letters to ensure all lower case to run queries. 
- Checked for and identified duplicate and Null values for key data to use in queries (identified to update to ensure usability)

Queries:
Below, provide the SQL queries you used to clean your data.

**I used these queries to filter invalid entries replacing '(not set)' and 'not available in demo dataset' values with single 'country/city unavailable':**

```
SELECT 	*,
		CASE
			WHEN country = '(not set)' THEN 'Country Unavailable'
			ELSE country
			END AS country1
FROM 	all_sessions 

SELECT 	*,
		CASE
			WHEN city = 'not available in demo dataset' THEN 'City Unavailable'
			WHEN city = '(not set)' THEN 'City Unavailable'
			ELSE city
		END AS city1
FROM 	all_sessions 

```

**I used this query for updating product price from text to numeric and updating decimals to reflect price (dollars):**

```
SELECT 	*,
		CAST(productprice AS NUMERIC)/ 1000000 AS NUMERIC
FROM 	all_sessions
```

**I used this query for updating updating ordered quantity from text to numeric:**

```
SELECT 	*,
    CAST(orderedquantity AS NUMERIC) AS NUMERIC
FROM    products
```

**I used this query for each of the 5 CSV tables to view each column's data identifying areas of needed cleaning. The example is of one of the 5 tables ('all_sessions' CSV table):**

```
SELECT  *
FROM    all_sessions
```

**I used this query to remove duplicates from tables (example demostrates query for 'analytics' table removing duplicates within visitid):**

```
SELECT DISTINCT     visitid
FROM                analytics
```

**I used this query to check and confirm no NULL values in country (example demostrates query for locating missing 'country' column values under 'all_sessions' table):**

SELECT  *
FROM    all_sessions
WHERE   country IS NULL

