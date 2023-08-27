## TV Shows database View & Modes

### 1. VIEW Examples

<strong>Note:</strong> <i>INSTEAD OF TYPING THIS QUERY ALL THE TIME</i>

```sql
SELECT title, released_year, genre, rating, first_name, last_name FROM reviews
JOIN series ON series.id = reviews.series_id
JOIN reviewers ON reviewers.id = reviews.reviewer_id;
```

<strong>Note:</strong> <i>WE CAN CREATE A VIEW</i>

```sql
CREATE VIEW full_reviews AS
SELECT title, released_year, genre, rating, first_name, last_name FROM reviews
JOIN series ON series.id = reviews.series_id
JOIN reviewers ON reviewers.id = reviews.reviewer_id;
```

<strong>Note:</strong> <i>NOW WE CAN TREAT THAT VIEW AS A VIRTUAL TABLE </i>

```sql
SELECT * FROM full_reviews;
```

```sql
SELECT * FROM full_reviews WHERE genre = 'Animation';
```

```sql
SELECT genre, AVG(rating) FROM full_reviews GROUP BY genre;
```

### 2. Create VIEW table

```sql
CREATE VIEW ordered_series AS SELECT * FROM series ORDER BY released_year;
```

### 3. Create or Replace VIEW table

```sql
CREATE OR REPLACE VIEW ordered_series AS SELECT * FROM series ORDER BY released_year DESC;
```

### 4. Alter VIEW table

```sql
ALTER VIEW ordered_series AS SELECT * FROM series ORDER BY released_year;
```

### 5. DROP VIEW table

```sql
DROP VIEW ordered_series;
```

### 6. HAVING clause

```sql
SELECT title, AVG(rating), COUNT(rating) AS review_count FROM full_reviews GROUP BY title HAVING COUNT(rating) > 1;
```

### 7. Show error or warning

```sql
SHOW WARNINGS;
```
