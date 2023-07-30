## Logical Operator in MySQL

---

### 1. Not Equal (!=) in MySQL

```sql
SELECT * FROM books WHERE release_year != 2021;
```

### 2. Not Like in MySQL

```sql
SELECT * FROM books WHERE title NOT LIKE '%Harry%';
```

```sql
SELECT * FROM books WHERE title LIKE 'Da%';            // Output: [start from ]: Da
```

### 3. Greater Than (>) in MySQL

```sql
SELECT * FROM books WHERE release_year > 2020;
```

### 4. LOGICAL AND (&&) in MySQL

```sql
SELECT * FROM books WHERE author_name = 'J.K. Rowling' AND release_year > 2020;
```

### 5. LOGICAL OR (||) in MySQL

```sql
SELECT * FROM books WHERE author_name = 'J.K. Rowling' OR release_year > 2020;
```

### 6. BETWEEN in MySQL

```sql
SELECT * FROM books WHERE release_year BETWEEN 2020 AND 2023;
```

### 7. NOT BETWEEN in MySQL

```sql
SELECT * FROM books WHERE release_year NOT BETWEEN 2020 AND 2023;
```

### 8. CAST in MySQL

```sql
SELECT * FROM books WHERE release_year = CAST('1983-11-11' AS DATETIME);
```

```sql
SELECT * FROM student WHERE birth_datetime BETWEEN CAST('1983-11-11' AS DATETIME) AND CAST('2000-01-01' AS DATETIME);
```

### 9. IN in MySQL

```sql
SELECT * FROM books WHERE author_name = 'J.K. Rowling' OR author_name = 'Carver';
```

```sql
SELECT * FROM books WHERE author_name IN ('J.K. Rowling', 'Carver');
```

### 10. NOT IN in MySQL

```sql
SELECT * FROM books WHERE author_name != 'J.K. Rowling' AND author_name != 'Carver';
```

```sql
SELECT * FROM books WHERE author_name NOT IN ('J.K. Rowling', 'Carver');
```

```sql
SELECT * FROM books WHERE release_year >= 2001 AND release_year NOT IN (2004, 2005, 2006);
```

### 11. MODULO in MySQL

```sql
SELECT * FROM books WHERE release_year >= 2000 AND release_year % 2 != 0;
```

<i>Get All books release year greater than 2000 and division by 2 not remender 0</i>

### 12. CASE in MySQL

```sql
SELECT title, name, CASE WHEN release_year >= 2000 THEN 'New Session Books' WHEN release_year >= 2010 THEN 'Modern Session Books' ELSE 'Old Session Books' END AS Session FROM books;
```

### 13. Start with in MySQL

<u>Select all book authot name start with C and S</u>

```sql
SELECT * FROM books WHERE author_name LIKE 'C%' OR author_name LIKE 'S%';
```

```sql
SELECT * FROM books WHERE SUBSTR(author_name, 1, 1) = 'C' OR SUBSTR(author_name, 1, 1) = 'S';
```

```sql
SELECT * FROM books WHERE SUBSTR(author_name, 1, 1) IN ('C', 'S');
```
