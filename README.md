# SQL Notes

## 1. Database concepts
> Database: A place to store and retrieve the data.

> DBMS: Softwares that are used to store data in databases in an organised way to make it easier for us to create, update, modify data records.

> Data Models: Defines how related data is connected to each other.
>
> - Hierarchial Model
> - Network Model
> - ER Model
> - Relational Model (commonly used)

> RDBMS: DBMS using relational data models. Eg: Oracle, MySql, PostgreSql

> SQL: Query Language for relational databases.

## 2. Select Command
> Purpose: retrieve data from tables

- `Select * from TableName;`
- `Select Column1, Column2 from TableName`

## 3. Distinct Keyword
> For Unique values to be retrieved

| Country | City  | CustomerName | CustomerID | PinCode |
|---------|-------|--------------|------------|---------|
| India   | Delhi | A            | 1          | 111     |
| India   | Pune  | B            | 2          | 112     |
| USA     | SF    | C            | 3          | 113     |
| USA     | CA    | D            | 4          | 114     |

- `Select distinct Country from Table`

- `Select distinct Country, PinCode from Table` *Combination of unique country and pincode will be displayed


## 4. SQL is not case sensitive

All of these all retrieve same data
- `SELECT * FROM TABLE`
- `select * from table`
- `Select * From Table`

## 5. Semicolon

> Mandatory in some RDBMS Software

> Not Mandatory in some online sql softwares where we cannot sun multiple sql queries

## 6. Where clause

> Purpose is to filter records based on some condition

> Practice:
- `Select * from Table where Country='India'`
- `Select * from Table where CusotmerID=1`
- `Select CustomerID, CustomerName from Table where City='Delhi'`

## 7. Relational operations with where clause
> Different Relational operator we can use with Where clause.

> ( = )
>
> `Select * from Product where price=10`

> ( > )
>
> `Select * from Product where price>10`

> ( < )
>
> `Select * from Product where price<10`

> ( <= )
>
> `Select * from Product where price<=10`

> ( >= )
>
> `Select * from Product where price>=10`

> ( <> )
>
> `Select * from Product where price<>10`

## 8. Logical operators with where clause

> To filter records based on multiple conditions

> AND 
> - `Select * from Table where Country='India' AND City='Delhi'`
> - `Select * from Table where City='Delhi' AND CustomerID<4`

> OR 
> - `Select * from Table where Country='India' OR City='Delhi'`
> - `Select * from Table where City='Delhi' OR CustomerID<4`

> NOT 
> - `Select * from Table where NOT Country='India'`


## 9. Between operator

> To filter records based on some range

> Practice:
- `Select * from Products where Price Between 10 and 20`
- `Select * from Products where Price NOT Between 10 and 20`

## 10. Order By clause

> Purpose is to retrieve records in ascending or descending order.
> Practice:
- `Select * from Products order by price ASC, discount ASC `
- `Select * from Products order by price DESC, discount DESC`

## 11. Between operator with Text

> To filter based on some range (the data is ordered in ascending order of alphabets automatically)

> Practice:
- `Select * from Products where Name Between 'Box' and 'Pen'`

## 12. In Operator

> Simplifies providing multiple values in where clause. (Works with OR)

> Practice:
- `Select * from Products where price=10 or price=20 or price=30`
- `Select * from Products where prine in(10, 20, 30)`
- `Select * from Customers where Country='India' or Country='USA'`
- `Select * from Customers where Country in('India', 'USA')`

## 13. Like Operator and wildcard characters

> We can use Like operator and wildcard characters for pettern matching needs.
>
> We can use them in Where clause condition.

> Practice:
- %: Multi Chars
- _: Single Char
- `Select * from Customers where CustomerName like 'A%'`
- `Select * from Customers where CustomerName like '%A'`
- `Select * from Customers where CustomerName like 'A_'`
- `Select * from Customers where CustomerName like '_A'`
- `Select * from Customers where CustomerName like '%A%'`
- `Select * from Customers where CustomerName like '_A_'`

## 14.Aliases

> While the records are retrieved, there alias provided for the column names will be displayed in place of original column name

