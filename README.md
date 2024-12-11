
### **Basic Commands**
1. **Create a Database**
   ```sql
   sqlite3 database_name.db
   ```

2. **Open a Database**
   ```sql
   .open database_name.db
   ```

3. **Show Tables in a Database**
   ```sql
   .tables
   ```

4. **Describe a Table (Schema)**
   ```sql
   PRAGMA table_info(table_name);
   ```

5. **Exit SQLite**
   ```sql
   .exit
   ```

---

### **Table Management**
1. **Create a Table**
   ```sql
   CREATE TABLE table_name (
       column1 datatype PRIMARY KEY,
       column2 datatype,
       column3 datatype
   );
   ```

2. **Drop a Table**
   ```sql
   DROP TABLE table_name;
   ```

3. **Alter a Table**
   - Add a column:
     ```sql
     ALTER TABLE table_name ADD COLUMN column_name datatype;
     ```
   - Rename a table:
     ```sql
     ALTER TABLE old_table_name RENAME TO new_table_name;
     ```

---

### **Data Manipulation**
1. **Insert Data**
   ```sql
   INSERT INTO table_name (column1, column2) VALUES (value1, value2);
   ```

2. **Insert Multiple Rows**
   ```sql
   INSERT INTO table_name (column1, column2)
   VALUES
       (value1, value2),
       (value3, value4);
   ```

3. **Select Data**
   - Select all columns:
     ```sql
     SELECT * FROM table_name;
     ```
   - Select specific columns:
     ```sql
     SELECT column1, column2 FROM table_name;
     ```

4. **Update Data**
   ```sql
   UPDATE table_name
   SET column1 = value1, column2 = value2
   WHERE condition;
   ```

5. **Delete Data**
   ```sql
   DELETE FROM table_name WHERE condition;
   ```

---

### **Filtering and Sorting**
1. **Where Clause**
   ```sql
   SELECT * FROM table_name WHERE column1 = value1;
   ```

2. **Like Clause (Search)**
   ```sql
   SELECT * FROM table_name WHERE column1 LIKE '%value%';
   ```

3. **Order By**
   ```sql
   SELECT * FROM table_name ORDER BY column1 ASC;
   SELECT * FROM table_name ORDER BY column1 DESC;
   ```

4. **Limit Results**
   ```sql
   SELECT * FROM table_name LIMIT number;
   ```

---

### **Joins**
1. **Inner Join**
   ```sql
   SELECT columns
   FROM table1
   INNER JOIN table2
   ON table1.column_name = table2.column_name;
   ```

2. **Left Join**
   ```sql
   SELECT columns
   FROM table1
   LEFT JOIN table2
   ON table1.column_name = table2.column_name;
   ```

3. **Right Join**
   SQLite does not support right joins directly, but you can switch the tables in a left join.

---

### **Aggregations**
1. **Count**
   ```sql
   SELECT COUNT(*) FROM table_name;
   ```

2. **Sum**
   ```sql
   SELECT SUM(column_name) FROM table_name;
   ```

3. **Average**
   ```sql
   SELECT AVG(column_name) FROM table_name;
   ```

4. **Group By**
   ```sql
   SELECT column_name, COUNT(*)
   FROM table_name
   GROUP BY column_name;
   ```

5. **Having**
   ```sql
   SELECT column_name, COUNT(*)
   FROM table_name
   GROUP BY column_name
   HAVING COUNT(*) > value;
   ```

---

### **Transactions**
1. **Start Transaction**
   ```sql
   BEGIN TRANSACTION;
   ```

2. **Commit Transaction**
   ```sql
   COMMIT;
   ```

3. **Rollback Transaction**
   ```sql
   ROLLBACK;
   ```

---

### **Indexing**
1. **Create Index**
   ```sql
   CREATE INDEX index_name ON table_name (column_name);
   ```

2. **Drop Index**
   ```sql
   DROP INDEX index_name;
   ```

---

### **Advanced**
1. **Create a View**
   ```sql
   CREATE VIEW view_name AS
   SELECT columns FROM table_name WHERE condition;
   ```

2. **Delete a View**
   ```sql
   DROP VIEW view_name;
   ```

3. **Execute Raw SQL**
   ```sql
   .read file_name.sql
   ```

4. **Vacuum the Database (Optimize)**
   ```sql
   VACUUM;
   ```

5. **Foreign Keys**
   - Enable foreign keys:
     ```sql
     PRAGMA foreign_keys = ON;
     ```
   - Create a table with foreign keys:
     ```sql
     CREATE TABLE table_name (
         column1 datatype PRIMARY KEY,
         column2 datatype,
         column3 datatype,
         FOREIGN KEY (column3) REFERENCES other_table(column)
     );
     ```
