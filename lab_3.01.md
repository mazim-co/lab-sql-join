-- Lab | SQL Join
-- 1. List number of films per category.
select count(*) as 'Number of Films', c.name as 'Category Name' from sakila.film_category f
inner join sakila.category c
on f.category_id = c.category_id
group by f.category_id;

-- 2. Display the first and last names, as well as the address, of each staff member.
SELECT first_name AS 'First Name', last_name AS 'Last Name', a.address AS 'Address'
FROM sakila.staff AS s
INNER JOIN sakila.address AS a
ON s.address_id = a.address_id;

-- 3. Display the total amount rung up by each staff member in August of 2005.
SELECT sum(amount) AS 'Total Amount', s.first_name AS 'Name'
FROM sakila.payment AS p
INNER JOIN sakila.staff AS s
ON p.staff_id = s.staff_id
GROUP BY s.first_name;

-- 4. List each film and the number of actors who are listed for that film.
SELECT title
FROM sakila.film AS f

-- 5. Using the tables payment and customer and the JOIN command, list the total paid by each customer. List the customers alphabetically by last name.