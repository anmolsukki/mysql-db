## SHOP database

---

### 1. Create Database

```sql
CREATE DATABASE shop;

USE shop;
```

### 2. Create Tables

```sql
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(50)
);

CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    order_date DATE,
    amount DECIMAL(8,2),
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

### 3. Insert data in tables

```sql
INSERT INTO customers (first_name, last_name, email)
VALUES ('Boy', 'George', 'george@gmail.com'),
       ('George', 'Michael', 'gm@gmail.com'),
       ('David', 'Bowie', 'david@gmail.com'),
       ('Blue', 'Steele', 'blue@gmail.com'),
       ('Bette', 'Davis', 'bette@aol.com');


INSERT INTO orders (order_date, amount, customer_id)
VALUES ('2016-02-10', 99.99, 1),
       ('2017-11-11', 35.50, 1),
       ('2014-12-12', 800.67, 2),
       ('2015-01-03', 12.50, 2),
       ('1999-04-11', 450.25, 5);

INSERT INTO orders(order_date, amount, customer_id) VALUES('2022-11-11', 78.99, 3);
```

### 4. Find oders details

```sql
SELECT * FROM orders WHERE customer_id = (SELECT id FROM customers WHERE last_name = 'George');
```

### 5. Inner Join

```sql
SELECT * FROM customers JOIN orders ON orders.customer_id = customers.id;
```

```sql
SELECT first_name, last_name, order_date, amount FROM customers JOIN orders ON orders.customer_id = customers.id;
```

### 6. Inner Join with GROUP BY

```sql
SELECT first_name, last_name, SUM(amount) AS total FROM customers
JOIN orders ON orders.customer_id = customers.id
GROUP BY first_name , last_name
ORDER BY total;
```

### 7. LEFT JOIN

```sql
SELECT first_name, last_name, order_date, amount FROM customers
LEFT JOIN orders ON orders.customer_id = customers.id;
```

```sql
SELECT order_date, amount, first_name, last_name FROM customers
LEFT JOIN customers ON orders.customer_id = customers.id;
```

### 8. LEFT JOIN with GROUP BY

```sql
SELECT first_name, last_name, IFNULL(SUM(amount), 0) AS money_spent FROM customers
LEFT JOIN orders ON customers.id = orders.customer_id
GROUP BY first_name , last_name;
```

### 9. RIGHT JOIN

```sql
SELECT first_name, last_name, order_date, amount FROM customers
RIGHT JOIN orders ON customers.id = orders.customer_id;
```

### 8. DELETE Cascade

```sql
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(50)
);

CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    order_date DATE,
    amount DECIMAL(8,2),
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id) ON DELETE CASCADE
);
```
