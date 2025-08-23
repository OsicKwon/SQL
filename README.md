# SQL


## SELECT

```sql

--2020.05.09
-------------------------
--BASIC
-------------------------
SELECT * FROM table_name;
SELECT column_name1, column_name2 FROM table_name;
SELECT col1 - col2 * (col3 + col4) FROM table;

-------------------------
--WHERE, (NOT) BETWEEN (AND)
-------------------------
SELECT * FROM table_name WHERE column_name='value';
SELECT * FROM table_name WHERE column_name BETWEEN start_num AND end_num;
SELECT * FROM table_name WHERE column_name NOT BETWEEN start_num AND end_num;

-------------------------
--LIKE
-------------------------
SELECT * FROM table_name WHERE column_name LIKE '%word%';
SELECT * FROM table_name WHERE column_name LIKE 'w_rd';
SELECT * FROM table_name WHERE column_name LIKE '[a-z]d%'; -- ad ~ zd
SELECT * FROM table_name WHERE column_name LIKE '[bsp]d%';  --'bd' 'sd' 'pd'
SELECT * FROM table_name WHERE column_name LIKE '[^bsp]d%';
SELECT * FROM table_name WHERE column_name LIKE '[!bsp]d%';

-------------------------
--LIMIT
-------------------------
SELECT * FROM table_name WHERE column_name LIMIT 5;
SELECT col1, /*col2,*/ col3 FROM table_name WHERE column_name LIMIT 5;
/*This is
a multiline comment
for example*/

-------------------------
--IN
-------------------------
SELECT * FROM table_name WHERE column_name IN ('word1', 'word2');
SELECT * FROM table_name WHERE column_name NOT IN ('word1', 'word2');
SELECT * FROM table1 WHERE column_name IN (SELECT column_name FROM table2)

-------------------------
--AND, OR, NOT
-------------------------
SELECT column1, column2 FROM table_name WHERE condition1 AND condtion2 AND condition3;
SELECT column1, column2 FROM table_name WHERE condition1 OR condtion2 OR condition3;
SELECT column1, column2 FROM table_name WHERE condition1 AND (condtion2 OR condition3);
SELECT column1, column2 FROM table_name WHERE NOT condition1 AND NOT condition2;
SELECT column1, column2 FROM table_name WHERE NOT condition;

-------------------------
--NULL, NOT NULL
-------------------------
SELECT column1, column2 FROM table_name WHERE column1 IS NULL;
SELECT column1, column2 FROM table_name WHERE column2 IS NOT NULL;

-------------------------
--GROUP BY, ORDER BY
-------------------------
SELECT * FROM table_name GROUP BY column_name;
SELECT column1, column2 FROM table_name ORDER BY column1, column2;
SELECT column1, column2 FROM table_name ORDER BY column1 ASC, column2 DESC;
SELECT column1, column2 FROM table_name ORDER BY COUNT(column2) DESC;

-------------------------
--DISTINCT (= DIFFERENT similar UNIQUE)
-------------------------
SELECT DISTINCT column_name1, column_name2 FROM table_name;
SELECT COUNT(DISTINCT column_name) FROM table_name;

-------------------------
--MIN, MAX, AVG, SUM, COUNT,
-------------------------
SELECT MAX(number_column) AS MaxNumber FROM table_name;
SELECT COUNT(number_column) AS CountNumer FROM table_name;

-------------------------
--Alias
-------------------------
SELECT a.column_x, b.column_x
FROM table_a AS a, table_b b
WHERE a.column_x='value' AND a.colum_y = b.column_y;


```
