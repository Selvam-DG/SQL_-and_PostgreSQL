# Creating the Database
- The first thing that we need to learn is to create a database
- The syntax to create a database is shown below:
  
          CREATE DATABASE name_of_database;

# Using the Database
- After we create a database, we have to let the DBMS know that we want to use this database. This is because the DBMS may be managing more than one databases concurrently. We have to let it know that all subsequent code that we write applies to the stated database.
- To do that, we use the following syntax:
 
          USE name_of_database;

# Deleting the Database
- Now, suppose after you create your database, you realise that you have typed the name wrongly. There is no easy way to rename a database in MySQL. What you can do is create a new database and delete the old database. To delete a database, we use the syntax
  
         DROP DATABASE [IF EXISTS] name_of_database;
# Creating Tables
- First, let’s look at how we can create tables to add to our database. To create a table, we use the following syntax:


            CREATE TABLE table_name (
              column_name1 datatype [column constraints],
              column_name2 datatype [column constraints],
              …
                [table constraints],
                [table constraints]
              );      

## Specifying Columns
- When we create the table, we need to specify the columns. For each column, we need to state the data type and any constraints that the column must satisfy.

### Data Types
- Data type refers to the type of data that the column stores
- Textual data types
 - Textual information, also known as strings, are commonly stored using the CHAR or VARCHAR data type in MySQL. They can contain letters, numbers or special characters.
 - CHAR(size)
 - VARCHAR(size)
- Numerical data types
  - INT
  - FLOAT(m,d)
    - In MySQL, you can specify two parameters - m and d - when defining FLOAT.
    - m refers to the total number of digits the FLOAT stores while d refers to the number of digits after the decimal point.
  - DOUBLE (m,d)
  - DECIMAL (m,d)
- Date and Time Data Types
  - YEAR
    -The YEAR data type is used to store a year in either a two-digit or a four-digit format. Values allowed in four-digit format are from 1901 to 2155. Values allowed in two-digit format are from 1 to 69 (representing years from 2001 to 2069) and 70 to 99 (representing years from 1970 to 1999).
  - DATE
    - The DATE datatype is used to store a date in the YYYY-MM-DD format, with a supported range of '1000-01-01' to '9999-12-31'
  - TIME
    - The TIME data type is used to store time in the HH:MI:SS format, with a supported range of '-838:59:59' to '838:59:59'.
  - DATETIME
    - The DATETIME data type is used to store a date and time combination in the YYYY-MM-DD HH:MI:SS format. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'.
  - TIMESTAMP
















