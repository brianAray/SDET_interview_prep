# SQL Review

## Relational Database
- a db where we store data as it relates to other data, or as connections to other data

- **SQL** is a language used to query, modify, and define relational DB. 
- table: entity comprised of columns and rows
- columns are named 
    - these columns correspond to fields in a Java Class
- rows are data entries - complete sets of information - sometimes called 'records'
    - these correspond to an instantiated object in Java

## SQL Sublanguages
- sometimes debated numbers vary from 3-5
- if three: DDL, DML, DCL
- if five: DDL, DML, DQL, DCL, TCL
- DDL: Data Definition Language
    - this is used to define tables, schemas, views, contraints, etc (objects in our db)
    - CREATE, ALTER, DROP, TRUNCATE
- DML: Data Manipulation Language
    - this is used to manipulate rows in tables (this is the data in our DB)
    - (in the "three sublanguages" view, DQL is included here in DML)
    - INSERT, UPDATE, DELETE
- DQL: Data Query Lanaguage
    - this is used to query the data (retrieving or reading information from the DB)
    - (in the "five sublanguages" view, this is a separate language because the queries can get very complex)
    - SELECT
- DCL: Data Control Language
    - this is used to manage permissions of database users
    - GRANT, REVOKE
- TCL: Transaction Control Language
    - this is used to manage transactions (a.k.a. groups of DML statements) that are related to each other
    - (in the "three languages" view, this is included in the DML)
    - ROLLBACK, COMMIT, SAVEPOINT, BEGIN
    - (ACID Properties: Atomic, Consistent, Isolated, Durable)

## Primary Key: the unique identifer of a row 
- primary key constraint is a combo of both UNIQUE and NOT NULL

## Foreign Key: a column that references the primary key of another table
- this is how we build our relationships between tables
- Customer Table (ID, NAME) and an Accounts Table (ID, BALANCE, CUSTOMER_ID)
    - CUSTOMER_ID is a foreign key to the CUSTOMER table

- Multiplicity
    - 1 to 1
    - 1 to Many
    - Many to Many

## Referential Integrity: 
- the concept that a foreign key must always reference (refer to/relate to) a valid key in the other table
    - ON DELETE ....
        - CASCADE
        - SET NULL
        - NO ACTION / RESTRICT
## Basic Statements
- SELECT (columns) FROM (table)
- WHERE: sets a condition -> WHERE id = 2;
- ORDER BY: allows us to sort by a specified column -> order by age | order by name
    - asc -> ascending is default (A->Z) | desc -> descending goes from highest to lowest (Z->A)

## Scalar and Aggregate functions
- scalar: single input, single output
    - substr, round, upper, lower, trim, left, concat
- aggregate: groups of input, single output
    - count, avg, sum, min, max
    - GROUP BY: used with aggregate functions for data analysis
        - eg. SELECT COUNT(col1) FROM table GROUP BY col1;
    - HAVING
        - eg. SELECT COUNT(col1) FROM table GROUP BY col1
                HAVING col2 = value;

## Joins
- joins are used to query data from multiple tables at the same time
- types of joins: 
    - inner join: only returns rows that have a match
    - left outer join: returns all rows from the left table and matching rows from the right table with null values in the right-side rows that don't have matches
    - right outer join: returns all rows from the right table and matching rows from the left table with null values in the left-side rows that don't have matches
    - full outer join: returns all rows from both tables with null values in rows on either side where matches do not exist
    - cross join: the Cartesian product of all rows from both tables
        - a.k.a. al possible combinations of rows from both tables
    - self join: joining a table with it itself in order to combine related data from the same table
        - e.g. when an EMPLYOEE table has a foreign key that references that employee's manager, who is also a employee and therefore in the EMPLOYEES table
- the JOIN keyword on its own is an inner join