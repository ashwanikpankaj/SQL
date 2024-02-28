# SQL

There are mainly 3 types of SQL commands

i) DDL => Data Definition Lannguage => to create ,alter and drop

ii) DML => Data Manipulation Language => Select , Update , Insert and Delete

iii) DCL => Data Control Language => Grant a permissions to users

## Database => a system => that helps to organise the data 


RDMS => a relational Data Base Management System

Sql is RDMS

## Data Types

Data type of columns defines what values the column will store in table

All the types are 

i) String :Char, Varchar, etc  => a) varchar : variable length string that contains numbers , letters, strings, special char b) char: fixed lenght string that contains numbers, letters, special char

ii) Numeric: int, float, bool, etc

iii) Date and Time : date, datetime etc,

   data => DD-MM-YYYY (only date combination)
   datetime => date and time combination


## Primary Keys and Foreign Keys

## Primary Key

Primary key is a unique column in table to easily identify and locate data in queries
A table can have only one primary key and that should not be null

## Foreign Key

FK is a column used to link two or more tables together

A table can have any number of foreign key and can be duplicate or null values

## Constraints

This are used to define the rules for data in the table => for accuracy and reliablility

### Syntax

CREATE_TABLE table_name (  
column1 datatype constraint,  
column2 datatype constraint,   
column3 datatype  
)

Commonly Used Constraints 

i) NOT NULL => this ensure that column can't have a null value

ii) UNIQUE: ensure all values in a column are different

iii) PRIMARY KEY : Combn of NOT NULL and UNIQUE

iv) FOREIGN KEY : Prevents actions that may destroy the links between the table

v) CHECK : Ensures that values in a column satisfy the certain conditions

vi) DEFAULT : defuault value for a column if no value comes

vii) CREATE INDEX: used to create and get that from the table quickly


# Create a table 
 ## Syntax
CREATE TABLE table_name (   
column_name1 datatype constraints
)

CREATE DATABASE database name => is used to create the database


This is for creating the table

Example

CREATE TABLE customer (  
"ID" int8 PRIMARY KEY,  
"NAME" varchar(50) NOT NULL,   
"AGE" int NOT NULL,  
"CITY" char(50),   
"Salary" numeric  
)

To get that table
 
SELECT * FROM customer (star is for all the value of the table)

## Insert data in the table

### syntax

INSERT INTO TABLE_NAME
(column1,column2...)   
VALUES   
(value1 , value2, ...)

Example

INSERT INTO customer  
(ID,NAME,AGE,CITY,Salary)   
VALUES   
(1,"Ashwani", 30,"Bihar",80000),   
(2,"Naveen", 30,"Bihar",1000000)  

## Update values => Update command is used to update the existing value in table
# Syntax   
UPDATE TABLE_NAME   
SET "Column_name1" = "value1" "Column_name2" ="value2"   
WHERE id="value"   

Example

UPDATE customer   
SET NAME ="Sunil" AGE =32  
WHER ID = 1;  

# Delete the values from Table

DELETE FROM customer   
WHERE id =1;   


# ALTER TABLE => used to add , delete , or modify the table

## Syntax

i) ALTER TABLE add column syntax

ALTER TABLE table_name  
ADD COLUMN table_name;

ii) Drop column syntax   

ALTER TABLE table_name    
DROP COLUMN column_name;  

iii) Modify column syntax  
ALTER TABLE table_name   
ALTER column column_name datatype;


## Drop Table => for deleting the table

DROP TABLE table_name   

## Truncate table => delete the data inside the table but not the table itselg

TRUNCATE TABLE table_name

## SELECT

This is used to select the data from the table

### Syntax

SELECT column_name1, column_name2 FROM table_name

To select all the fields from the table

SELECT * FROM table_name

To select unique and dinstinct fields present in the table

SELECT DISTINCT column_name FROM table_name

example for distinct will be like => if the grade column is present A,B,C,D,A,B then only cloumn of grade with A,B,C D will be visible => unique grades only

## WHERE

Used to filter the records

### Syntax

SELECT  column_name FROM table_name     
WHERE conditions

Example 

SELECT name FROM classroom   
WHERE grade = "A" (here grade is column name for now) only name column for that grade will be visible

## Operators in SQL
Used with the WHERE clause while doing any query

i) Arithmatic operators  => +,-,/,%

ii) Comparison operators  => =, !=, > , < , >=,<= etc

iii) Logical operators => perform boolean logic   
eg => ALL, BETWEEN, IN , LIKE, AND , OR, NOT , ANY

iii) Bitwise operator => &(AND) , | (OR)

Examples 

SELECT name FROM classroom  
WHERE grade ="A" AND rollno > 3

## LIMIT  CLAUSE 
This is used to set set an upper limit on number of tuples returned by the SQL

Example => Below code will return the 5 rows of data  
SELECT column_name FROM table_name  
LIMTI 5;  


## ORDER BY clause 
Set the data in ascending order or descending order  

Example   
SELECT column_name FROM table_name
ORDER BY column_name ASC; (for Descending oreder => DESC)




## Functions in SQL 

i) Built in functions =>  rand(),round(),uppper(),lower(),

ii) User defined functions => Custom functions

MOST used strings functions  => that is perform on the strings  

i) UPPER => converts the value of field to upper case  

ii ) LOWER => converts the value of field to lower case  

iii) LENGTH => return the length of the value in text field   

iv)  SUBSTRING => extract the subsring  from the string   

v) NOW () => returns the current system date and time.   

vi) FORMAT => used to set the format of the field   

vii) CONCAT => add two or more string together   

viii) REPLACE => replace all occurences of a substring in a string with the new substring   

ix) TRIM => removes the leading and trailing spaces  

Example

SELECT UPPER(column_name) FROM table_name => it will convert the text of the column in upper case

SELECT CONCAT(column_name1, column_name2) FROM table_name  => add the two string

SELECT REPLACE(column_name , textTobeReplaced , replacingText)   

### AGGREGATE FUNCTION => perform calucations on multiple values and returns a single value

Most used aggregate function

Aggregate funtion is most used by GROUP BY or SELECT statement

i) COUNT() => returns number of values => gives the total number of rows

ii) SUM() => returns sum of all values

iii) AVG() => returns avg value

iv) MAX() => returns the maximum value

v) MIN() =>  returns the min value

vi) ROUNDS() => rounds a number to a specified number of decimal places


Example

a) SELECT COUNT(*) FROM table_name

or  =>b) SELECT COUNT(column_name) FROM table_name => both a) and b) will give the same value no of rows

ii) SELECT SUM(column_name) FROM column_name

iii) SELECT ROUND(AVG(column_name),2) FROM table_name => here 2 is like after decimal 2 digits will be visible


## GROUP BY => group rows that have same values into summary rows

It is often used with Aggregate functions

## Syntax  
SELECT column_name(s) FROM table_name
GROUP BY column_name(s)

Example

SELECT mode,SUM(amount) AS total FROM payment   => AS will determine the column name
GROUP BY mode  (here select cloumn_name and group by column_name should be same)


mode | total 
--- | --- 
MobilePayment | 301 
Debit Card    | 201 




































Attempt | #1 | #2 | #3 | #4 | #5 | #6 | #7 | #8 | #9 | #10 | #11
--- | --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |---
Seconds | 301 | 283 | 290 | 286 | 289 | 285 | 287 | 287 | 272 | 276 | 269




