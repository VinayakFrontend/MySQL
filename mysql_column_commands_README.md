
# 📘 MySQL Column Operations - README

This README provides a guide to managing columns in MySQL databases, including viewing, creating, renaming, modifying, and deleting columns, data types, and constraints.

---

## 📋 1. Show Columns

```sql
SHOW COLUMNS FROM table_name;
-- or --
DESCRIBE table_name;
```

Shows each column's name, data type, nullability, key status, default value, and extra info.

---

## ➕ 2. Create Columns (During Table Creation)

```sql
CREATE TABLE table_name (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE
);
```

Defines columns with data types and optional constraints during table creation.

---

## 🧱 3. Add Columns to Existing Table

```sql
ALTER TABLE table_name
ADD COLUMN new_column_name column_definition [AFTER existing_column];
```

**Example:**
```sql
ALTER TABLE employees
ADD COLUMN birth_date DATE AFTER name;
```

---

## ✏️ 4. Rename Column

```sql
ALTER TABLE table_name
CHANGE COLUMN old_name new_name column_definition;
```

**Example:**
```sql
ALTER TABLE employees
CHANGE COLUMN fullname name VARCHAR(100);
```

---

## ❌ 5. Remove (Drop) Column

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

**Example:**
```sql
ALTER TABLE employees
DROP COLUMN birth_date;
```

---

## 🔡 6. Add / Change Data Types

**Modify a column's data type:**

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name new_data_type;
```

**Example:**
```sql
ALTER TABLE employees
MODIFY COLUMN name VARCHAR(200);
```

---

## 🔐 7. Add Constraints

**Examples:**

- Primary Key:
  ```sql
  ALTER TABLE employees
  ADD PRIMARY KEY (id);
  ```

- Unique Constraint:
  ```sql
  ALTER TABLE employees
  ADD CONSTRAINT unique_email UNIQUE (email);
  ```

- Foreign Key:
  ```sql
  ALTER TABLE orders
  ADD CONSTRAINT fk_customer_id FOREIGN KEY (customer_id) REFERENCES customers(id);
  ```

- Not Null:
  ```sql
  ALTER TABLE employees
  MODIFY COLUMN name VARCHAR(100) NOT NULL;
  ```

---

## 🔄 8. Rename Constraint (Indirectly)

MySQL **does not support direct constraint renaming**. You must:

1. Drop the existing constraint
2. Re-add it with a new name

**Example:**
```sql
ALTER TABLE employees
DROP INDEX unique_email;

ALTER TABLE employees
ADD CONSTRAINT new_unique_email UNIQUE (email);
```

---

## ❌ 9. Remove Constraint

```sql
-- For foreign keys:
ALTER TABLE table_name
DROP FOREIGN KEY constraint_name;

-- For unique or index:
ALTER TABLE table_name
DROP INDEX index_name;
```

To find constraint/index names:
```sql
SHOW CREATE TABLE table_name;
```

---

## 🧼 10. Remove Data Type (Not Supported)

⚠️ MySQL does **not support removing a data type** — every column must have one. To change a type, use:

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name new_data_type;
```

---

## 🔁 11. Rename Data Type (Change Column Type)

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name new_data_type;
```

**Example:**
```sql
ALTER TABLE employees
MODIFY COLUMN salary DECIMAL(10,2);
```

---

## 🧨 12. Delete Column (Again)

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

Use `SHOW COLUMNS` before deleting to avoid accidental data loss.

---

# ✅ Tips

- Always **back up your table** before modifying column structure.
- Use `SHOW CREATE TABLE table_name;` to view the full structure including constraints.
- Use `INFORMATION_SCHEMA` for programmatic access to metadata.
