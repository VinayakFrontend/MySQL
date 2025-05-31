
# 📘 MySQL Database Commands

This document provides a quick reference to essential MySQL database operations, including creating, using, listing, backing up, restoring, and deleting databases.

---

## 📋 1. Show All Databases

```sql
SHOW DATABASES;
```

---

## 🆕 2. Create a New Database

```sql
CREATE DATABASE database_name;
```

*Example:*

```sql
CREATE DATABASE my_database;
```

---

## ✅ 3. Use a Database

```sql
USE database_name;
```

*Example:*

```sql
USE my_database;
```

---

## 🔍 4. Check Current Database

```sql
SELECT DATABASE();
```

---

## 📦 5. Backup (Export) a Database

Use the `mysqldump` tool in the terminal (not in SQL prompt):

```bash
mysqldump -u [username] -p [database_name] > [backup_file.sql]
```

*Example:*

```bash
mysqldump -u root -p my_database > my_database_backup.sql
```

---

## ♻️ 6. Restore Database from Backup

```bash
mysql -u [username] -p [database_name] < [backup_file.sql]
```

*Example:*

```bash
mysql -u root -p my_database < my_database_backup.sql
```

---

## 🗑️ 7. Drop (Delete) a Database

```sql
DROP DATABASE database_name;
```

*Example:*

```sql
DROP DATABASE my_database;
```

---

## ✅ Notes

- Always make a backup before dropping a database.
- Use `SHOW TABLES;` after selecting a database to view its contents.
- Use `EXIT;` to quit the MySQL shell.
