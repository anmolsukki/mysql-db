## Window Functions

### 1. Create Database

```sql
CREATE DATABASE window_funcs;
```

```sql
USE window_funcs;
```

### 2. Create Tables

```sql
CREATE TABLE employees (emp_no INT PRIMARY KEY AUTO_INCREMENT, department VARCHAR(20), salary INT);
```

### 3. Insert data in tables

```sql
INSERT INTO employees (department, salary)
VALUES  ('engineering', 80000),
        ('engineering', 69000),
        ('engineering', 70000),
        ('engineering', 103000),
        ('engineering', 67000),
        ('engineering', 89000),
        ('engineering', 91000),
        ('sales', 59000),
        ('sales', 70000),
        ('sales', 159000),
        ('sales', 72000),
        ('sales', 60000),
        ('sales', 61000),
        ('sales', 61000),
        ('customer service', 38000),
        ('customer service', 45000),
        ('customer service', 61000),
        ('customer service', 40000),
        ('customer service', 31000),
        ('customer service', 56000),
        ('customer service', 55000);
```

### 4. Using OVER()

<strong>Note:</strong> <i>OVER return value in the respective of each Row</i>

```sql
SELECT emp_no, department, salary,
    AVG(salary) OVER() AS dept_avg,
    MIN(salary) OVER() AS dept_min,
    MAX(salary) OVER() AS dept_max
FROM employees;
```

### 5. PARTITION BY

```sql
SELECT emp_no, department, salary,
    AVG(salary) OVER(PARTITION BY department) AS dept_avg,
    AVG(salary) OVER() AS company_avg
FROM employees;
```

```sql
SELECT emp_no, department, salary,
    COUNT(*) OVER(PARTITION BY department) as dept_count
FROM employees;
```

### 6. RANK()

```sql
SELECT emp_no, department, salary,
    RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS dept_salary_rank,
    RANK() OVER(ORDER BY salary DESC) AS overall_salary_rank
FROM employees ORDER BY department;
```

### 7. ROW_NUMBER()

```sql
SELECT emp_no, department, salary,
    ROW_NUMBER() OVER(PARTITION BY department ORDER BY salary DESC) as dept_row_number,
    RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS dept_salary_rank,
    RANK() OVER(ORDER BY salary DESC) AS overall_salary_rank
FROM employees ORDER BY department;
```

### 8. DENSE_RANK()

```sql
SELECT emp_no, department, salary,
    ROW_NUMBER() OVER(PARTITION BY department ORDER BY salary DESC) as dept_row_number,
    RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS dept_salary_rank,
    RANK() OVER(ORDER BY salary DESC) AS overall_salary_rank,
    DENSE_RANK() OVER(ORDER BY salary DESC) as overall_dense_rank
FROM employees ORDER BY overall_salary_rank;
```
