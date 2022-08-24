** What is the name of the category with the highest category_id in the dvd_rentals.0category table?**  
``
SELECT 
  name,
  category_id
FROM 
  dvd_rentals.category
ORDER BY category_id DESC
LIMIT 1``

** For the films with the longest length, what is the title of the “R” rated film with the lowest replacement_cost in dvd_rentals.film table?**  \ 
```
WITH cte AS (
SELECT
  title,
  replacement_cost,
  length,
  rating,
  MAX(length) OVER() AS m_length
FROM 
  dvd_rentals.film
GROUP BY title, replacement_cost, length, rating
)
SELECT 
  title,
  length,
  replacement_cost
FROM 
  cte 
WHERE length = m_length
AND rating = 'R'
ORDER BY replacement_cost
LIMIT 1```