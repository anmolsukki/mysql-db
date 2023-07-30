## CONSTRAINT

---

### 1. Check CONSTRAINT

```sql
CREATE TABLE users ( username VARCHAR(20) NOT NULL, age INT CHECK (age > 5) );
```

### 2. Named CONSTRAINT

```sql
CREATE TABLE users1 ( username VARCHAR(20) NOT NULL, age INT, CONSTRAINT age_greater_five CHECK (age > 5) );
```

### 3. UNIQUE CONSTRAINT

<strong>Note:</strong> <i>Combination of name & address should not be same</i>

```sql
CREATE TABLE companies ( name VARCHAR(50) NOT NULL, address VARCHAR(255) NOT NULL, CONSTRAINT name_address UNIQUE (name , address) );
```

---

## ALTER Query

### 1. ADD Column

```sql
ALTER TABLE companies ADD COLUMN phone VARCHAR(15);
```

### 2. DROP Column

```sql
ALTER TABLE companies DROP COLUMN phone;
```

### 3. RENAME Table

```sql
RENAME TABLE companies to suppliers;
```

<i>--- OR ---</i>

```sql
ALTER TABLE suppliers RENAME TO companies;
```

### 4. RENAME Column

```sql
ALTER TABLE companies RENAME COLUMN name TO company_name;
```

### 5. MODIFY Column

```sql
ALTER TABLE companies MODIFY company_name VARCHAR(100) DEFAULT 'unknown';
```
