# SQL-learning-notes


### 1.Select
SELECT *
FROM xxx

### 2.Distinct
SELECT DISTINCT country
FROM films;

SELECT  count(DISTINCT customerid)
FROM salesorderheader

[can be replaced by : group by ]

---Q3a
SELECT DISTINCT customerid,shippinglocationid
FROM salesorderheader

---Q3b
SELECT customerid,shippinglocationid
FROM salesorderheader
GROUP BY customerid,shippinglocationid

### 3.Count
SELECT COUNT(*)
FROM people;

Count non-mising values of a variable
SELECT COUNT(birthdate)
FROM people;

Count unique non-mising values of a variable
SELECT COUNT(DISTINCT birthdate)
FROM people;

### 4.Filter

= equal; <> not equal; < less than; > greater than; <= less than or equal to; >= greater than or equal to

SELECT COUNT(*)
FROM films
WHERE release_year<2000
AND / OR
SELECT *
FROM films
WHERE language='Spanish' 
AND release_year > 2000 
AND release_year < 2010;

SELECT title, release_year
FROM films
WHERE (release_year >= 1990 AND release_year < 2000)
AND (language = 'French' OR language='Spanish')
BETWEEN
SELECT title, release_year
FROM films
WHERE release_year BETWEEN 1990 AND 2000
AND budget > 100000000
AND (language = 'Spanish' or language = 'French');
WHERE IN
SELECT title, release_year
FROM  films
WHERE release_year IN (1990, 2000)
AND duration > 120
IS NULL / IS NOT NULL   (NULL represents a missing or unknown value)
SELECT title
FROM films 
WHERE budget IS NULL

LIKE and NOT LIKE
The % wildcard will match zero, one, or many characters in text.
The _ wildcard will match a single character. 
SELECT name
FROM people
WHERE name LIKE 'B%'

SELECT name
FROM people
WHERE name LIKE '_r%'

SELECT name
FROM people
WHERE name not LIKE 'A%'
