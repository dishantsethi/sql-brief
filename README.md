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

- `Select distinct Country, PinCode from Table` *Combication of unique country and pincode will be displayed


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

## 10. Order By clause

## 11. Between operator with Text

## 12. In Operator

## 13. Like Operator and wildcard characters

## 14.Aliases

## 15. Limit Keyword

## 16. Breaking lengthy sql statements

## 17. MySQL builtin functions

## 18. upper() function

## 19. lower() function

## 20. length() function

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

Truncate Statement

Single and Multi Line Comments

Group By Clause

Having Clause

Sequence of using Where, Group By, Having and Order By

Set Operator

Union Operator

Union All Operator

Intersect Operator

Minus Operator

Tables and Aliases

Joins

Subquery


