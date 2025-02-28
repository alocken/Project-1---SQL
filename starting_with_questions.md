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

*Types (product categories) of products ordered from visitors in each city:*
```
SELECT  a.city, 
	    CAST(a.v2productcategory AS TEXT) AS producttypes, 
	    SUM(CAST(p.orderedquantity AS NUMERIC)) AS orderedquantity,
	    CASE
		    WHEN a.v2productcategory= '${escCatTitle}' THEN 'Cat'
		    ELSE a.v2productcategory
	    END AS producttypes1
FROM    all_sessions a
JOIN    products p
	    ON 	a.productsku = p.sku
WHERE   CAST(p.orderedquantity AS NUMERIC)<> 0 
            AND a.city<> 'not available in demo dataset' 
            AND a.city<> '(not set)' 
            AND a.v2productcategory<> '(not set)'
GROUP BY a.city, a.v2productcategory
ORDER BY producttypes1 ASC, orderedquantity DESC;
```

*Types (product categories) of products ordered from visitors in each country:*
```
SELECT 	a.country, 
	    CAST(a.v2productcategory AS TEXT) AS producttypes, 
	    SUM(CAST(p.orderedquantity AS NUMERIC)) AS orderedquantity,
	    CASE
		    WHEN a.v2productcategory= '${escCatTitle}' THEN 'Cat'
		    ELSE a.v2productcategory
	    END AS producttypes1
FROM    all_sessions a
JOIN    products p
	    ON 	a.productsku = p.sku
WHERE   CAST(p.orderedquantity AS NUMERIC)<> 0 
            AND a.country<> 'not available in demo dataset' 
            AND a.country<> '(not set)' 
            AND a.v2productcategory<> '(not set)'
GROUP BY a.country, a.v2productcategory
ORDER BY producttypes1 ASC, orderedquantity DESC;
```

Answer:

There are a few noteworthy patterns observed when viewing the results from the queries returning the types of products ordered from visitors in each country:
1) Almost all cities have home product types in the products ordered.
2) United states is the highest volume orders per product type for almost all categories listed indicating the United States is the higest consumer of ordered products from this particular site.
3) Significant volume of product types in 'Home' product types while other product types observed to be realtively limitedlimited or low in comparison.

![alt text](image-4.png)

![alt text](image-5.png)

**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:



Answer:





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:



Answer:







