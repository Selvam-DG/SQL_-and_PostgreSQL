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
    - The TIMESTAMP data type is also used to store a date and time combination in the YYYY-MM-DD HH:MI:SS format. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC.

### Column Constraints
- NOT NULL
  - Specifies that a column cannot be empty. In other words, it must have a value for all rows.
- UNIQUE
  - Specifies that all values in the column must be unique.
- DEFAULT
  - Sets a default value for a column when no value is specified.
- PRIMARY KEY
  - Specifies that the column is a primary key. A primary key uniquely identifies each row in a table.
  - A primary key is by default NOT NULL and UNIQUE; there is no need to explicitly state these two constraints if the column is a primary key. In addition, each table can only have one primary key.
- AUTO_INCREMENT
  - Specifies that the values for this column should be automatically increased by 1 for each new record. This feature is often used to generate a primary key for the table. By default, the starting value for an auto increment column is 1. We’ll learn how to change this starting value in the next chapter.
  - Each table can only have one auto increment column and that column must be defined as a key (such as a primary key or a unique key).


                  CREATE TABLE co_employees (
                    id INT PRIMARY KEY AUTO_INCREMENT,
                    em_name VARCHAR(255) NOT NULL,
                    gender CHAR(1) NOT NULL,
                    contact_number VARCHAR(255),
                    age INT NOT NULL,
                    date_created TIMESTAMP NOT NULL DEFAULT NOW()
                    );
 - Foreign Key Constraint
   - A foreign key is a column (or a collection of columns) in one table that links to the primary key in another table

                FOREIGN KEY(mentor_id) REFERENCES co_employees(id) ON DELETE CASCADE ON UPDATE RESTRICT,
                 FOREIGN KEY(mentee_id) REFERENCES co_employees(id) ON DELETE CASCADE ON UPDATE RESTRICT

  - note that we also added the ON DELETE CASCADE and ON UPDATE RESTRICT clauses to our foreign keys.
  - The ON DELETE CASCADE clause means that if a certain employee is deleted from the co_employees table (the parent table), any record of that employee (child table) in the mentorships table will also be deleted.

#### ON DELETE Clauses
- ON DELETE RESTRICT
  - The row in the parent table cannot be deleted if a row in the child table references that parent row.
- ON DELETE SET NULL
  - The child row foreign key value will be set to NULL if the parent row is deleted. For this to work, the relevant column in the child row must allow for NULL values.
-ON DELETE SET DEFAULT
 - The child row foreign key value will be set to the default value if the parent row is deleted.
- These ON DELETE clauses can also be applied when updating the parent table. To do that, we use the ON UPDATE clause.


        Some readers may notice that a UNIQUE constraint is very similar to a PRIMARY KEY constraint. Indeed, a primary key is unique by definition.
          However, one of the main differences between a primary key and a unique key is that a table can only have one primary key but can have multiple unique keys.

 
### Named Constraints
- we added table constraints without naming them. If we want, we can name our constraints. To do that, we add the following syntax before stating the constraint:

          CONSTRAINT name_of_constraint

          for example : CONSTRAINT mm_constraint UNIQUE (mentor_id, mentee_id)


- The code to create the table is:

          CREATE TABLE mentorships (
          mentor_id INT NOT NULL,
          mentee_id INT NOT NULL,
          status VARCHAR(255) NOT NULL,
          project VARCHAR(255) NOT NULL,
  
          PRIMARY KEY (mentor_id, mentee_id, project),
          CONSTRAINT fk1 FOREIGN KEY(mentor_id) REFERENCES co_employees(id) ON DELETE CASCADE ON UPDATE RESTRICT,
          CONSTRAINT fk2 FOREIGN KEY(mentee_id) REFERENCES co_employees(id) ON DELETE CASCADE ON UPDATE RESTRICT,
          CONSTRAINT mm_constraint UNIQUE(mentor_id, mentee_id)
          );

# Altering Tables

- Table Names
  - The first thing we can modify is the table name. To do that, we use the syntax

      RENAME TABLE old_name TO new_name;

- Columns and Table Constraints

      ALTER TABLE table_name

- followed by
  - AUTO_INCREMENT = starting_value to change the starting value of the auto increment column,
  - ADD CONSTRAINT [name of constraint] details_of_constraint to add a table constraint (including foreign key constraints),
  - DROP INDEX name_of_constraint to drop a table constraint (excluding foreign key constraints),
  - DROP FOREIGN KEY name_of_foreign_key to drop a foreign key constraint,
  - MODIFY COLUMN column_name data_type [constraints] to modify a column,
  - DROP COLUMN column_name to drop a column, and
  - ADD COLUMN column_name data_type [constraints] to add a column.
 
        ALTER TABLE employees
        DROP COLUMN age,
        ADD COLUMN salary FLOAT NOT NULL AFTER contact_number,
        ADD COLUMN years_in_company INT NOT NULL AFTER salary;
  
- After modifying our table, we can check if our modifications are correct by asking MySQL to describe our table.The syntax is simply

      DESCRIBE table_name;

# Deleting Tables
- we use the syntax below:
 
       DROP TABLE [IF EXISTS] table_name;


