> Practice:
- `Select ProductID as ID, ProductName as Name from Products`

## 15. Limit Keyword
> Using limit keyword we can decide how many records are to be displayed on the page irrespective of number of records present in the table.

> Practice:
- `Select * from Products LIMIT 3`
- `Select * from Products LIMIT 2,8` * Start with index 2 and print first 8 records


## 16. Breaking lengthy sql statements
> Break SQL statements by clause for better understanding

- `Select CustomerID, CustomerName, City, Country, Pin from Customer where City='Delhi' Limit 5 Order By Pin DESC`
- `Select CustomerID, CustomerName, City, Country, Pin`

    `from Customer`

    `where City='Delhi'`
    
    `Limit 5`
    
    `Order By Pin DESC`

## 17. MySQL builtin functions
> There are several built-in functions, using which we can perform different operations on different table data.

> Types of built-in functions
> - String Functions
> - Numeric Functions
> - Date Time Functions
> - Aggregate Functions

## 18. upper() function
> Convert text under the specified column data into upper case

> Practice:

- `Select upper('Dishant')`
- `Select upper(Country) as Country from Customer`
- `Select upper(Country) as Country, upper(City) as City from Customer`

## 19. lower() function
> Convert text under the specified column data into lower case

> Practice:

- `Select lower('Dishant')`
- `Select lower(Country) as Country from Customer`
- `Select lower(Country) as Country, upper(City) as City from Customer`

## 20. length() function
> Find size of data under specified column

> Practice:

- `Select length('Dishant')`
- `Select Country, length(Country) as CountrySize from Customer`
- `Select * from Customer where length(Country) = 6`

## 21. instr() function
> Find the position of given text in the specified column

- `select instr('Dishant', 'i')`
- `select instr(Country, 'e') as Position from Customer`

## 22. substr() function
> Retrieves a portion of text from the specified column

- `select substr('Dishant', 2,5)`
- `select substr(ColumnName, StartIndex, Size)`

## 23. concat() function
> Adds two or more table column together.

- `select concat(Firstname, ' ', LastName) from Table`
- `select concat('Dishant', ' ', 'Sethi')`

## 23. trim() function
> To remove leading and trailing spaces in column data.

- `select trim('   Dishant   ')`
- `select trim(concat(FirstName, LastName)) from Table`

## 24. abs() function
> The function will retrieve positive value irrespective of whether the given number is positive or negative.

- `select abs(-9)`
- `select abs(9)`
- `select abs(price) from table`

## 25. mod() function
> mod function will return remainder value of the given data of specified column.

- `select mod(12,3)` 0
- `select mod(10,3)` 1
- `select mod(14,5)` 4

## 26. greatest() and least() function
> return the greatest and least value from the given numeric values

- `select greatest(1,2,3,4,5,6,7,8,9,19)`
- `select least(1,2,3,4,5,6,7,8,9,19)`
- ``

## 27. truncate() function
> returns the numerical value with the specified number of digits after the decimal points.

- `select truncate(123.456, 1)` 123.4
- `select truncate(price, 2) from Products`

## 28. power() and sqrt() function
> Power and square root of given numeric value

- `select power(2,5)` 2*2*2*2*2
- `select sqrt(2)` 1.414

## 29. current_date(), curdate(), current_time(), curtime(), now(), sysdata() function
> current_date(): Return the current date in string format
>
> curdate():  Return current date in string format
>
> current_time(): Return current time HH:MM:SS
>
> curtime(): Return current time HH:MM:SS
>
> now(): Return both current date and time
>
> sysdate(): Return both current date and time

## 30. year(), month(), day(), monthname(), dayname() function

- `select year('2020-04-01')`
- `select month('2020-04-01')`
- `select day('2020-04-01')`
- `select monthname('2020-04-01')`
- `select dayname('2020-04-01')`
- `select * from Orders where month(OrderDate)=4`
- `select * from Orders where monthname(OrderDate)='May'`

## 31. avg(), max(), min(), count(), sum() function

- `select avg(price) from Products`
- `select max(price) from Products`
- `select min(price) from Products`
- `select sum(price) from Products`
- `select count(*) from Products`

