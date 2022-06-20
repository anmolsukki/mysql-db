#### Start databse CLI

```sql
mysql-ctl cli
```

#### Create a database

```sql
CREATE DATABASE database_name;
```

#### Show database

```sql
SHOW DATABASES;
```

#### Delete database

```sql
DROP DATABASE database_name;
```

#### Use databae

```sql
USE database_name;
```

#### Check current database

```sql
SELECT DATABASE();
```

#### Create a table

```sql
CREATE TABLE table_name (column_name data_type, column_name data_type);
```

#### Show tables

```sql
SHOW TABLES;
```

#### Show columns from tables OR Descibe tables

```sql
SHOW COLUMNS FROM table_name;
```

```sql
DESC table_name;
```

#### Delete table

```sql
DROP TABLE table_name;
```

#### Insert data into table

```sql
INSERT INTO table_name(column_name1, column_name2) VALUES(value1, value2);
```

#### View data from table

```sql
SELECT * FROM database_name.table_name;
```

```sql
SELECT * FROM table_name;
```

#### Multiple insert data into table

```sql
INSERT INTO table_name(column_name1, column_name2) VALUES(value1, value2), (value1, value2);
```

#### Show warnings

```sql
SHOW WARNINGS;
```

#### Prevent null values insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 NOT NULL, column_name2 data_type2 NOT NULL);
```

#### Default value insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 DEFAULT default_value1, column_name2 data_type2 DEFAULT default_value2);
```

#### Prevent null and default value insert into table

```sql
CREATE TABLE table_name (column_name1 data_type1 NOT NULL DEFAULT default_value1, column_name2 data_type2 NOT NULL DEFAULT default_value2);
```

#### Primer on Primary Key

```sql
CREATE TABLE table_name (column_name1 data_type1 PRIMARY KEY, column_name2 data_type2);
```

```sql
CREATE TABLE person (person_id INT NOT NULL, name VARCHAR(50), age INT, PRIMARY KEY (person_id));
```

#### Auto increment primary key

```sql
CREATE TABLE table_name (column_name1 data_type1 AUTO_INCREMENT, column_name2 data_type2);
```

```sql
CREATE TABLE person (person_id INT NOT NULL AUTO_INCREMENT, name VARCHAR(50), age INT, PRIMARY KEY (person_id));
```

```sql
INSERT INTO person (name, age) VALUES ('John', 20);
```
