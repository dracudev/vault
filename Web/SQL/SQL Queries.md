Structured Query Language (SQL) is used to communicate with and manipulate databases. It allows users to perform tasks such as querying data, updating records, and managing database structures.

---

## Key SQL Statements

### 1. **SELECT**

Used to retrieve data from a database.

```sql
SELECT column1, column2 FROM table_name;
```

- **SELECT *** retrieves all columns.
    
- **WHERE** filters rows.
    
- **ORDER BY** sorts results.
    
- **LIMIT** restricts the number of rows returned.
    

### 2. **INSERT INTO**

Adds new data into a table.

```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
```

### 3. **UPDATE**

Modifies existing data.

```sql
UPDATE table_name SET column1 = value1 WHERE condition;
```

### 4. **DELETE**

Removes data from a table.

```sql
DELETE FROM table_name WHERE condition;
```

---

## Filtering and Conditions

### 1. **WHERE Clause**

Applies conditions to SQL statements.

```sql
SELECT * FROM Employees WHERE age > 30;
```

### 2. **Logical Operators**

- `AND`, `OR`, `NOT`
    
- Example:
    

```sql
SELECT * FROM Employees WHERE age > 30 AND department = 'HR';
```

### 3. **Comparison Operators**

- `=`, `!=`, `<>`, `<`, `>`, `<=`, `>=`
    

### 4. **BETWEEN**, **IN**, **LIKE**

- `BETWEEN`: Range
    
- `IN`: List of values
    
- `LIKE`: Pattern matching (use `%` as wildcard)
    

```sql
SELECT * FROM Products WHERE name LIKE 'A%';
```

---

## Joining Tables

Used to combine rows from two or more tables.

### 1. **INNER JOIN**

Returns rows when there is a match in both tables.

```sql
SELECT A.name, B.salary
FROM Employees A
INNER JOIN Salaries B ON A.id = B.emp_id;
```

### 2. **LEFT JOIN** / **RIGHT JOIN**

- `LEFT JOIN`: All rows from left table + matched rows from right table
    
- `RIGHT JOIN`: All rows from right table + matched rows from left table
    

### 3. **FULL OUTER JOIN**

All rows when there is a match in one of the tables.

### 4. **CROSS JOIN**

Returns Cartesian product of both tables.

---

## Grouping and Aggregation

### 1. **GROUP BY**

Groups rows sharing a property so aggregate functions can be applied.

```sql
SELECT department, COUNT(*) FROM Employees GROUP BY department;
```

### 2. **HAVING**

Filters groups (similar to WHERE but for aggregates).

```sql
SELECT department, COUNT(*) FROM Employees
GROUP BY department
HAVING COUNT(*) > 5;
```

### 3. **Aggregate Functions**

- `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
    

---

## Subqueries

A query inside another query.

```sql
SELECT name FROM Employees WHERE salary > (SELECT AVG(salary) FROM Employees);
```

---

## Creating and Modifying Tables

### 1. **CREATE TABLE**

```sql
CREATE TABLE Students (
  StudentID INT PRIMARY KEY,
  Name VARCHAR(100),
  Birthdate DATE
);
```

### 2. **ALTER TABLE**

Add, drop, or modify columns.

```sql
ALTER TABLE Students ADD Email VARCHAR(100);
```

### 3. **DROP TABLE**

Deletes a table.

```sql
DROP TABLE Students;
```

---

## Keys and Constraints

### 1. **Primary Key**

Uniquely identifies a record.

### 2. **Foreign Key**

References the primary key of another table.

```sql
CREATE TABLE Enrollments (
  StudentID INT,
  CourseID INT,
  PRIMARY KEY (StudentID, CourseID),
  FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
  FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);
```

### 3. **Unique**, **Not Null**, **Check**, **Default**

- `UNIQUE`: Ensures all values in a column are different.
    
- `NOT NULL`: Ensures a column cannot have NULL values.
    
- `CHECK`: Ensures values meet a condition.
    
- `DEFAULT`: Provides a default value.
    

---

## Views

A virtual table based on a SQL query.

```sql
CREATE VIEW HighEarners AS
SELECT name, salary FROM Employees WHERE salary > 50000;
```

---

## Indexes

Improve query performance.

```sql
CREATE INDEX idx_name ON Employees(name);
```

---

