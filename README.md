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

## 22. substr() function

## 23. concat() function

## 23. trim() function

## 24. abs() function

## 25. mod() function

## 26. greatest() and least() function

## 27. truncate() function

## 28. power() and sqrt() function

## 29. current_date(), curdate(), current_time(), curtime(), now(), sysdata() function

## 30. year(), month(), day(), monthname(), dayname() function

## 31. avg(), max(), min(), count(), sum() function

## 32. Arithmetic Operators

## 33. Install Mysql server and Mysql workbench

## 34. Create, Delete, Viewing and Using Database in Workbench

## 35. Create, Viewing, Describing and Deleting Tables in Workbench

## 36. Insert Statement

## 37. Data Types

## 38. Null Value, IsNull and IsNotNull

## 39. Delete Statement

## 40. Update Statement

## 41. Rename Statement and To Keyword

## 42. Alter Statement, Add Modify Rename and Drop Column

## 43. Set Autocommit

## 44. Commit Statement

## 45. Rollback Statement

## 46. Truncate Statement

## 47. Single and Multi Line Comments

## 48. Group By Clause

## 49. Having Clause

## 50. Sequence of using Where, Group By, Having and Order By

## 51. Set Operator

## 52. Union Operator

## 53. Union All Operator

## 54. Intersect Operator

## 55. Minus Operator

## 56. Tables and Aliases

## 57. Joins

## 58. Subquery


