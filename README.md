# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
Focused on the learning that we have acheived throughout our time in the Data Science Flex course, this project brings together and tests SQL knowledge. The goals of this project are to complete a series of steps, including development of queries, to answer and also create questions on the ecommerce database as well as to complete QA and cleaning of the data. This project requires use of both entry and more advanced SQL queries to complete and provide responses to key questions that explore the data in the ecommerce database. 

Goals were to enhance understanding and knowledge of the ecommerce database through exploration and queries to build on developed skills to be able to transform data to answer complex questions. 


## Process
### Loaded CSV data into pgAdmin
- 5 unique CSV files had to be manually loaded into pgadmin
- loaded each of the 5 into a database title 'ecommerce' in PostGresSQL
- loaded each column as text to avoid issues with data discrepancies 
- realized that each column will require to have all lowercase, updated columns manually to reflect this observation
- reviewed the data in PostGresSQL to become familiar with what was available within each set and noted immediate areas of issue (e.g, null values, incomplete columns, etc.)
### Completed Part 2: Data Cleaning 
- oriented with the ecommerce database and identified potental issues that needed to be cleaned
- completed the necessary queries to clean required data for the assignment and recorded the issues addressed into the cleaning_data.md file
### Completed Part 3: Starting with Questions
- explored and identified the data required to answer the questions (5) presented 
- ensured data was useable and cleaned data as necessary to be able to use the data in the function queries 
- queries resulted in the answers to the questions
- completed the inputs in VScode, CMD, and then pushed to GitHub 
- double checked how the information transferred and updated as required 
### Completed Part 4: Starting with Data
- explored the data and developed queries for three additional queries 
- tested the queries and cleaned the required data
- copied over the queries and supporting answers to VScode, CMD, and then pushed to GitHub
### Completed Part 5: QA your data
- completed a QA process that identified and described risk areas
- developed and executred a QA process to address those areas and validate accuracy of results
### Completed Part 6: Generate ERD 
- within pgAdmin, generated the ERD for the database after identifying primary keys for each table 
- downloaded the image and saved as schema.png and added to repo for submission
### Completed Final Additons to README file 
- reviewed and updated the README file for final edits and additions
- finalized README file 

## Results
This data can provide information to answer questions on things such as highest revenue of countries/cities, top selling countries/cities, average products ordered by cities/countries, products odered from cities/countries, and understanding the highest ordered products for countries/cities. 

Althought not requested, this data could also answer other types of questions such as queries regarding stock levels and stock time and how long it would take to restock out of stock product or determining highest volume of visitors by date/country/city and type of visit most frequently associated with the visits.


## Challenges 
The original state of the data presented challenges as it was often incomplete, not clean, and observed many discrepancies. It was a challenge to identify areas of issue and error as they were quite vast and extensive. 

Once in the data and working through data questions, it was clear that sometimes the incomplete data would create issues that would have to be resolved before being able to complete the work to answer the questions. 


## Future Goals
Spend more time cleaning all of the data in greater depth and detail. Adding in additional queries throughout to reduce things like repetitive zeroes (e.g., Q1 of starting_with_questions). I would also take the time to learn how to upload PDFs for the visual instead of PNGs through VScode as I think this might be able to reduce the volume of additional image files on the assignment. I would also likely load the CSV column data to reflect what each column's data was instead of loading all as text as this added extra steps in queries to shift 'text' to 'numeric' in instances that took time to consider and complete.