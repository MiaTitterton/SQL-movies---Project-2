OVERVIEW: This project aims to demonstrate key SQL skills and techniques commonly used by data analysts to explore, clean, and analyse retail sales data. It covers the process of creating and managing a retail sales database, conducting exploratory data analysis and using SQL queries to answer a range of business-focused questions.


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

-- Q.1 list all the movies released in a 2026 
SELECT * FROM film_data
WHERE release_year = 2026 

--Q.2 Find the top 3 countries with the most films 
SELECT 
   original_language, 
   COUNT(film_id) AS total_content 
FROM film_data
GROUP BY original_language 
ORDER BY total_content DESC
LIMIT 3

--Q.3 How many Spider-Man films are there
SELECT * FROM film_data
WHERE title LIKE '%Spider-Man%'

--Q.4 What are the top ten most popular films
SELECT 
   popularity 
FROM film_data 
ORDER BY popularity DESC
LIMIT 10

--Q.5 How many Horror films were released in 2025
SELECT 
   COUNT(film_id) AS horror_films
FROM film_data  
WHERE Genres = 'Horror'
  AND release_year = 2025

-- END OF PROJECT 
