SQL Server Tutorial: Relational Databases and SQL
This tutorial provides a comprehensive guide to using SQL Server, covering relational databases, SQL syntax, DDL/DML operations, data types, constraints, keys, joins, subqueries, CTEs, views, indexes, transactions, and ACID properties.

Table of Contents
  •	Relational Databases Overview
  •	SQL Syntax & DDL/DML Operations
  •	Data Types, Constraints, Primary/Foreign Keys
  •	Joins (INNER, LEFT, RIGHT, FULL)
  •	Subqueries and Common Table Expressions (CTEs)
  •	Views and Indexes
  •	Transactions & ACID Properties

Relational Databases Overview
A relational database organizes data into tables, where each table represents an entity, rows represent instances, and columns define attributes. SQL Server is a relational database management system (RDBMS) by Microsoft for managing structured data.
Key Concepts:
  •	Tables: Store data in rows and columns.
  •	Relationships: Linked via keys (primary/foreign keys).
  •	Schema: Defines the database structure.
  •	Normalization: Eliminates redundancy and ensures data integrity.
Example: A bookstore database with Books, Authors, and Orders tables linked by keys.
SQL Syntax & DDL/DML Operations
SQL (Structured Query Language) interacts with SQL Server databases, divided into:
  •	DDL (Data Definition Language): Modifies database structure.
  •	DML (Data Manipulation Language): Manages data within tables.

DDL Operations
Define or modify database objects.
•	CREATE: Creates a new object (e.g., table).
  CREATE TABLE Authors (
      AuthorID INT PRIMARY KEY,
      FirstName NVARCHAR(50),
      LastName NVARCHAR(50)
  );
  •	ALTER: Modifies an existing object.
  •	ALTER TABLE Authors ADD Email NVARCHAR(100);
  •	DROP: Deletes an object.
  •	DROP TABLE Authors;
  •	TRUNCATE: Removes all rows but retains structure.
  •	TRUNCATE TABLE Authors;

DML Operations
Manipulate data within tables.
  •	INSERT: Adds new rows.
    INSERT INTO Authors (AuthorID, FirstName, LastName, Email)
    VALUES (1, 'Jane', 'Doe', 'jane.doe@email.com');
  •	UPDATE: Modifies rows.

UPDATE Authors
  SET Email = 'jane.new@email.com'
  WHERE AuthorID = 1;
•	DELETE: Removes rows.
	DELETE FROM Authors WHERE AuthorID = 1;

•	SELECT: Retrieves data.
  SELECT FirstName, LastName FROM Authors WHERE AuthorID = 1;
  Data Types, Constraints, Primary/Foreign Keys
  Data Types

SQL Server supports various data types:
  •	Numeric: INT, BIGINT, DECIMAL(p,s), FLOAT.
  •	String: CHAR(n), VARCHAR(n), NVARCHAR(n) (Unicode).
  •	Date/Time: DATE, DATETIME, TIME.
  •	Binary: BINARY, VARBINARY.
  •	Others: BIT, UNIQUEIDENTIFIER, XML.
Example:
  CREATE TABLE Books (
      BookID INT,
      Title NVARCHAR(100),
      Price DECIMAL(10,2),
      PublicationDate DATE
  );
Constraints
Enforce data rules.
•	NOT NULL: Prevents NULL values.
    CREATE TABLE Authors (
        AuthorID INT NOT NULL,
        FirstName NVARCHAR(50) NOT NULL
    );

•	UNIQUE: Ensures unique values.
	ALTER TABLE Authors ADD CONSTRAINT UK_Email UNIQUE (Email);

•	CHECK: Ensures values meet a condition.
	ALTER TABLE Books ADD CONSTRAINT CHK_Price CHECK (Price > 0);

•	DEFAULT: Sets a default value.
ALTER TABLE Books ADD CONSTRAINT DF_PublicationDate DEFAULT GETDATE() FOR PublicationDate;
Primary Key
Uniquely identifies rows, cannot be NULL.
  CREATE TABLE Authors (
      AuthorID INT PRIMARY KEY,
      FirstName NVARCHAR(50)
  );
Foreign Key
Links tables by referencing a primary key.
  CREATE TABLE Books (
      BookID INT PRIMARY KEY,
      Title NVARCHAR(100),
      AuthorID INT,
      FOREIGN KEY (AuthorID) REFERENCES Authors(AuthorID)
  );

Joins (INNER, LEFT, RIGHT, FULL)
Joins combine rows from multiple tables based on a related column.
INNER JOIN
  Returns matching rows from both tables.
    SELECT a.FirstName, b.Title
    FROM Authors a
INNER JOIN Books b ON a.AuthorID = b.AuthorID;
LEFT JOIN
  Returns all rows from the left table, with NULLs for non-matching right table rows.
  SELECT a.FirstName, b.Title
  FROM Authors a

