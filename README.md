

# SQL Queries Documentation

This repository contains essential SQL queries for database operations. Each query is briefly described for quick reference.

## Table of Contents
- [Create Table](#create-table)
- [Insert Data](#insert-data)
- [Select Data](#select-data)
- [Update Data](#update-data)
- [Delete Data](#delete-data)
- [Join Tables](#join-tables)
- [Aggregate Functions](#aggregate-functions)
- [Order and Limit](#order-and-limit)
- [Search Query](#search-query)
- [Alter Table](#alter-table)

---

### Create Table
```sql
CREATE TABLE table_name (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
**Description:**  
This query creates a new table with fields `id`, `name`, `age`, and `created_at`. The `id` is auto-incremented and serves as the primary key.

---

### Insert Data
```sql
INSERT INTO table_name (name, age) VALUES ('John Doe', 25);
```
**Description:**  
Inserts a new row into the table with the values for `name` and `age`. 

---

### Select Data
```sql
SELECT * FROM table_name;
```
**Description:**  
Fetches all data from the specified table.

```sql
SELECT name, age FROM table_name WHERE age > 20;
```
**Description:**  
Selects specific columns (`name` and `age`) where the `age` is greater than 20.

---

### Update Data
```sql
UPDATE table_name SET age = 26 WHERE name = 'John Doe';
```
**Description:**  
Updates the `age` field for the row where `name` is 'John Doe'.

---

### Delete Data
```sql
DELETE FROM table_name WHERE id = 1;
```
**Description:**  
Deletes the row with a specific `id`.

---

### Join Tables
```sql
SELECT a.name, b.order_date 
FROM customers a 
INNER JOIN orders b 
ON a.id = b.customer_id;
```
**Description:**  
Performs an inner join to retrieve data from two related tables (`customers` and `orders`).

---

### Aggregate Functions
```sql
SELECT COUNT(*) FROM table_name;
```
**Description:**  
Counts the total number of rows in a table.

```sql
SELECT AVG(age) FROM table_name;
```
**Description:**  
Calculates the average `age` from the table.

---

### Order and Limit
```sql
SELECT name, age FROM table_name ORDER BY age DESC LIMIT 5;
```
**Description:**  
Selects `name` and `age`, orders the result by `age` in descending order, and limits the output to 5 rows.

---

### Search Query
```sql
SELECT * FROM table_name WHERE name LIKE '%Doe%';
```
**Description:**  
Searches for records where the `name` contains 'Doe'.

---

### Alter Table
```sql
ALTER TABLE table_name ADD COLUMN email VARCHAR(255);
```
**Description:**  
Adds a new column `email` to the existing table.

```sql
ALTER TABLE table_name DROP COLUMN email;
```
**Description:**  
Removes the `email` column from the table.

---

### Conclusion

These SQL queries cover common database operations. For more complex queries, refer to specific database documentation or consult an SQL guide. **Make sure to test each query in your development environment before running it in production.**