## 32. Arithmetic Operators
> Below are Arithmetic operators which can be used in sql
- Addition (+)
- Subtraction (-)
- Multiplication (*)
- Division (/)
- Modulus (%)

> Demonsteration
- `select 5+4`
- `select 5-4`
- `select 5*4`
- `select 5/4`
- `select 5%4`
- `select price, price+10 from products`
- `select price, price-10 from products`
- `select price, price*10 from products`
- `select price, price/10 from products`
- `select price, price%10 from products`

## 33. Install Mysql server and Mysql workbench
> Mysql server: store the data in database
>
> Mysql workbench client: GUI application to connect to the database server and perform operations on the database

> How to install mysql server and mysql workbench client?
>
> GOOGLE IT.

## 34. Create, Delete, Viewing and Using Database in Workbench
> Creating a database:
- `show databases;`
- `create database DBName;`
- Refresh to see the newly created database
- Observe that the db will be created without any table, views, stored procedure and functions

> Deleting a database:
- `show databases;`
- `drop database DBName;`

> Use a database:
- `use DBName; select * from Table;`
OR
- `select * from DBName.Table;`

## 35. Create, Describing and Deleting Tables in Workbench
> create table
- `use DBName;`
- `show tables;`
- `create table TableName(id int, name varchar(50), gender varchar(1), country varchar(50), experience int)`
- `create table NewTable as Select * from OldTable` //data from oldtable will also be copied

> describe table
- `use DBName;`
- `describe TableName;`

> delete table
- `use DBName;`
- `drop table TableName;`

## 36. Insert Statement
> Insert data into table

- `use DBName;`
- `Insert into TableName values(value1, value2, ..., valueN)`
- `Insert into TableName(col1, col2) values(value1, value2)`

## 37. Data Types
> Commonly used data types
- varchar(size)
- int
- double
- boolean
- date
- time
- datetime
- year

## 38. Null Value, IsNull and IsNotNull
> Suppose a table Employee with three columns id, name, experience

- `insert into employee values(1, 'dishant')` // error
- `insert into employee(id, name) values(1, 'dishant')` // experience will be NULL
- `select * from employee where experience IS NULL`
- `select * from employee where experience IS NOT NULL`

## 39. Delete Statement
> Use delete statement to delete table records.

- `delete from TableName where id=1`
- `delete from TableName where id=2`

## 40. Update Statement
> Update records of a table using SET keyword

- `update TableName set name='Dishant' where id=1`
- `update Employee set name='Dishant Sethi' where id=2`

## 41. Rename Statement and To Keyword
> Rename Table name using To Keyword

- `rename table Employee to NewTableName`
- `rename table Product to NewProducts`

## 42. Alter Statement, Add Modify Rename and Drop Column
> Use ALTER keyword to add, modify, rename and drop column

- `Alter table Employee add location varchar(25)`
- `Alter table Employee modify location int`
- `Alter table Employee rename column location to loc`
- `Alter table Employee drop column loc`

## 43. Set Autocommit
> In mysql workbench client, autocommit is set to 1(True), We can turn it off using

- `set autocommit = 0` 

> The changes you make to the tables will be temporary changes if autocommit is off.

## 44. Commit Statement
> If autocommit is turned off, using commit keyword to save the changes manually.

- `commit;`

## 45. Rollback Statement
> Revert temporary changes done on a particular table

- `set autocommit = 0`
- `insert into TableName values(value1, value2)`
- `rollback;`

## 46. Truncate Statement
> No matter if autocommit is set to 0 or 1, truncate will permanently delete all the records of a particular table.

- `truncate table tablename`

## 47. Single and Multi Line Comments

> -- single line comment

> /* This is a multi
>
> line comment */

## 48. Group By Clause
> To group the retrieved records according to the specified column. 

- `select id from Country`
- `select count(id) from Country`
- `select count(id), continent from Country group by continent`
- `select sum(amount) from payment group by customerid`

## 49. Having Clause
> Having clause is like where clause for group by clause

- `select count(id), continent from Country group by continent having count(id)<10`
- `select sum(amount) from payment group by customerid having sum(amount)>1000`

