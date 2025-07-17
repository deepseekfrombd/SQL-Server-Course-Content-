# SQL Server Tutorial: Relational Databases and SQL

This tutorial provides a comprehensive guide to using SQL Server, covering relational databases, SQL syntax, DDL/DML operations, data types, constraints, keys, joins, subqueries, CTEs, views, indexes, transactions, and ACID properties.

## Table of Contents

* [Relational Databases Overview](#relational-databases-overview)
* [SQL Syntax & DDL/DML Operations](#sql-syntax--ddldml-operations)
* [Data Types, Constraints, Primary/Foreign Keys](#data-types-constraints-primaryforeign-keys)
* [Joins (INNER, LEFT, RIGHT, FULL)](#joins-inner-left-right-full)
* [Subqueries and Common Table Expressions (CTEs)](#subqueries-and-common-table-expressions-ctes)
* [Views and Indexes](#views-and-indexes)
* [Transactions & ACID Properties](#transactions--acid-properties)
* [Database Design Concepts for Freelancers](#database-design-concepts-for-freelancers)
* [Stored Procedures, Functions, and Triggers](#stored-procedures-functions-and-triggers)
* [Getting Started](#getting-started)

---

## Relational Databases Overview

... *(content unchanged)* ...

---

## Database Design Concepts for Freelancers

Designing scalable, normalized databases is a crucial freelance skill. Below are essential concepts with short theory and hands-on notes.

### ER Diagram Design

**Theory:**

* An Entity-Relationship (ER) diagram visually maps out entities (tables) and their relationships.
* Entities = tables, Attributes = columns, Relationships = foreign key links.

**Hands-On:**

* Tools: dbdiagram.io, DrawSQL, Lucidchart.
* Example:

```
[Authors] --< [Books] --< [Orders]
```

* Primary keys connect to foreign keys in child tables.

### Normalization (1NF to 3NF)

**Theory:**
Normalization organizes data to reduce redundancy and improve integrity.

* **1NF**: Atomic values (no repeating groups).
* **2NF**: Remove partial dependencies (non-key columns depend on full PK).
* **3NF**: Remove transitive dependencies (non-key columns depend only on the PK).

**Hands-On:**
**Unnormalized Table:**

| OrderID | CustomerName | Product1 | Product2 |
| ------- | ------------ | -------- | -------- |
| 1       | Alice        | Apple    | Banana   |

**1NF:** Separate products into rows.

```sql
OrderID | CustomerName | Product
1       | Alice         | Apple
1       | Alice         | Banana
```

**2NF & 3NF:** Split into `Customers`, `Orders`, and `Products` tables with relationships.

### Keys and Relationships

**Theory:**

* **Primary Key (PK)**: Uniquely identifies a record.
* **Foreign Key (FK)**: Links one table to another.
* **Composite Key**: Uses multiple columns as a key.
* **One-to-Many**: Most common relationship in databases.

**Hands-On:**

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name NVARCHAR(100)
);

CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

### Physical vs Logical Design

**Theory:**

* **Logical Design**: Abstract model of the structure (ERD, entities, relationships).
* **Physical Design**: Implementation in SQL Server (tables, indexes, constraints).

**Hands-On:**

* Logical: Draw ERD using dbdiagram.io.
* Physical: Write the actual SQL schema with types and constraints.

**Example:**
Logical:

* Table: `Author`, Fields: `AuthorID`, `Name`
* Table: `Book`, Fields: `BookID`, `Title`, `AuthorID`

Physical:

```sql
CREATE TABLE Author (
    AuthorID INT PRIMARY KEY,
    Name NVARCHAR(100)
);
CREATE TABLE Book (
    BookID INT PRIMARY KEY,
    Title NVARCHAR(100),
    AuthorID INT,
    FOREIGN KEY (AuthorID) REFERENCES Author(AuthorID)
);
```

### ✅ Freelance Relevance: Designing Scalable Client Databases

* Helps clients avoid future data issues.
* Ensures extensibility and performance.
* Shows professionalism in proposals and documentation.
* Clients often need normalized, well-related tables for reporting and integrity.

---

## Stored Procedures, Functions, and Triggers

### CREATE/ALTER Procedures

**Theory:**

* Stored Procedures encapsulate SQL logic to execute multiple commands efficiently.
* Use `CREATE PROCEDURE` or `ALTER PROCEDURE` for versioning or updates.

**Hands-On:**

```sql
CREATE PROCEDURE GetCustomerOrders @CustomerID INT
AS
BEGIN
    SELECT * FROM Orders WHERE CustomerID = @CustomerID;
END;
```

### Parameters and Execution Logic

**Theory:**

* Procedures can take input, output, or return parameters.
* Enhance code reuse and security by avoiding dynamic SQL.

**Hands-On:**

```sql
EXEC GetCustomerOrders @CustomerID = 101;
```

### Scalar and Table-Valued Functions

**Theory:**

* **Scalar Functions** return a single value.
* **Table-Valued Functions (TVF)** return a result set.

**Hands-On:**

```sql
-- Scalar Function
CREATE FUNCTION GetFullName (@First NVARCHAR(50), @Last NVARCHAR(50))
RETURNS NVARCHAR(100)
AS
BEGIN
    RETURN @First + ' ' + @Last;
END;

-- Table-Valued Function
CREATE FUNCTION GetHighValueOrders (@MinAmount DECIMAL)
RETURNS TABLE
AS
RETURN (
    SELECT * FROM Orders WHERE TotalAmount >= @MinAmount
);
```

### AFTER/INSTEAD OF Triggers

**Theory:**

* Triggers run automatically on data changes.
* **AFTER** triggers execute after an insert/update/delete.
* **INSTEAD OF** triggers override the original action.

**Hands-On:**

```sql
-- AFTER Trigger
CREATE TRIGGER trg_AfterInsertOrder
ON Orders
AFTER INSERT
AS
BEGIN
    PRINT 'New order inserted';
END;

-- INSTEAD OF Trigger
CREATE TRIGGER trg_InsteadDeleteCustomer
ON Customers
INSTEAD OF DELETE
AS
BEGIN
    PRINT 'Deletion blocked - archival required first';
END;
```

### ✅ Freelance Relevance: Business Rule Automation, Server-Side Logic Development

* Automate complex business rules inside the database.
* Improve performance by reducing round trips.
* Secure and control logic centrally for client projects.

---

## Getting Started

... *(content unchanged)* ...
