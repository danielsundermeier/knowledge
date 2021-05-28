# SQL 

## Links
- [SQL Operators Tutorial](https://www.freecodecamp.org/news/sql-operators-tutorial/)
- [SQL Templates](https://popsql.com/sql-templates)
- [Reduce the size of MySQL dump file](https://mauricius.dev/reduce-the-size-of-a-large-mysql-dump-file/)
- [Use the Index, Luke](https://use-the-index-luke.com/)
- [In-depth discussion of all kinds of topics related to the database modeling](https://minimalmodeling.substack.com/)

## SQL Syntax and PDO Operations

[Overview of SQL Commands and PDO Operations](https://www.taniarascia.com/overview-of-sql-commands-and-pdo-operations)

### Create Database

```sql
CREATE DATABASE IF NOT EXISTS database_name
```

### Drop Database

```sql
DROP DATABASE IF EXISTS database_name
```

### Create Table

```sql
CREATE TABLE IF NOT EXISTS table_name (
  column_a Datatype Constraints,
  column_b Datatype Constraints,
);
```

#### Datatypes

**Datatype**|**Description**
-----|-----
`INT(n)`|Integer values
`FLOAT(n, d)`| Decimal values
`VARCHAR(n)`|String with max number of characters
`TEXT`|String with without set limit (max value of 65,535)
`DATE('YYYY-MM-DD')`|Year, month, and day
`DATETIME('YYYY-MM-DD HH:MI:SS')`|Year, month, day, hour, minute, and second
`TIMESTAMP('YYYY-MM-DD HH:MI:SS')`|Datetime corresponding to UNIX epoch time

#### Constraints

**Constraint**|**Description**
-----|-----
`PRIMARY KEY`|Unique identifier
`AUTO_INCREMENT`|Integer value is automatically added and incremented
`UNIQUE`|Value must be unique
`NOT NULL`|Value cannot be NULL
`DEFAULT`|Initialized with default value

### Alter Table

```sql
 ALTER TABLE table_a
         ADD column_a DataType
ALTER COLUMN column_a DataType   
        DROP column_a
   RENAME TO table_b
```

### Drop Table

```sql
DROP TABLE IF EXISTS table_name
```

### Select Rows

```sql
   SELECT *, column_a, column_b, AggregateFunction(column_a)
       AS Alias
     FROM table_a
     JOIN table_b
       ON table_a.column_a = table_b.column_a
    WHERE Condition
      AND Condition
       OR Condition
      NOT Condition
 GROUP BY column_a
   HAVING Condition
 ORDER BY column_a
      ASC
     DESC
    LIMIT Count
   OFFSET Count
```

### Select Distint Rows

```sql
SELECT DISTINCT column_name
           FROM table_name
```

#### Joins

**Join**|**Description**
-----|-----
`(INNER) JOIN`|Returns only matches from both tables
`LEFT JOIN`|Returns all entries from left table, and matches from right table
`RIGHT JOIN`|Returns all entries from right table, and matches from left table
`FULL JOIN`|Returns all entries from both tables

#### Aggregate Functions

**Function**|**Description**
-----|-----
`COUNT(column)`|Counts number of rows
`SUM(column)`|Adds all values
`MIN(column)`|Find the smallest value
`MAX(column)`|Find the largest value
`AVG(column)`|Find the average value

#### Conditions

**Operator**|**Condition**
-----|-----
`=`, `!=`|Equal, not equal
`<`,  `>`, |Less than, greater than
`<=`, `>=`|Less/greater than or equal to
`BETWEEN ... AND ...`|Within range of two values
`NOT BETWEEN ... AND ...`|Not within range of two values
`IN (...)`|Exists in list
`NOT IN (...)`|Does not exist in list
`LIKE`|Case insensitive equality comparison
`NOT LIKE`|Case insensitive inequality comparison
`%`|Matches a sequence of characters
`\_`|Matches a single character
`IS NULL`|Value is null
`IS NOT NULL`|Value is not null
`ANY (...)`|If any values meet condition
`ALL`|If all values meet condition
`EXISTS`|If one or more records exist

### Insert Rows

```sql
INSERT INTO table_name (column_a, column_b)
     VALUES ("value_1", "value_2")
```

### Update Rows

```sql
UPDATE table_name
   SET column_a = "value_1"
       column_b = "value_2"
 WHERE Condition
```

### Delete Rows

```sql
DELETE FROM table_name
      WHERE Condition
```

## PDO

### Open Connection

```php
$host       = 'localhost';
$username   = 'root';
$password   = 'root';
$dbname     = 'pdo';
$dsn        = "mysql:host=$host;dbname=$dbname";
$options    = [
                PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
                PDO::ATTR_EMULATE_PREPARES => false
              ];

$connection = new PDO($dsn, $username, $password, $options);
```

#### Datatypes

**Datatype**|**Description**
-----|-----
`PDO::PARAM_BOOL`|Represents a boolean data type
`PDO::PARAM_NULL`|Represents the SQL NULL data type
`PDO::PARAM_INT`|Represents the SQL INTEGER data type
`PDO::PARAM_STR`|Represents the SQL CHAR, VARCHAR, or other string data type

### Select Rows

```php
$sql = "SELECT * 
          FROM users
         WHERE location = :location";
         
$location = 'Chicago';

$statement = $connection->prepare($sql);
$statement->bindParam(':location', $location, PDO::PARAM_STR);
$statement->execute();

$rows = $statement->fetchAll(PDO::FETCH_ASSOC);

foreach ($rows as $row) {
  echo $row['location'];
} 
```

### Insert Row

```php
$sql = "INSERT INTO users (username, email) 
             VALUES (:username, :email)";

$username = 'Tania';
$email = 'tania@example.com';

$statement = $connection->$prepare($sql);
$statement->bindValue(':username', $username, PDO::PARAM_STR);
$statement->bindValue(':email', $email, PDO::PARAM_STR);

$insert = $statement->execute();
```

### Update Row

```php
$user = [
  'username'  => 'Tania',
  'email'     => 'tania@example.com',
  'location'  => 'Chicago',
];

$sql = "UPDATE users 
           SET username = :username, 
               email = :email, 
               location = :location, 
         WHERE id = :id";
        
$statement = $connection->prepare($sql);
$statement->execute($user);
```

### Delete Row

```php
$sql = "DELETE FROM users 
              WHERE id = :id";

$statement = $connection->prepare($sql);
$statement->bindValue(':id', 5, PDO::PARAM_INT);
 
$delete = $statement->execute();
```

## MySQL Dump

[MySQL Dump mit praxisnahen Beispielen einfach erklärt](https://mizine.de/html/import-sql-dump-via-terminal/)

Export

```
mysqldump -uroot -p serienguide > serienguide.sql
```

Import

```
mysql -uroot -p serienguide < serienguide.sql
```

## Prefix for all tables
  
[How to add prefix of all tables in mysql](https://stackoverflow.com/questions/7970798/how-to-add-prefix-of-all-tables-in-mysql)

```sql
SELECT
    concat('ALTER TABLE ',db,'.',tb,' RENAME ',db,'.',prfx,tb,';')
FROM
    (SELECT table_schema db,table_name tb
    FROM information_schema.tables WHERE
    table_schema='serienguide') A,
    (SELECT 'legacy_' prfx) B;
```