## 50. Sequence of using Where, Group By, Having and Order By
> where > group by > having > order by

- `select count(*), country from Customers where city is not 'Berlin' group by country having length(customerName)>1 order by PostalCode`

## 51. Union Operator

## 52. Union All Operator

## 53. Intersect Operator

## 54. Minus Operator

## 55. Tables and Aliases
> Alias names for tables

- `select o.id, o.name, o.quantity, p.id, p.price, p.discount from Order o, Product p where o.id = p.id `

## 56. Joins
> The purpose of joins is to join two tables while retrieving data from tables using the common column.
>
> Types of joins
>
> - Inner Join
> - Left Join
> - Right Join
> - Full Join
> - Self Join

Emp1
| id | firstname |
|----|-----------|
| 1  | A         |
| 2  | B         |
| 3  | C         |
| 4  | D         |

Emp2
| id | lastname |
|----|-----------|
| 3  | E         |
| 4  | F         |
| 5  | G         |
| 6  | H         |

### Inner Join
`select * from Emp1 inner join Emp2 on Emp1.id=Emp2.id`

Result
| id | fristname | lastname |
|----|-----------|----------|
| 3  | C         | E        |
| 4  | D         | F        |

### Left Join
`select * from Emp1 left join Emp2 on Emp1.id=Emp2.id`

Result
| id | fristname | lastname |
|----|-----------|----------|
| 1  | A         | NULL     |
| 2  | B         | NULL     |
| 3  | C         | E        |
| 4  | D         | F        |

### Right Join
`select * from Emp1 right join Emp2 on Emp1.id=Emp2.id`

Result
| id | fristname | lastname |
|----|-----------|----------|
| 3  | C         | E        |
| 4  | D         | F        |
| 5  | NULL      | G        |
| 6  | NULL      | H        |

### Full Join
> Full join is not supported in Mysql RDBMS. 

### Self Join
> Same table will be used two times
>
> There is no keyword for self join

## 57. Subquery
> Running query inside a query (Nested query)
>
> - Single row sub query
> - multi row sub query

### Single row subquery
> Question: Select all customers in Customers table who are from the same city of "Hari Kumar"

- `select * form Customers where city=(select city from Customers where name='Hari Kumar')`

> Question: Find second max price of Products

- `select max(price) from Products where price<(select max(price) from Products)`

> Question: Display products sold at least price

- `select * from products where price=(select min(price) from products)`

## 58. In Operator
> Without IN operator we can only give one value in WHERE clause.

- `select * from Customers where city = 'Delhi'`
- `select * from Customers where city IN ('Delhi', 'Bombay', 'Pune')`

## 59. In Operator with mulit row subquery
> Question: Find different products which fall into specified name category.

- `select * from product where categoryid IN (select categoryid from category where categoryname like 'C%')`

## 60. Any operator with multi row subquery
> ANY means that the condition will be true if the operation is true for any of the values in the range.

- `SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition);`

Note: The operator must be a standard comparison operator (=, <>, !=, >, >=, <, or <=).

> Example:
- `SELECT ProductName FROM Products WHERE ProductID = ANY (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);`

> `productid=10 or productid=20 or productid=30 `

## 61. All operator with multi row subquery
> Example:
- `SELECT ProductName FROM Products WHERE ProductID = ALL (SELECT ProductID FROM OrderDetails WHERE Quantity = 10);`

> `productid=10 and productid=20 and productid=30`

## 62. Exists Operator
> The EXISTS operator is used to test for the existence of any record in a subquery.

- `select * from orders where exists (select * from customers where customerid=10)`

## 63. Using subquery to retrieve records from multiple tables
> Example

- `select city, (select country from Country where City.country_id = Coutnry.country_id) as country from City`

## 64. Multiple subquery in single sql statement
> Question: List out films having length less than meximum length and having rental duration equal to minimum rental duration

- `select * from film where length < (select max(length) from film) and rental_duration = (select min(rental_duration) from film)`

## 65. Integrity constraint
> We can apply these integrity constraints to the table column while using create and alter sql statements

> The following constraints are commonly used in SQL:

