
# 📘 MySQL Table Operations – Syntax and Examples

---

## 1. 🔍 Show All Tables

**Syntax:**
```sql
SHOW TABLES;
```

**Example:**
```sql
SHOW TABLES;
```

**Output:**
```
+----------------+
| Tables_in_db   |
+----------------+
| users          |
| products       |
| orders         |
+----------------+
```

---

## 2. 🆕 Create a New Table

**Syntax:**
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```

**Example:**
```sql
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    enrolled_date DATE
);
```

---

## 3. 🔁 Rename a Table

**Syntax:**
```sql
RENAME TABLE old_table_name TO new_table_name;
```

**Example:**
```sql
RENAME TABLE students TO learners;
```

---

## 4. ✅ Check Table Status

**Syntax:**
```sql
SHOW TABLE STATUS LIKE 'table_name';
```

**Example:**
```sql
SHOW TABLE STATUS LIKE 'learners';
```

---

## 5. 💾 Backup a Table

> All commands are to be executed in a terminal/command prompt.

### a. 📦 Full Table Backup (Structure + Data)

**Syntax:**
```bash
mysqldump -u username -p database_name table_name > filename.sql
```

**Example:**
```bash
mysqldump -u root -p school learners > learners_full.sql
```

---

### b. 🧱 Only Structure Backup

**Syntax:**
```bash
mysqldump -u username -p -d database_name table_name > filename.sql
```

**Example:**
```bash
mysqldump -u root -p -d school learners > learners_structure.sql
```

---

### c. 🧾 Only Data Backup

**Syntax:**
```bash
mysqldump -u username -p --no-create-info database_name table_name > filename.sql
```

**Example:**
```bash
mysqldump -u root -p --no-create-info school learners > learners_data.sql
```

---

## 6. ♻️ Restore a Table

### a. 🔄 Full Restore

**Syntax:**
```bash
mysql -u username -p database_name < filename.sql
```

**Example:**
```bash
mysql -u root -p school < learners_full.sql
```

---

### b. 🔄 Structure Only Restore

**Example:**
```bash
mysql -u root -p school < learners_structure.sql
```

---

### c. 🔄 Data Only Restore

**Example:**
```bash
mysql -u root -p school < learners_data.sql
```

---

## 7. 🗑️ Drop a Table

**Syntax:**
```sql
DROP TABLE table_name;
```

**Example:**
```sql
DROP TABLE learners;
```

---

## 🧪 Full Use Case Example

```sql
-- Create table
CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255),
    author VARCHAR(255)
);

-- Rename table
RENAME TABLE books TO library_books;

-- Backup full table
-- Terminal command:
mysqldump -u root -p library library_books > library_books_full.sql

-- Drop table
DROP TABLE library_books;

-- Restore table
-- Terminal command:
mysql -u root -p library < library_books_full.sql;
```
