## Trigger Event

### 1. Create Database

```sql
CREATE DATABASE trigger_demo;
```

```sql
USE trigger_demo;
```

### 2. Create Tables

```sql
CREATE TABLE users (username VARCHAR(2100), age INT);
```

### 3. Insert data in tables

```sql
INSERT INTO users (username, age)
VALUES  ('bobby', 23);
```

### 4. Create Trigger for age validation

```sql
DELIMITER $$
CREATE TRIGGER must_be_adult
BEFORE INSERT ON users FOR EACH ROW
    BEGIN IF NEW.age < 18 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Must be an adult!';
    END IF;
END;
$$ DELIMITER ;
```
