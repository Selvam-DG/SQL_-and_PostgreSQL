**source** - Udemy - SQL and PostgreSQL 
### Introduction:
- SQL is a communication language.
- It is how we interface or interact with our database.
- SQL is supported by many other databases as well, such as Oracle, Microsoft, SQL, MySQL, and so on.
- Four challenges in PostgreSQL:
  1. Writing efficient queries to retrieve information
  2. Designing the schema or structure of the database
  3. Understanding when to use advanced features
  4. Managing the database in a production environment
- Database Design Process
  - What kind of thing are we storing? - For this, we should create a Table for the collection of records
  - What properties does this thing have? The table contains columns
  - What type of data does each of those properties contain? each column that records one for each of those properties
- **Client**: https://pg-sql.com/
- **Database**: PostgreSQL
- SQL statement consists of different words:
  - keywords: are very special words inside of SQL that tell the database that we want to do a very specific thing. Always written out in Capital letters
  - Identifiers: Tell the database what things we want to act on. Always written in lower character
- Column Data Types:
  - VARCHAR: Variable length character
  - INTEGER: Numbers without a decimal
- SQL is not just about pulling raw data out of a table. We can write SQL to transform or process data before we receive it.
- String operators and Functions:
  - || - Join two strings
  - CONCAT()- concatenate two string
  - LENGTH() - returns the length of the string
  - UPPER()- Returns a Uppercase string
  - LOWER()- Gives a lowercase string
### Filtering Records:
- Filtering Rows with "WHERE"
- Updating Rows using"UPDATE"
- Deleting Record with "DELETE"
### Working with Tables:
- Database design with
  - One-to-many relationships or  many-to-one relationship
    - one boat with many crew members
  - one-to-one relationship
    - one company one CEO, one boat one captain
  - many-to-many relationship
    - players play many matches



