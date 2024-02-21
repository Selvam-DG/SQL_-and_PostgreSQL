# SQL
- SQL is structured Query Language which is a computer language for storing, manipulating and retrieving data stored in relational databases.
- SQL is the standard language for Relation Database System.
- All relational database management systems like MySQL, MS Access, Oracle, SQL Server, PostgreSQL uses SQL as standard database language

### Why SQL?
- Allow users to access data in relational database management systems
- allow users to describe the data
- Allow users to define the data in the database and manipulate the data
- Allow users to create and drop the database and tables
### SQL process
- SQLQuery
- Query Language Processor
- DBMS Engine
- Database 
### Categories of SQL Statements:
1. DDL = Data Definition Language => Create, Alter, Drop
2. DML = Data Manipulation Language => Insert, Update, Delete
3. DQL = Data Query Language => Select
4. Data Control Language => Grant, Revoke
-   **CRUD** rule is CREATE, READ, UPDATE, DELETE
- RDBMS - The software used to store, manage, query, and retrieve data stored in a relational database is called a relational database management system (RDBMS)

### CREATE Statement:
- CREATE DATABASE database_name;
  - For example: CREATE DATABASE Demo;
  - use test;
- CREATE TABLE table_name
  - for example:
  - CREATE TABLE test_table(
  - column1 datatype (Size),
  - column2 datatype (Size),
  - column3 datatype,
  - .....
  - column datatype);
### INSERT  Statement 
- INSERT INTO table_EID ( column1, column2....columnN)
  VALUES ( value1, value2....valueN); 

### SQL SELECT Statement 
- SELECT * FROM table_EID;
  - selecting rows and columns from the table
- SELECT column1, column2,.....,columnN FROM table_name;

## SQL Data Types 
### Numerical Data Types
- int (-2147483648, 2147483647)
- small int (-32768, 32767)
- Decimal (-10^38 +1, 10^38 +1)
- Money (-922337203685477.5808, +922337203685477.5807)  
- Float (-1.79E + 308, 1.79E + 308)
### Character Data Types:
- Char
- Varchar
- Text
### Date & Time Data Types: 
- Datetime
- Smalldatetime
- Date
- Time
### Misc Data Type:
- Image
### SQL CLAUSES
- SQL WHERE Clause
  - SELECT column1, column2....columnN FROM table_EID WHERE  CONDITION; 
- SQL LIKE Clause
  - SELECT column1, column2....columnN FROM table_EID WHERE column LIKE 'XXXX%‘
  - SELECT FROM table_EID WHERE column LIKE 'XXXX_' 
  - There are two wildcards used in conjunction with the LIKE operator:
    - The percent sign (%)
    - The underscore (_)
- SQL TOP Clause
    - SELECT TOP number|percent column_name(s) FROM table_name WHERE [condition]

### SQL Statements
- SQL UPDATE Statement
  - UPDATE table_name
    SET column1 = value1, column2 = value2....columnN=valueN
    [ WHERE  CONDITION ];
- SQL DELETE Statement
  - DELETE FROM table_name WHERE  {CONDITION};
  - DELETE FROM table_name;
  - DELETE table_name; 
- SQL ALTER TABLE Statement
  - ALTER TABLE table_name, ADD column_name {data_type};
  - ALTER TABLE table_name DROP Column column_name;
  - ALTER TABLE table_name ALTER Column column_name {data_type};
- SQL DROP TABLE Statement
  - DROP TABLE table_name;
  - DROP DATABASE database_name; 
- SQL TRUNCATE TABLE Statement
  - TRUNCATE TABLE table_name; 
- SQL COMMIT Statement
- SQL ROLLBACK Statement
### SQL Operators 
- An operator is a reserved word or a character used primarily in a SQL statement where a clause performs operations such as comparisons and arithmetic operations.
- Operators are used to specify conditions in an SQL statement
- Arithmetic Operators (+, -, /, *, %)
- Comparison Operators (=, <>, !=, >, <, >= ,<=, !>, !<)
- Logical Operators (AND, OR, NOT)
- Other Operators (BETWEEN, IN, LIKE, IS NULL, DISTINCT, EXISTS )

### Normalization 
- Database normalization is the process of efficiently organizing data in a database.  It is a set or rules/guidelines/statements that we follow while storing the data.
-  There are two reasons for the normalization process:
  - Eliminating redundant data, for example, storing the same data in more than one tables.
  - Ensuring data dependencies make sense.
- **First Normal Form (1NF)**:
  - Define the data items. This means looking at the data to be stored, organizing the data into columns, defining what type of data each column contains, and finally putting related columns into their own table.
  - Ensure that there are no repeating groups of data
  - Ensure that there is a primary key.
- **Second Normal Form (2NF)**
  - It should meet all the rules for 1NF
  - There must be no partial dependencies of any of the columns on the primary key    
- **Third Normal Form (3NF)**
  - It should meet all the rules for 2NF
  - Tables should have a relationship. (one-to-one, one-to-many, many-to-one, many-to-many relationships)

### SQL Constraints:
- Constraints are the rules enforced on data columns on a table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database.
- The following are commonly used constraints available in SQL:
  - **PRIMARY Key**: Uniquely identified each row/record in a database table.
  - **UNIQUE Constraint**: Ensures that all values in a column are different.
  - **NOT NULL Constraint**: Ensures that a column cannot have a NULL value.
  - **DEFAULT Constraint**: Provides a default value for a column when none is specified.
  - **CHECK Constraint**: The CHECK constraint ensures that all values in a column satisfy certain conditions.
  - **FOREIGN Key**: Uniquely identified rows/records in any other database table.  








##### PRIMARY KEY Constraint: 
- A primary key is a field in a table that uniquely identifies each rows/records in a database table. Primary keys must contain unique values. A primary key column cannot have NULL values.
- A table can have only one primary key which may consist of single or multiple fields. When multiple fields are used as a primary key, they are called a composite key.
- Syntax:
  - CREATE TABLE SALESS(
    - ID   INT
    - NOT NULL,
    - EID VARCHAR (20)     NOT NULL,
    - AGE  INT  NOT NULL,
    - ADDRESS  CHAR (25),
    - SALARY   DECIMAL (18, 2),
    - PRIMARY KEY (ID) );
- Other syntax
  - ALTER TABLE SALES
    - ADD CONSTRAINT pkID  PRIMARY KEY (ID);
  - ALTER TABLE SALESS
    - DROP CONSTRAINT pkID;























