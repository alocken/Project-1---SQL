Question 1: Determine the number of visitors that visited each date and determine which date had the highest number of total visits.
SELECT date, COUNT(visitid) AS totalvisits

SQL Queries: 

```
SELECT date, COUNT(visitid) AS totalvisits
FROM analytics
GROUP BY date, visitid
ORDER BY totalvisits DESC;
```

Answer: 
2017-07-31 had the highest total visits with 1033. 

![alt text](<Start Data - Q1.png>)


Question 2: Determine total visits per country per date. Which country held the highest total visits? Are there any noteworthy patterns in the frequency of countries listed?

SQL Queries:

```
SELECT s.country, s.date, COUNT(a.visitid) AS totalvisits
FROM all_sessions s
JOIN analytics a
    ON s.visitid = a.visitid
GROUP BY s.country, s.date, a.visitid
ORDER BY totalvisits DESC;
```

Answer: The United States held the highest total visits with 292 on 2017-07-14. Also, the United States was often the highest total visits for many of the dates observed.

![
](<Start Data - Q2.png>)

Question 3: List the type of visits associated with the countries with the highest total visits per date. What is observed to be the most frequent type? 

SQL Queries:

```
SELECT s.country, s.date, s.type, COUNT(a.visitid) AS totalvisits
FROM all_sessions s
JOIN analytics a
    ON s.visitid = a.visitid
GROUP BY s.country, s.date, s.type, a.visitid
ORDER BY totalvisits DESC;
```

Answer: "Event" is observed to be the most frequent type. 

![alt text](<Start Data - Q3.png>)


