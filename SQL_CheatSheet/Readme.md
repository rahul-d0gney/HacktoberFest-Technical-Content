**Welcome to `Top-18 Command`!**

<div align="right" markdown="1">

*[Read this in other languages](README.md#translations)*

</div>

**`QUERYING SINGLE TABLE`!**

Fetch all columns from the country table:
<pre><code>
SELECT *
FROM country;
Fetch id and name columns from the city table:
</code></pre>

<pre><code>
SELECT id, name
FROM city;
Fetch city names sorted by the rating column in the default ASCending order:
</code></pre>

<pre><code>
SELECT name
FROM city
ORDER BY rating [ASC];
</code></pre>
Fetch city names sorted by the rating column in the DESCending order:
<pre><code>
SELECT name
FROM city
ORDER BY rating DESC;
</code></pre>

# ALIASES

<pre><code>
<b>COLUMNS</b>
SELECT name AS city_name
FROM city;
</code></pre>
<b>TABLES</b>
<pre><code>
SELECT co.name, ci.name
FROM city AS ci
JOIN country AS co
  ON ci.country_id = co.id;
</code></pre>

# FILTERING THE OUTPUT
<b>COMPARISON OPERATORS</b>
<pre><code>
Fetch names of cities that have a rating above 3:
SELECT name
FROM city
WHERE rating > 3;
</code></pre>
Fetch names of cities that are neither Berlin nor Madrid:
<pre><code>SELECT name
FROM city
WHERE name != 'Berlin'
  AND name != 'Madrid';
</code></pre>

<b>TEXT OPERATORS</b>
Fetch names of cities that start with a 'P' or end with an 's':
<pre><code>
SELECT name
FROM city
WHERE name LIKE 'P%'
  OR name LIKE '%s';

</code></pre>
Fetch names of cities that start with any letter followed by 'ublin' (like Dublin in Ireland or Lublin in Poland):
<pre><code>
SELECT name
FROM city
WHERE name LIKE '_ublin';
</code></pre>
<b>OTHER OPERATORS</b>
Fetch names of cities that have a population between 500K and 5M:
<pre><code>
SELECT name
FROM city
WHERE population BETWEEN 500000 AND 5000000;
</code></pre>
Fetch names of cities that don't miss a rating value:
<pre><code>
SELECT name
FROM city
WHERE rating IS NOT NULL;
</code></pre>
Fetch names of cities that are in countries with IDs 1, 4, 7, or 8:
<pre><code>
SELECT name
FROM city
WHERE country_id IN (1, 4, 7, 8);
QUERYING MULTIPLE TABLES
INNER JOIN
JOIN (or explicitly INNER JOIN) returns rows that have matching values in both tables.

SELECT city.name, country.name
FROM city
[INNER] JOIN country
  ON city.country_id = country.id;
Tables joined using INNER JOIN
LEFT JOIN
LEFT JOIN returns all rows from the left table with corresponding rows from the right table. If there's no matching row, NULLs are returned as values from the second table.
</code></pre>
<pre><code>
SELECT city.name, country.name
FROM city
LEFT JOIN country
  ON city.country_id = country.id;
</code></pre>