- NOT NULL - Ensures that a column cannot have a NULL value
- UNIQUE - Ensures that all values in a column are different
- PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
- FOREIGN KEY - Prevents actions that would destroy links between tables
- CHECK - Ensures that the values in a column satisfies a specific condition
- DEFAULT - Sets a default value for a column if no value is specified
- CREATE INDEX - Used to create and retrieve data from the database very quickly

Note: Syntax to add, alter, create a column with integrity constraints might vary from Mysql, Sql server, oracle etc etc

## 66. Not Null Integrity constraint
- `CREATE TABLE Persons (ID int NOT NULL, LastName varchar(255) NOT NULL, FirstName varchar(255) NOT NULL, Age int);`

- `ALTER TABLE Persons MODIFY COLUMN Age int NOT NULL;`

## 67. Unique Integrity constraint
- `CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    FirstName varchar(255)
);`

- `ALTER TABLE Persons ADD UNIQUE (ID);`

## 68. Primary Key Integrity constraint
- `CREATE TABLE Persons (ID int NOT NULL, LastName varchar(255) NOT NULL, FirstName varchar(255), Age int, PRIMARY KEY (ID));`

## 69. Foreign Key Integrity constraint
- `CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);`

## 70. Check Integrity constraint
- `CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);`

## 71. Default Integrity constraint
- `CREATE TABLE Persons (
    ID int NOT NULL,
    FirstName varchar(255),
    City varchar(255) DEFAULT 'Delhi'
);`

## 72. auto_increment Integrity constraint
> Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

- `CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);`

Note: By default, the starting value for AUTO_INCREMENT is 1

## 73. Insert itno Integrity constraint

## 74. IfNull() function
> Return the specified value IF the expression is NULL, otherwise return the expression:

- `SELECT IFNULL(expression, alt_value);`

expression: Required. The expression to test whether is NULL
alt_value:	Required. The value to return if expression is NULL

## 75. Case, When, Then and End Keywords
> The CASE statement goes through conditions and return a value when the first condition is met (like an IF-THEN-ELSE statement). So, once a condition is true, it will stop reading and return the result.
>
> If no conditions are true, it will return the value in the ELSE clause. 
>
> If there is no ELSE part and no conditions are true, it returns NULL.

- 
    `select product, price,`

    `case`
    
    `when price=10 then 'price is equal to 10'`
    
    `when price>10 then 'price is greater than 10'`
    
    `else 'price is smaller than 10'`
    
    `as pricedetails`
    
    `from Products`

## 76. Advance SQL Functions
- select BIN(15) // binary repr of a number
- select BINARY "a sentence" // convert value to binary string
- select COALESCE(null, null, 'W3Schools.com', null, 'Example.com'); // returns first non null value
- select CONNECTION_ID(); // Return the unique connection ID for the current connection:
- select CONV(15, 10, 2); // Convert a number from numeric base system 10 to numeric base system 2
- select CURRENT_USER(); //Return the user name and host name for the MySQL account
- select DATABASE(); //Return the name of the current (default) database
- select SYSTEM_USER(); //Return the current user name and host name for the MySQL connection
- select USER(); //Return the current user name and host name for the MySQL connection

## 77. Delimeter
 
## 78. Views

## 79. Indexes

## 80. Mysql shell CLI Tool

## 81. Mysql command line client

## 82. Types of SQL statement
- DQL: Select statements
- DML: Insert, Update, Delete
- DDl: Create, Drop, Alter, Truncate
- TCL: commit, rollback
- DCL: grant, revoke

## 83. Grants and Revoke
> Create User in mySql server.
>
> Grant and revoke permissions
> - use db;
> - grant select, insert on table to 'new_non_root_user';
> - revoke select, insert on table to 'new_non_root_user';

> - use db;
> - grant select, insert, drop, delete, alter on table to 'new_non_root_user';
> - revoke select, insert on table to 'new_non_root_user';

## 84. Temporary Tables

## 85. Show Columns, Indexes, Privileges, grants statement
- `show columns from tablename`
- `show indexes from tablename`
- `show previliges`
- `show grant for 'userone'`
- `show grant for 'usertwo'`

