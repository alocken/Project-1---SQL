# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
(fill in your description and goals here)
Focused on the learning that we have acheived throughout our time in the Data Science Flex course, this project brings together and tests SQL knowledge. The goals of this project are to complete a series of steps, including development of queries, to answer and also create questions on the ecommerce database as well as to complete QA and cleaning of the data. This project requires use of both entry and more advanced SQL queries to complete.


## Process
### Loaded CSV data into pgAdmin
- 5 unique CSV files had to be manually loaded into pgadmin
- loaded each of the 5 into a database title 'ecommerce' in PostGresSQL
- loaded each column as text to avoid issues with data discrepancies 
- realized that each column will require to have all lowercase, updated columns manually to reflect this observation
- reviewed the data in PostGresSQL to become familiar with what was available within each set and noted immediate areas of issue (e.g, null values, incomplete columns, etc.)
### (your step 2)

## Results
(fill in what you discovered this data could tell you and how you used the data to answer those questions)
This data can provide a multitude of information to answer questions on things such as highest revenue of countries/cities, nderstanding the highest ordered products for countries/cities, 

This data could also answer other types of questions such as queries regarding stock levels and stock time and how long it would take to restock out of stock products.

## Challenges 
(discuss challenges you faced in the project)
The original state of the data presented challenges as it was often incomplete, not clean, and observed many discrepancies. It was a challenge to identify areas of issue and error as they were quite vast and extensive. 
Once in the data and working through data questions, it was clear that sometimes the incomplete data would create issues that would have to be resolved before being able to complete the work to answer the questions. 


## Future Goals
(what would you do if you had more time?)
Spend more time cleaning all of the data in greater depth and detail. Adding in additional queries throughout to reduce things like repetitive zeroes (e.g., Q1 of starting_with_questions). I would also take the time to learn how to upload PDFs for the visual instead of PNGs through VScode as I think this might be able to reduce the volume of additional image files on the assignment. I would also likely load the CSV column data to reflect what each column's data was instead of loading all as text as this added extra steps in queries to shift 'text' to 'numeric' in instances that took time to consider and complete.