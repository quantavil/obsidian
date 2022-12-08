
# [Data Manipulation Statements](https://dev.mysql.com/doc/refman/5.7/en/sql-data-manipulation-statements.html)

- [[#DELETE Statement|DELETE Statement]]
- [[#INSERT INTO|INSERT INTO]]
	- [[#INSERT INTO#Multiple INSERT INTO|Multiple INSERT INTO]]
- [[#UPDATE Statement|UPDATE Statement]]
- [[#DELETE Statement|DELETE Statement]]
- [[#Constraint|Constraint]]
	- [[#Constraint#NOT NULL Constraint|NOT NULL Constraint]]
	- [[#Constraint#UNIQUE Constraint|UNIQUE Constraint]]
	- [[#Constraint#PRIMARY KEY Constraint|PRIMARY KEY Constraint]]
	- [[#Constraint#[FOREIGN KEY Constraint](https://dev.mysql.com/doc/refman/5.6/en/create-table-foreign-keys.html)|FOREIGN KEY Constraint]]
		- [[#[FOREIGN KEY Constraint](https://dev.mysql.com/doc/refman/5.6/en/create-table-foreign-keys.html)#Adding Foreign Key Constraints|Adding Foreign Key Constraints]]
		- [[#[FOREIGN KEY Constraint](https://dev.mysql.com/doc/refman/5.6/en/create-table-foreign-keys.html)#Dropping Foreign Key Constraints|Dropping Foreign Key Constraints]]
	- [[#Constraint#SQL PRIMARY KEY Constraint|SQL PRIMARY KEY Constraint]]
	- [[#Constraint#CHECK Constraint|CHECK Constraint]]
	- [[#Constraint#DEFAULT Constraint|DEFAULT Constraint]]
- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)|SELECT ]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#ORDER BY  Clause|ORDER BY  Clause]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#Where Clause|Where Clause]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#HAVING Clause|HAVING Clause]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#LIMIT Clause|LIMIT Clause]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#DISTINCT modifier|DISTINCT modifier]]
	- [[#[SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)#[Join Clause](https://dev.mysql.com/doc/refman/8.0/en/join.html)|Join Clause]]



## DELETE Statement

[`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "13.2.2 DELETE Statement") is a DML statement that removes rows from a table.
A [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "13.2.2 DELETE Statement") statement can start with a [`WITH`](https://dev.mysql.com/doc/refman/8.0/en/with.html "13.2.15 WITH (Common Table Expressions)") clause to define common table expressions accessible within the [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "13.2.2 DELETE Statement"). 

**SYNTAX**
```sql
DELETE FROM _table_name_ WHERE _condition_;
```


## INSERT INTO
The `INSERT INTO` statement is used to insert new records in a table.
 **SYNTAX**

It is possible to write the `INSERT INTO` statement in two ways:
1. Specify both the column names and the values to be inserted:

```SQL
INSERT INTO _table_name_ (_column1_, _column2_, _column3_, ...)  
VALUES (_value1_, _value2_, _value3_, ...);
```

2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the `INSERT INTO` syntax would be as follows:

```SQL
INSERT INTO _table_name_  
VALUES (_value1_, _value2_, _value3_, ...);
```

### Multiple INSERT INTO

```SQL
INSERT INTO _table_name_ (_column1_, _column2_, _column3_, ...)  
VALUES (_valueA1_, _valueA2_, _valueA3_, ...),
       (_valueB1_, _valueB2_, _valueB3_, ...),
       (_valueC1_, _valueC2_, _valueC3_, ...);
```

## UPDATE Statement
The SQL **UPDATE** Query is used to modify the existing records in a table. You can use the WHERE clause with the UPDATE query to update the selected rows, otherwise all the rows would be affected.
```mysql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```


## DELETE Statement

The `DELETE` statement is used to delete existing records in a table.

```mysql
DELETE FROM table_name WHERE condition;
```

**Delete All Records**
```mysql
DELETE FROM _table_name_;
```


## Constraint
SQL constraints are used to specify rules for the data in a table.
Constraints are used to limit the type of data that can go into a table. 
Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table. By default, a column can hold NULL values. 
The following constraints are commonly used in SQL:
- *NOT NULL* - Ensures that a column cannot have a NULL value
- *UNIQUE* - Ensures that all values in a column are different
- *PRIMARY KEY* - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
- *FOREIGN KEY* - Prevents actions that would destroy links between tables
- *CHECK* - Ensures that the values in a column satisfies a specific condition
- *DEFAULT* - Sets a default value for a column if no value is specified
- *CREATE INDEX* - Used to create and retrieve data from the database very quickly

### NOT NULL Constraint

**NOT NULL on CREATE TABLE**

```mysql
CREATE TABLE Persons (  
    ID int NOT NULL,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255) NOT NULL,  
    Age int  
);
```

**SQL NOT NULL on ALTER TABLE**

```mysql
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

### UNIQUE Constraint

The `UNIQUE` constraint ensures that all values in a column are different.
Both the `UNIQUE` and `PRIMARY KEY` constraints provide a guarantee for uniqueness for a column or set of columns.

A `PRIMARY KEY` constraint automatically has a `UNIQUE` constraint.
However, you can have many `UNIQUE` constraints per table, but only one `PRIMARY KEY` constraint per table.

**UNIQUE Constraint on CREATE TABLE**

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

**UNIQUE Constraint on ALTER TABLE**

```mysql
ALTER TABLE Persons
ADD UNIQUE (ID);
```

**DROP a UNIQUE Constraint**

```mysql
ALTER TABLE Persons  
DROP INDEX UC_Person;
```

### PRIMARY KEY Constraint
The `PRIMARY KEY` constraint uniquely identifies each record in a table.
Primary keys must contain UNIQUE values, and cannot contain NULL values. A table can have only ONE primary key

**PRIMARY KEY on CREATE TABLE**

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

**PRIMARY KEY on ALTER TABLE**

```mysql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

```sql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

**DROP a PRIMARY KEY Constraint**

```mysql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

### [FOREIGN KEY Constraint](https://dev.mysql.com/doc/refman/5.6/en/create-table-foreign-keys.html)

The `FOREIGN KEY` constraint permit cross-referencing is used to prevent actions that would destroy links between tables.
A `FOREIGN KEY` is a field (or collection of fields) in one table, that refers to the `PRIMARY KEY` in another table.

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```

```sql
[CONSTRAINT [symbol]] FOREIGN KEY
    [index_name] (col_name, ...)
    REFERENCES tbl_name (col_name,...)
    [ON DELETE reference_option]
    [ON UPDATE reference_option]

reference_option:
    RESTRICT | CASCADE | SET NULL | NO ACTION | SET DEFAULT
```

-  CASCADE : **ON DELETE CASCADE** constraint is used in MySQL to delete the rows from the child table automatically, when the rows from the parent table are deleted.
	```sql
	CREATE TABLE child (
    id INT,
    parent_id INT,
    INDEX par_ind (parent_id),
    FOREIGN KEY (parent_id)
        REFERENCES parent(id)
        ON DELETE CASCADE
	) 
	```


#### Adding Foreign Key Constraints

You can add a foreign key constraint to an existing table using the following [`ALTER TABLE`](https://dev.mysql.com/doc/refman/5.6/en/alter-table.html "13.1.7 ALTER TABLE Statement") syntax:

```sql
ALTER TABLE tbl_name
    ADD [CONSTRAINT [symbol]] FOREIGN KEY
    [index_name] (col_name, ...)
    REFERENCES tbl_name (col_name,...)
    [ON DELETE reference_option]
    [ON UPDATE reference_option]
```

#### Dropping Foreign Key Constraints

You can drop a foreign key constraint using the following [`ALTER TABLE`](https://dev.mysql.com/doc/refman/5.6/en/alter-table.html "13.1.7 ALTER TABLE Statement") syntax:
use  `SHOW CREATE TABLE \G`  to see foreign  key symbol 

- `\G` : The ubiquitous semicolon command terminator `;` is actually shorthand for the `\g` command 

```sql
ALTER TABLE tbl_name DROP FOREIGN KEY fk_symbol;
```

```sql
mysql> SHOW CREATE TABLE child\G
*************************** 1. row ***************************
       Table: child
Create Table: CREATE TABLE `child` (
  `id` int(11) DEFAULT NULL,
  `parent_id` int(11) DEFAULT NULL,
  KEY `par_ind` (`parent_id`),
  CONSTRAINT `child_ibfk_1` FOREIGN KEY (`parent_id`)
  REFERENCES `parent` (`id`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1

mysql> ALTER TABLE child DROP FOREIGN KEY `child_ibfk_1`;
```

### SQL PRIMARY KEY Constraint

The `PRIMARY KEY` constraint uniquely identifies each record in a table.
Primary keys must contain UNIQUE values, and cannot contain NULL values.

A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

**PRIMARY KEY on ALTER TABLE**
```mysql
ALTER TABLE Persons  
ADD PRIMARY KEY (ID);
```

```mysql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

**DROP a PRIMARY KEY Constraint**
```mysql
ALTER TABLE Persons  
DROP PRIMARY KEY;
```
### CHECK Constraint

The `CHECK` constraint is used to limit the value range that can be placed in a column.
If you define a `CHECK` constraint on a column it will allow only certain values for this column.
If you define a `CHECK` constraint on a table it can limit the values in certain columns based on values in other columns in the row.

**CHECK on CREATE TABLE**

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```

**CHECK on ALTER TABLE**

```mysql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

```mysql
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

**DROP a CHECK Constraint**

```mysql
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```

### DEFAULT Constraint

The `DEFAULT` constraint is used to set a default value for a column.
The default value will be added to all new records, if no other value is specified.

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

The DEFAULT constraint can also be used to insert system values, by using functions like GETDATE():

```sql
CREATE TABLE Orders (
    ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```

**SQL DEFAULT on ALTER TABLE**

```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```

**DROP a DEFAULT Constraint**

```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```


---


## [SELECT Statement](https://dev.mysql.com/doc/refman/8.0/en/select.html)

The `SELECT` statement is used to select data from a database. The data returned is stored in a result table, called the result-set.

```mysql
SELECT column1, column2, ...
FROM table_name;
```

**SELECT DISTINCT**
```mysql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```


### ORDER BY  Clause

The `ORDER BY` keyword is used to sort the result-set in ascending or descending order.

The `ORDER BY` keyword sorts the records in ascending order by default. To sort the records in descending order, use the `DESC` keyword.

```sql
SELECT _column1_, _column2, ..._  
FROM _table_name_  
ORDER BY _column1, column2, ..._ ASC|DESC; # Muliple column means 
``` 

**Examples :**
```sql
 SELECT DISTINCT released_year, title from books order by 2,1 DESC;  # Here 2 means title i.e. shortcut
```

### Where Clause

-   The `WHERE` clause, if given, indicates the condition or conditions that rows must satisfy to be selected. _`where_condition`_ is an expression that evaluates to true for each row to be selected. The statement selects all rows if there is no `WHERE` clause.
    
    In the `WHERE` expression, you can use any of the functions and operators that MySQL supports, except for aggregate (group) functions. See [Section 9.5, “Expressions”](https://dev.mysql.com/doc/refman/8.0/en/expressions.html "9.5 Expressions"), and [Chapter 12, _Functions and Operators_](https://dev.mysql.com/doc/refman/8.0/en/functions.html "Chapter 12 Functions and Operators").

```mysql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Examples :** 

```sql
SELECT t1.name, t2.salary FROM employee AS t1, info AS t2
  WHERE t1.name = t2.name;

SELECT t1.name, t2.salary FROM employee t1, info t2
  WHERE t1.name = t2.name;
```

### HAVING Clause

The `HAVING` clause, like the `WHERE` clause, specifies selection conditions. The `WHERE` clause specifies conditions on columns in the select list, but cannot refer to aggregate functions. The `HAVING` clause specifies conditions on groups, typically formed by the `GROUP BY` clause. The query result includes only groups satisfying the `HAVING` conditions. (If no `GROUP BY` is present, all rows implicitly form a single aggregate group.)

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _condition_  
GROUP BY _column_name(s)  
_HAVING _condition  
_ORDER BY _column_name(s);_
```

**Examples :**
```sql
SELECT user, MAX(salary) FROM users
  GROUP BY user HAVING MAX(salary) > 10;
```

### LIMIT Clause

The `LIMIT` clause can be used to constrain the number of rows returned by the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "13.2.10 SELECT Statement") statement. `LIMIT` takes one or two numeric arguments, which must both be nonnegative integer constants, with these exceptions:

```MYSQL
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

**Examples :**

```sql
SELECT * FROM tbl LIMIT 5;     # Retrieve first 5 rows
```

```sql
SELECT * FROM tbl LIMIT 5,10;  # Retrieve rows 6-15
```


### DISTINCT modifier
The `SELECT DISTINCT` statement is used to return only distinct (different) values.

```mysql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

### [Join Clause](https://dev.mysql.com/doc/refman/8.0/en/join.html)

A `JOIN` clause is used to combine rows from two or more tables, based on a related column between them.

Joins are of  two type :
	- Implicit 
	- Explicit 

Fundamentally and performance  wise there is no difference between the implicit join and the explicit  joins. Prefer the explicit notation as it makes it easier to read and debug

**Example :**
```mysql
# implicit 
SELECT a.*, b.*
FROM table a, table b
WHERE a.id = b.id;
```

```mysql
# Explicit 
SELECT * FROM
table a INNER JOIN table b
ON a.id = b.id;
```


-   `INNER JOIN`: Returns records that have matching values in both tables
```mysql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

-   `LEFT JOIN`: Returns all records from the left table, and the matched records from the right table
```mysql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

-   `RIGHT JOIN`: Returns all records from the right table, and the matched records from the left table
```mysql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

-   `CROSS JOIN`: Returns all records from both tables ; table order matter

```mysql
[[Explicit]]
SELECT column_name(s)
FROM table1
CROSS JOIN table2;
```

```mysql
# Implicit  -- Don't Use --
SELECT column_name(s)
FROM table1, table2;
```


- `Self Join` : A self join is a regular join, but the table is joined with itself.
```mysql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

![](https://miro.medium.com/max/1200/1*av8Om3HpG1MC7YTLKvyftg.png)

