#For this SQL project i will be answering 10 questions from this dataset

#I will start by introducing the table 
```sql
-- Use the appropriate database
USE hollywood_db;

-- Show all tables in the database
SHOW tables;

-- Display all records in the hollywood_db_table
SELECT * FROM hollywood_db_table;

-- 1. What is the most popular genre based on revenue in the dataset?
SELECT genre, SUM(worldwide_gross) AS total_gross
FROM hollywood_db_table
GROUP BY genre
ORDER BY total_gross DESC
LIMIT 1;

-- 2. How many films are produced by Lionsgate in the dataset?
SELECT COUNT(*) AS number_of_films
FROM hollywood_db_table
WHERE lead_studio = 'Lionsgate';

-- 3. What is the film with the highest audience score in the dataset?
SELECT film, audience_score
FROM hollywood_db_table
ORDER BY audience_score DESC
LIMIT 1;

-- 4. What is the film with the least audience score in the dataset?
SELECT film, audience_score
FROM hollywood_db_table
ORDER BY audience_score ASC
LIMIT 1;

-- 5. What is the genre with the lowest audience score in the dataset?
SELECT genre, audience_score
FROM hollywood_db_table
ORDER BY audience_score ASC
LIMIT 1;

-- 6. What is the genre with the most audience score in the dataset?
SELECT genre, audience_score
FROM hollywood_db_table
ORDER BY audience_score DESC
LIMIT 1;

-- 7. What year was the film with the most profitability released?
SELECT year, film, profitability
FROM hollywood_db_table
ORDER BY profitability DESC
LIMIT 1;

-- 8. What genre has the most profitability?
SELECT genre, SUM(profitability) AS total_profitability
FROM hollywood_db_table
GROUP BY genre
ORDER BY total_profitability DESC
LIMIT 1;

-- 9. What movie has the highest gross revenue in the dataset?
SELECT film, MAX(worldwide_gross) AS highest_gross_revenue
FROM hollywood_db_table;

-- 10. What lead studio has the highest Rotten Tomatoes rating?
SELECT lead_studio, MAX(rotten_tomatoes_rating) AS highest_rating
FROM hollywood_db_table
GROUP BY lead_studio
ORDER BY highest_rating DESC
LIMIT 1;
```
