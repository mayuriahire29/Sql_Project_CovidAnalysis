create database sqlproject3;
-- use database 
use sqlproject3;

-- show tables
show tables;
-- Joining Tables:
-- 1. Retrieve the full name of artists along with the names of the museums where their works are displayed.
SELECT artist.full_name, museum.name
FROM artist
JOIN work ON artist.artist_id = work.artist_id
JOIN museum ON work.museum_id = museum.museum_id;
-- 2. Group By and Count:
-- How many works does each artist have in the database? Display the artist's full name along with the count of their works, ordered by the count in descending order.
SELECT artist.full_name, COUNT(work.work_id) AS work_count
FROM artist
LEFT JOIN work ON artist.artist_id = work.artist_id
GROUP BY artist.artist_id, artist.full_name
ORDER BY work_count DESC;

-- 3. Order By and Limit:
-- List the top 5 museums with the highest number of works displayed in the database, along with their respective counts.
SELECT museum.name, COUNT(work.work_id) AS work_count
FROM museum
LEFT JOIN work ON museum.museum_id = work.museum_id
GROUP BY museum.museum_id, museum.name
ORDER BY work_count DESC
LIMIT 5;


-- 4. Join, Order By, and Limit:
-- Display the names and styles of the works along with the corresponding museum names, ordered by the museum name in ascending order. Limit the results to 10.
SELECT work.name, work.style, museum.name AS museum_name
FROM work
JOIN museum ON work.museum_id = museum.museum_id
ORDER BY museum.name ASC
LIMIT 10;




-- 5.Join, Group By, and Sum:
-- Show the total sale price for each artist's works. Display the artist's full name along with the total sale price, ordered by the total sale price in descending order.
SELECT artist.full_name, COUNT(work.work_id) AS work_count
FROM artist
LEFT JOIN work ON artist.artist_id = work.artist_id
GROUP BY artist.artist_id, artist.full_name
ORDER BY work_count DESC;




-- 6. Join, Group By, and Having:
-- List artists who have more than 3 works in the database, along with the count of their works.
SELECT MAX(artist.full_name) AS full_name, COUNT(work.work_id) AS work_count
FROM artist
JOIN work ON artist.artist_id = work.artist_id
GROUP BY artist.artist_id
HAVING work_count > 3;



-- 7. Join, Where, and Order By:
-- Retrieve the names of works and their corresponding artists' full names for works that have a sale price smaller than their regular price. 
SELECT work.name, artist.full_name, product_size.sale_price
FROM work
JOIN artist ON work.artist_id = artist.artist_id
JOIN product_size ON work.work_id = product_size.work_id
WHERE product_size.sale_price > product_size.regular_price;




-- 8. Join, Group By, and Average:
-- Calculate the average height and width of the artworks in the database. Display the average height and width.
SELECT AVG(canvas_size.height) AS avg_height, AVG(canvas_size.width) AS avg_width
FROM canvas_size;




-- Join, Group By, and Max:
-- 9 Find the maximum sale price among all the works in each museum. Display the museum name along with the maximum sale price.
SELECT m.name, ps.max_sale_price
FROM museum m
JOIN (
    SELECT work.museum_id, MAX(product_size.sale_price) AS max_sale_price
    FROM work
    JOIN product_size ON work.work_id = product_size.work_id
    GROUP BY work.museum_id
) ps ON m.museum_id = ps.museum_id;


-- Join, Group By, and Concatenate:
-- 10. Concatenate the first name and last name of artists along with their nationality, separated by a comma. Display the concatenated string along with the count of woescendrks by each artist, ordered by the count in ding order.
SELECT CONCAT(artist.first_name, ' ', artist.last_name, ', ', artist.nationality) AS artist_info, COUNT(work.work_id) AS work_count
FROM artist
JOIN work ON artist.artist_id = work.artist_id
GROUP BY artist.artist_id, artist.first_name, artist.last_name, artist.nationality
ORDER BY work_count DESC;