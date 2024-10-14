# Creating the Database
- The first thing that we need to learn is to create a database
- The syntax to create a database is shown below:
  - CREATE DATABASE name_of_database;

# Using the Database
- After we create a database, we have to let the DBMS know that we want to use this database. This is because the DBMS may be managing more than one databases concurrently. We have to let it know that all subsequent code that we write applies to the stated database.
- To do that, we use the following syntax:
  - USE name_of_database;

# Deleting the Database
- Now, suppose after you create your database, you realise that you have typed the name wrongly. There is no easy way to rename a database in MySQL. What you can do is create a new database and delete the old database. To delete a database, we use the syntax
  - DROP DATABASE [IF EXISTS] name_of_database;
# Creating Tables
- First, let’s look at how we can create tables to add to our database. To create a table, we use the following syntax:
  - CREATE TABLE table_name (
    column_name1 datatype [column constraints],
    column_name2 datatype [column constraints],
    …
      [table constraints],
      [table constraints]
    );      


