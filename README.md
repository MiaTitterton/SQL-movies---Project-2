OVERVIEW: This project aims to demonstrate key SQL skills and techniques commonly used by data analysts to explore, clean, and analyse movie data. It covers the process of creating and managing a movie database, conducting exploratory data analysis and using SQL queries to answer a range of business-focused questions.

Below, I have included the SQL questions and queries used throughout the project, demonstrating how I applied SQL to investigate the data and address specific business requirements.


# SQL-movies---Project-2

DROP TABLE IF EXISTS film_data;

CREATE TABLE film_data
(
    media_type VARCHAR(10),
    film_id INT PRIMARY KEY,
    title VARCHAR(100),
    original_language VARCHAR(5),
    genres VARCHAR(100),
    popularity NUMERIC(10,4),
    vote_average NUMERIC(5,3),
    vote_count INT,
    release_year INT
);

SELECT * FROM film_data

-- Q.1 List all the movies released in 2026
SELECT * FROM film_data
WHERE release_year = 2026;

--Q.2 Find the top 3 languages used within films
SELECT 
   original_language, 
   COUNT(film_id) AS total_content 
FROM film_data
GROUP BY original_language 
ORDER BY total_content DESC
LIMIT 3;

--Q.3 List all Spider-Man films
SELECT * FROM film_data
WHERE title LIKE '%Spider-Man%';

--Q.4 What are the top ten most popular films
SELECT 
   title,
   popularity 
FROM film_data 
ORDER BY popularity DESC
LIMIT 10;

--Q.5 How many Horror films were released in 2025
SELECT 
   COUNT(film_id) AS horror_films
FROM film_data  
WHERE genres = 'Horror'
  AND release_year = 2025;

-- END OF PROJECT 
