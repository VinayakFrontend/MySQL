
# 📘 MySQL Clauses – Syntax, Examples, and Output

This guide covers essential **MySQL clauses** including WHERE, ORDER BY, GROUP BY, HAVING, LIMIT, and more, with syntax, examples, and sample output.

---

## 1. 🔍 WHERE Clause

**Syntax:**
```sql
SELECT columns FROM table_name WHERE condition;
```

**Example:**
```sql
SELECT * FROM students WHERE age > 18;
```

**Output:**
```
+----+--------+-----+
| id | name   | age |
+----+--------+-----+
| 2  | Alice  | 19  |
| 4  | David  | 21  |
+----+--------+-----+
```

---

## 2. 📊 ORDER BY Clause

**Syntax:**
```sql
SELECT columns FROM table_name ORDER BY column ASC|DESC;
```

**Example:**
```sql
SELECT * FROM students ORDER BY age DESC;
```

**Output:**
```
+----+--------+-----+
| id | name   | age |
+----+--------+-----+
| 4  | David  | 21  |
| 2  | Alice  | 19  |
| 3  | Bob    | 17  |
+----+--------+-----+
```

---

## 3. 🧮 GROUP BY Clause

**Syntax:**
```sql
SELECT column, aggregate_function(column) FROM table_name GROUP BY column;
```

**Example:**
```sql
SELECT department, COUNT(*) FROM employees GROUP BY department;
```

**Output:**
```
+-------------+----------+
| department  | COUNT(*) |
+-------------+----------+
| HR          | 2        |
| Sales       | 3        |
| IT          | 4        |
+-------------+----------+
```

---

## 4. 🧪 HAVING Clause

**Syntax:**
```sql
SELECT column, aggregate_function(column) FROM table_name 
GROUP BY column HAVING condition;
```

**Example:**
```sql
SELECT department, COUNT(*) AS total FROM employees 
GROUP BY department HAVING total > 2;
```

**Output:**
```
+-------------+-------+
| department  | total |
+-------------+-------+
| IT          | 4     |
| Sales       | 3     |
+-------------+-------+
```

---

## 5. ⛔ LIMIT Clause

**Syntax:**
```sql
SELECT columns FROM table_name LIMIT number;
```

**Example:**
```sql
SELECT * FROM students LIMIT 2;
```

**Output:**
```
+----+--------+-----+
| id | name   | age |
+----+--------+-----+
| 1  | John   | 18  |
| 2  | Alice  | 19  |
+----+--------+-----+
```

---

## 6. 🧩 DISTINCT Clause

**Syntax:**
```sql
SELECT DISTINCT column FROM table_name;
```

**Example:**
```sql
SELECT DISTINCT department FROM employees;
```

**Output:**
```
+-------------+
| department  |
+-------------+
| HR          |
| Sales       |
| IT          |
+-------------+
```

---

## 🧪 Combined Example

```sql
SELECT department, COUNT(*) AS total
FROM employees
WHERE salary > 30000
GROUP BY department
HAVING total > 1
ORDER BY total DESC
LIMIT 3;
```

**Output:**
```
+-------------+-------+
| department  | total |
+-------------+-------+
| IT          | 4     |
| Sales       | 2     |
+-------------+-------+
```

---

📌 **Note:** Use clauses in the correct order: `SELECT` → `FROM` → `WHERE` → `GROUP BY` → `HAVING` → `ORDER BY` → `LIMIT`.
