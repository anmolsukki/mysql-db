## DATA TYPE in MySQL

---

### 1. CHAR and VARCHAR

```sql
CREATE TABLE books (first_name VARCHAR(10), gender CHAR(1), quantity INT);
```

<strong>Note:</strong> <i>CHAR is for fixed length text</i>

---

### 2. DECIMAL

```sql
CREATE TABLE books (price DECIMAL(5, 2));
```

<strong>Note:</strong> <i>5 is is total number of digits and 2 is decimal</i>

```sql
INSERT INTO books (price) VALUES (7);           // 7.00
```

```sql
INSERT INTO books (price) VALUES (7987654);           // 999.99
```

```sql
INSERT INTO books (price) VALUES (34.88);           // 34.88
```

```sql
INSERT INTO books (price) VALUES (1.9999);           // 2.00
```

---

### 3. FLOAT

```sql
CREATE TABLE books (price FLOAT);
```

```sql
INSERT INTO books (price) VALUES (8877.45);           // 8877.45
```

```sql
INSERT INTO books (price) VALUES (8877665544.45);           // 8877670000
```

---

### 4. Dates & Times

```sql
CREATE TABLE student (name VARCHAR(25), birthdate DATE, birthtime TIME, birth_datetime DATETIME);
```

```sql
INSERT INTO student (name, birthdate, birthtime, birth_datetime) VALUES('Padma', '1983-11-11', '10:07:35', '1983-11-11 10:07:35');
```

<strong>CURDATE()</strong> - <i>Gives current date // (2023-07-24)</i>

<strong>CURTIME()</strong> - <i>Gives current time // (04:17:05)</i>

<strong>NOW()</strong> - <i>Gives current datetime // (2023-07-24 04:17:05)</i>

```sql
SELECT CURDATE();
```

```sql
INSERT INTO student (name, birthdate, birthtime, birth_datetime) VALUES('Naira', CURDATE(), CURTIME(), NOW());
```

```sql
SELECT name, DAY(birthdate), DAYNAME(birthdate), DAYOFWEEK(birthdate), DAYOFYEAR(birthdate) FROM student;      // Padma, 11, Friday, 5, 283
```

```sql
SELECT name, birthdate, MONTH(birthdate) FROM student;       // Padma, 1983-11-11, 11
```

```sql
SELECT name, birthdate, MONTHNAME(birthdate) FROM student;    // Padma, 1983-11-11, November
```

```sql
SELECT name, birthtime, HOUR(birthtime) FROM student;         // Padma, 10:07:35, 10
```

```sql
SELECT name, birthtime, MINUTE(birthtime) FROM student;       // Padma, 10:07:35, 7
```

```sql
SELECT DATE_FORMAT(birth_datetime, '%m/%d/%Y') FROM student;      // Padma, 11/11/1983
```

```sql
SELECT DATE_FORMAT(birth_datetime, '%m/%d/%Y at %h:%i') FROM student;     // Padma, 11/11/1983 at 10:07
```

<u>Date Difference</u>

```sql
SELECT name, DATEDIFF(NOW(), birthdate) FROM student;            // Padma, 14135
```

<u>Add Month in date</u>

```sql
SELECT name, DATE_ADD(birthdate, INTERVAL 1 MONTH) FROM student;         // Padma, 1983-12-11
```

<u>Add Second in date</u>

```sql
SELECT birthdate, DATE_ADD(birthdate, INTERVAL 10 SECOND) FROM student;           // 1983-11-11,   1983-11-11 00:00:10
```

<u>Add Quater in date</u>

```sql
SELECT birthdate, DATE_ADD(birthdate, INTERVAL 3 QUARTER) FROM student;             // 1983-11-11,  1984-08-11
```

<u>Add Multiple Field in date</u>

```sql
SELECT birthdate, birthdate + INTERVAL 15 MONTH + INTERVAL 10 HOUR FROM student;        // 1983-11-11,  1985-02-11 10:00:00
```

<u>Timestamp in SQL</u>

```sql
CREATE TABLE comments (content VARCHAR(100), created_at TIMESTAMP DEFAULT NOW(), updated_at TIMESTAMP DEFAULT NOW() ON UPDATE CURRENT_TIMESTAMP);
```

```sql
INSERT INTO comments (content) VALUES('I LIKE CATS AND DOGS');
```

<strong>comments:</strong> <i>I LIKE CATS AND DOGS</i>, <strong>created_at:</strong> <i>2022-07-24 02:32:30</i>, <strong>updated_at:</strong> <i>2022-07-24 02:32:30</i>

```sql
UPDATE comments SET content='THIS IS NOT GIBBERISH' WHERE content='I LIKE CATS AND DOGS';
```

<strong>comments:</strong> <i>THIS IS NOT GIBBERISH</i>, <strong>created_at:</strong> <i>2022-07-24 02:32:30</i>, <strong>updated_at:</strong> <i>2022-07-24 02:41:18</i>
