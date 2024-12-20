#For this SQL project i will be answering 10 questions from this dataset 

#I will start by introducing the table
```sql
-- Use the appropriate database
USE athletes_db;

-- Show all tables in the database
SHOW tables;

-- Display all records in the athlete_info table
SELECT * from athlete_info;

-- 1. What is the average age of the athletes in the dataset?
SELECT AVG(age)
FROM athlete_info;

-- 2. How many athletes in the dataset are from the United States?
SELECT COUNT(athletes)
FROM athlete_info
WHERE country = 'United States';

-- 3. What sport in the dataset has the most gold medals?
SELECT sport, SUM(gold_medals) AS Total_goldmedals
FROM athlete_info
GROUP BY sport
ORDER BY Total_goldmedals DESC
LIMIT 1;

-- 4. How many athletes in the dataset are below the age of 30?
SELECT COUNT(*) AS athletes_below_30
FROM athlete_info
WHERE age < 30;

-- 5. Who is the youngest and the oldest athlete in the dataset?

-- Youngest athlete
SELECT athletes, age
FROM athlete_info
WHERE age = (SELECT MIN(age) FROM athlete_info);

-- Oldest athlete
SELECT athletes, age
FROM athlete_info
WHERE age = (SELECT MAX(age) FROM athlete_info);

-- 6. How many athletes in the dataset are from France?
SELECT COUNT(*) AS athletes_from_france
FROM athlete_info
WHERE country = 'France';

-- 7. How many athletes in the dataset participated in swimming?
SELECT COUNT(DISTINCT athletes) AS athletes_in_swimming
FROM athlete_info
WHERE sport = 'Swimming';

-- 8. What is the total number of medals won by athletes in the dataset over the years?
SELECT year, COUNT(*) AS total_medals
FROM athlete_info
GROUP BY year
ORDER BY year;

-- 9. Who is the most participating athlete in the dataset?
SELECT athletes, COUNT(*) AS participation
FROM athlete_info
GROUP BY athletes
ORDER BY participation DESC
LIMIT 1;

-- 10. How many athletes in the dataset are above the age of 30?
SELECT COUNT(*) AS athletes_above_30
FROM athlete_info
WHERE age > 30;
```
