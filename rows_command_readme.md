
# 📘 `rows` Command – SQL Syntax & Example Outputs

This guide shows how to use SQL commands to manage rows in a table with syntax examples and sample output for each operation.

---

### 🧾 Table Schema Example

```sql
CREATE TABLE users (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  email VARCHAR(100)
);
```

---

## 🔍 Show Records

**SQL Syntax:**
```sql
SELECT * FROM users;
```

**Example Output:**

| id | name      | email              |
|----|-----------|--------------------|
| 1  | Alice     | alice@mail.com     |
| 2  | Bob       | bob@mail.com       |

---

## ➕ Create a New Record

**SQL Syntax:**
```sql
INSERT INTO users (id, name, email)
VALUES (3, 'Charlie', 'charlie@mail.com');
```

**Example Output (confirmation):**
```
1 row inserted.
```

---

## ➕ Add Multiple Records

**SQL Syntax:**
```sql
INSERT INTO users (id, name, email)
VALUES 
  (4, 'David', 'david@mail.com'),
  (5, 'Eve', 'eve@mail.com');
```

**Example Output:**
```
2 rows inserted.
```

---

## 🔄 Update One Record

**SQL Syntax:**
```sql
UPDATE users
SET email = 'alice.new@mail.com'
WHERE id = 1;
```

**Example Output:**
```
1 row updated.
```

---

## 🔁 Update All Records

**SQL Syntax:**
```sql
UPDATE users
SET email = 'updated@mail.com';
```

**Example Output:**
```
5 rows updated.
```

---

## ❌ Remove One Record

**SQL Syntax:**
```sql
DELETE FROM users
WHERE id = 2;
```

**Example Output:**
```
1 row deleted.
```

---

## ❌ Remove All Records

**SQL Syntax:**
```sql
DELETE FROM users;
```

**Example Output:**
```
All rows deleted from 'users'.
```

---

## ✅ Final Tip

Always run a `SELECT` first with the same `WHERE` condition before executing `UPDATE` or `DELETE`, to make sure only intended records are affected.
