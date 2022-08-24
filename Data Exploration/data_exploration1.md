** What is the name of the category with the highest category_id in the dvd_rentals.0category table?
\\
``SELECT 
  name,
  category_id
FROM 
  dvd_rentals.category
ORDER BY category_id DESC
LIMIT 1``