LEFT JOIN Books b ON a.AuthorID = b.AuthorID;
RIGHT JOIN
  Returns all rows from the right table, with NULLs for non-matching left table rows.
  SELECT a.FirstName, b.Title
  FROM Authors a

RIGHT JOIN Books b ON a.AuthorID = b.AuthorID;
FULL JOIN
Returns all rows from both tables, with NULLs where there is no match.
  SELECT a.FirstName, b.Title
  FROM Authors a
  FULL JOIN Books b ON a.AuthorID = b.AuthorID;

Sample Data:
-- Authors
  INSERT INTO Authors VALUES (1, 'Jane', 'Doe', 'jane@email.com');
  INSERT INTO Authors VALUES (2, 'John', 'Smith', 'john@email.com');

-- Books
  INSERT INTO Books VALUES (101, 'SQL Basics', 1, '2023-01-01');
  INSERT INTO Books VALUES (102, 'Advanced SQL', 1, '2024-01-01');
  INNER JOIN Result:
    FirstName	Title
    Jane	SQL Basics
    Jane	Advanced SQL
    LEFT JOIN Result:
    FirstName	Title
    Jane	SQL Basics
    Jane	Advanced SQL
    John	NULL

Subqueries and Common Table Expressions (CTEs)
Subqueries
A query nested within another query.

•	Single-row subquery:
  SELECT Title
  FROM Books
  WHERE AuthorID = (SELECT AuthorID FROM Authors WHERE FirstName = 'Jane');
•	Multi-row subquery:
SELECT Title
  FROM Books
  WHERE AuthorID IN (SELECT AuthorID FROM Authors WHERE LastName LIKE 'D%');
  Common Table Expressions (CTEs)
  Temporary result sets for use within a query.
  WITH AuthorBooks AS (
      SELECT a.FirstName, b.Title
      FROM Authors a
      INNER JOIN Books b ON a.AuthorID = b.AuthorID
  )
  SELECT FirstName, Title
  FROM AuthorBooks
  WHERE FirstName = 'Jane';
Benefits:
•	Enhances readability.
•	Supports recursive queries for hierarchical data.

Views and Indexes
Views
  Virtual tables based on SELECT queries.
  CREATE VIEW AuthorBookView AS
  SELECT a.FirstName, a.LastName, b.Title
  FROM Authors a
  INNER JOIN Books b ON a.AuthorID = b.AuthorID;

-- Query the view
SELECT * FROM AuthorBookView;
Use Cases:
    •	Simplify complex queries.
    •	Restrict column access.

Indexes
Improve query performance.
•	Clustered Index: Defines physical data order (one per table).
  CREATE CLUSTERED INDEX IX_Books_BookID
  ON Books(BookID);
•	Non-Clustered Index: Separate structure pointing to data.
  CREATE NONCLUSTERED INDEX IX_Authors_LastName
  ON Authors(LastName);

Notes:
  •	Indexes speed up SELECT but slow down INSERT/UPDATE/DELETE.
  •	Remove with:
  	DROP INDEX IX_Authors_LastName ON Authors;

Transactions & ACID Properties

Transactions
  A sequence of operations treated as a single unit.
  BEGIN TRANSACTION;
  INSERT INTO Authors (AuthorID, FirstName, LastName) VALUES (3, 'Alice', 'Brown');
  UPDATE Books SET AuthorID = 3 WHERE BookID = 101;
  COMMIT;

•	ROLLBACK: Undoes changes on error.
  BEGIN TRANSACTION;
  INSERT INTO Authors VALUES (4, 'Bob', 'Green', 'bob@email.com');
-- Error occurs

ROLLBACK;
•	SAVEPOINT: Allows partial rollback.
  BEGIN TRANSACTION;
  INSERT INTO Authors VALUES (5, 'Carol', 'White', 'carol@email.com');
  SAVE TRANSACTION SavePoint1;
  UPDATE Authors SET FirstName = 'Caroline' WHERE AuthorID = 5;
  ROLLBACK TRANSACTION SavePoint1;
  COMMIT;

ACID Properties
Transactions ensure reliability via:
  •	Atomicity: All operations complete or none are applied.
  •	Consistency: Database remains valid before/after transactions.
  •	Isolation: Transactions execute independently.
  •	SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
  •	Durability: Committed changes are permanently saved.

Example with Error Handling:
  BEGIN TRY
      BEGIN TRANSACTION;
      INSERT INTO Authors VALUES (6, 'David', 'Lee', 'david@email.com');
      INSERT INTO Books VALUES (103, 'Database Design', 6, '2025-01-01');
      COMMIT;
  END TRY
  BEGIN CATCH
      ROLLBACK;
      PRINT ERROR_MESSAGE();
  END CATCH;

Getting Started
  To practice, install SQL Server and SQL Server Management Studio (SSMS). Create a sample database and run the provided SQL scripts. For further learning, explore advanced      topics like stored procedures or triggers.
  For questions, open an issue in this repository or contact the maintainer.

