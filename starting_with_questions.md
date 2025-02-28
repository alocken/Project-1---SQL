Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:

*Cities with highest level of transaction revenues:*
```
SELECT 	a.city,
	SUM(CAST(
        (CAST(a.productprice AS NUMERIC)/ 1000000)*
        CAST(p.orderedquantity AS NUMERIC)AS NUMERIC)) 
        AS transactionrevenue,
	CASE
		WHEN city = 'not available in demo dataset' THEN 'City Unavailable'
		WHEN city = '(not set)' THEN 'City Unavailable'
		ELSE city
	END AS city1
FROM 	all_sessions a
JOIN 	sales_report s
		ON 		a.productsku = s.productsku
JOIN 	products p 
		ON 		s.restockingleadtime = p.restockingleadtime
GROUP BY a.city 
ORDER BY transactionrevenue DESC;
```

*Countries with highest level of transaction revenues:*
```
SELECT 	a.country,
	SUM(CAST(
        (CAST(a.productprice AS NUMERIC)/ 1000000)*
        CAST(p.orderedquantity AS NUMERIC)AS NUMERIC)) 
        AS transactionrevenue,
	CASE
		WHEN country = '(not set)' THEN 'Country Unavailable'
		ELSE country
	END AS country1
FROM 	all_sessions a
JOIN 	sales_report s
		ON 		a.productsku = s.productsku
JOIN 	products p 
		ON 		s.restockingleadtime = p.restockingleadtime
GROUP BY a.country 
ORDER BY transactionrevenue DESC;
```

Answer:

*Cities with highest level of transaction revenues:*

![alt text](image.png)

*Countries with highest level of transaction revenues:*

![alt text](image-1.png)

**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:

*Average number of products ordered from visitors in each city:*
```
SELECT  a.city, 
	AVG(CAST (s.total_ordered AS NUMERIC)) AS averageordered,
	CASE
		WHEN city = 'not available in demo dataset' THEN 'City Unavailable'
		WHEN city = '(not set)' THEN 'City Unavailable'
		ELSE city
	END AS city1
FROM    all_sessions a
JOIN    sales_report s
        ON  a.productsku = s.productsku
GROUP BY a.city
ORDER BY averageordered DESC;
```

*Average number of products ordered from visitors in each country:*
```
SELECT  a.country, 
	AVG(CAST (s.total_ordered AS NUMERIC)) AS averageordered,
	CASE
		WHEN country = 'not available in demo dataset' THEN 'City Unavailable'
		WHEN country = '(not set)' THEN 'City Unavailable'
		ELSE country
	END AS country1
FROM    all_sessions a
JOIN    sales_report s
        ON a.productsku = s.productsku
GROUP BY a.country
ORDER BY averageordered DESC;
```

Answer:

*Average number of products ordered from visitors in each city:*

![alt text](image-3.png)

*Average number of products ordered from visitors in each country:*

![alt text](image-2.png)



**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:



Answer:





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







