# 1. Some of most important SQL commands

* `SELECT`: extracts data from a database
* `UPDATE`: updates data in a database
* `DELETE`: deletes data from a database
* `INSERT` INTO: inserts new data into a database
* `CREATE DATABASE`: creates a new database
* `ALTER DATABASE`: modifies a database
* `CREATE TABLE`: creates a new table
* `ALTER TABLE`: modifies a table
* `CREATE INDEX`: creates an index(seach key)
* `DROP INDEX`: delets an index

# 2. SELECT

The `SELECT` statement is used to read data from database.  
The result of select query is stored in a result table, called result-set.  

Syntax:  

```SQL
SELECT column_name1, column_name2, ..., column_nameN
FROM table_name;

SELECT * FROM table_name;
```

# 3. DISTINCT

The `DISTINCT` keyword is used to return only different values. (non-duplicated values)  
Syntax:  

```SQL
SELECT DISTINCT column_name1, column_name2, ..., column_nameN
FROM table_name;
```

# 4. WHERE

The `WHERE` clause is used to extract only those records that are satisfied with specified criterion.  
Syntax:  

```SQL
SELECT column_name
FROM table_name
WHERE column_name operator value;
```
Operators:  
|operator | description|
|-|-|
|=|Equal|
|<>|Not equal. `!=` also can be 'not equal' in some DBMS.|
|>|Greater than|
|<|Less than|
|>=|Greater than or equal|
|<=|Less than or equal|
|BETWEEN|Between an inclusive range|
|LIKE|Search for a pattern|
|IN|Specifiy multiple possible values for a column|

# 5. AND & OR operators

`AND` operator is same as Logical AND in programming.  
`OR` operator is also same as Logical OR in programming.  

example1:  

```SQL
SELECT * FROM Access_Log
WHERE Browser='Chrome' AND IP='127.0.0.1'
```

example2:  

```SQL
SELECT * FROM Access_Log
WHERE Browser='Chrome' OR Browser='IE6'
```

example3:  

```SQL
SELECT * FROM Access_Log
WHERE IP='8.8.8.8' AND (Browser='Chrome' OR Browser='IE6')
```

# 6. ORDER BY

The `ORDER BY` keyword is used to sort result-set by one more columns.  
And you can also sort the records in ascending order or descending order.  

```SQL
SELECT * FROM table_name
ORDER BY idx desc, name;
```

If you omit the order, the records will be sorted in ascending order.  

# 7. INSERT INTO

The `INSERT INTO` keyword is used to insert new data into a table.  
There are two ways to insert data into the table with `INSERT INTO` keyword.  

```SQL
INSERT INTO table_name
VALUES(value1, value2, ..., valueN);

INSERT INTO table_name(column1, column2)
VALUES(value1, value2);
```

You can specify both columns and values to be inserted with the second form.  

# 8. UPDATE

The `UPDATE` keyword is used to update data in a table.  
Syntax:  

```SQL
UPDATE table_name
SET column1=value1, column2=value2, ..., columnN=valueN
WHERE columnR=valueR
```

# 9. DELETE

The `DELETE` keyword is used to delete records in a table.
Syntax:  

```SQL
DELETE FROM table_name
WHERE columnR=valueR;
```

# 10. LIKE

The `LIKE` keyword is used to search for a pattern in a column.  
If you want to search all cities with a Country starting with the letter 'A':  

```SQL
SELECT * FROM Cities
WHERE Country LIKE 'A%';
```

ending with the letter 'A':

```SQL
SELECT * FROM Cities
WHERE Country LIKE '%A';
```

You can use not only the letter, but also the string or pattern.  

```SQL
SELECT * FROM Cities
WHERE Country LIKE '%ORE%';
```

# 11. Wildcards

`Wildcards` are used with `LIKE` operator.  

|Wildcard|Description|Example|
|-|-|-|
|`%`|A substitute for zero or more characters|%hi%|
|`_`|A substitute for a single character|_orea|
|`[charlist]`|Sets and ranges of characters to match|[abc]%

You can use one or more wildcards at the same time.  

```SQL
SELECT * FROM Cities
WHERE Country LIKE '_or%';
```

# 12. IN

To specify multiple values in `WHERE` clause, use `IN` operator.  

```SQL
SELECT columns
FROM table_name
WHERE column_name IN (value1, value2, ..., valueN);
```

# 13. BETWEEN

The `BETWEEN` operator is used to select values within a range.  
You can use numbers, text, or dates as values.  

```SQL
SELECT column_name
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```
