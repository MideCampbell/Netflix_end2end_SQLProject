# Netflix_end2end_SQLProject
This project requires a thorough examination of Netflix's movie and TV show data using SQL. The purpose is to extract relevant insights and answer a variety of (20+) business questions using the dataset. This project details the project's objectives, business challenges, solutions, findings, and conclusions. 


# Netflix Movies and TV Shows End-to-End Data Analysis Project using SQL
 
## Overview
This project requires a thorough examination of Netflix's movie and TV show data using SQL. The purpose is to extract relevant insights and answer a variety of (20+) business questions using the dataset. This paper details the project's objectives, business challenges, solutions, findings, and conclusions.
 
## Objectives
 
- Examine the distribution of content types (movies versus television shows).
- Determine the most frequent ratings for films and television shows.
- Organise and analyse content by release year, country, and duration.
- Analyse and categorise information using precise criteria and keywords.
 
## Dataset
 
Though the dataset for this project is sourced from the Kaggle dataset, but its uploaded here: Netflix_titles.csv
 
 
## Business Problems and Solutions
 
### 1. Display the total Number of Movies vs TV Shows
 
```sql
SELECT 
   type,
   COUNT(*) count_type
FROM netflix_titles
GROUP BY type
```
 
**Objective:** Determine the distribution of content types on Netflix.
 
 
### 2. Count the Number of Content Items in Each Genre
 
```sql
SELECT 
	Trim(Value) AS genre,  
	COUNT(*) AS total_content  
FROM netflix_titles
   CROSS APPLY string_split (listed_in, ',') 
GROUP BY Trim(Value);
```
 
**Objective:** Objective: Count the number of content items in each genre.
