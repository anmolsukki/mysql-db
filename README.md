## Start databse CLI

```sql
mysql-ctl cli
```

---

## Create a database

```sql
CREATE DATABASE database_name;
```

---

## Show database

```sql
SHOW DATABASES;
```

---

## Delete database

```sql
DROP DATABASE database_name;
```

---

## Use databae

```sql
USE database_name;
```

---

## Check current database

```sql
SELECT DATABASE();
```

---

## Create a table

```sql
CREATE TABLE table_name (column_name data_type, column_name data_type);
```

---

## Show tables

```sql
SHOW TABLES;
```

---

## Show columns from tables OR Descibe tables

```sql
SHOW COLUMNS FROM table_name;
```

```sql
DESC table_name;
```

---

## Delete table

```sql
DROP TABLE table_name;
```

---

## Insert data into table

```sql
INSERT INTO table_name(column_name1, column_name2) VALUES(value1, value2);
```

---

## View data from table

```sql
SELECT * FROM database_name.table_name;
```

```sql
SELECT * FROM table_name;
```

---

## View data from table particular column

```sql
SELECT column_name1, column_name2 FROM table_name;
```

```sql
SELECT name, age FROM cats;
```

---

## WHERE clause (Get data from table with condition)

```sql
SELECT * FROM table_name WHERE column_name1 = value1;
```

```sql
SELECT * FROM cats WHERE age = 4;
```

---

## Aliases (Give a name to a column)

```sql
SELECT column_name1 AS alias_name1, column_name2 AS alias_name2 FROM table_name;
```

```sql
SELECT cat_id AS id, name AS cat_name FROM cats;
```

---

## Multiple insert data into table

```sql
INSERT INTO table_name(column_name1, column_name2) VALUES(value1, value2), (value1, value2);
```

---

## Show warnings

```sql
SHOW WARNINGS;
```

---

## Prevent null values insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 NOT NULL, column_name2 data_type2 NOT NULL);
```

---

## Default value insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 DEFAULT default_value1, column_name2 data_type2 DEFAULT default_value2);
```

---

## Prevent null and default value insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 NOT NULL DEFAULT default_value1, column_name2 data_type2 NOT NULL DEFAULT default_value2);
```

---

## Primer on Primary Key

```sql
CREATE TABLE table_name (column_name1 data_type1 PRIMARY KEY, column_name2 data_type2);
```

```sql
CREATE TABLE person (person_id INT NOT NULL, name VARCHAR(50), age INT, PRIMARY KEY (person_id));
```

---

## Auto increment primary key

```sql
CREATE TABLE table_name (column_name1 data_type1 AUTO_INCREMENT, column_name2 data_type2);
```

```sql
CREATE TABLE person (person_id INT NOT NULL AUTO_INCREMENT, name VARCHAR(50), age INT, PRIMARY KEY (person_id));
```

```sql
INSERT INTO person (name, age) VALUES ('John', 20);
```

---

## UPDATE data in table

```sql
UPDATE table_name SET column_name1 = value1 WHERE column_name2 = value2;
```

```sql
UPDATE cats SET breed = 'shorthair' WHERE breed = 'Tabby';
```

---

## DELETE data from table

```sql
DELETE FROM table_name WHERE column_name1 = value1;
```

```sql
DELETE FROM cats WHERE breed = 'Tabby';
```

---

## CONCAT String in SQL

```sql
SELECT CONCAT(column_name1, column_name2) FROM table_name AS alias_name;
```

```sql
SELECT CONCAT(firstname, lastname) FROM authors AS fullname;
```

---

## CONCAT_WS in SQL

```sql
SELECT CONCAT_WS(' - ', column_name1, column_name2, column_name3) FROM table_name;
```

---

## SUBSTRING in SQL

```sql
SELECT SUBSTRING(column_name1, 1, 2) FROM table_name;
```

```sql
SELECT SUBSTRING('Hello World', 1, 5) FROM table_name;
```
