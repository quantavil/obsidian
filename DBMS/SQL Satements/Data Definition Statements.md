# [Data Definition Statements](https://dev.mysql.com/doc/refman/5.7/en/sql-data-definition-statements.html)

- [[#[CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)|CREATE TABLE Statement]]
	- [[#[CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)#CREATE TABLE .. LIKE Statement|CREATE TABLE .. LIKE Statement]]
	- [[#[CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)#CREATE TABLE .. SELECT Statement|CREATE TABLE .. SELECT Statement]]
	- [[#[CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)#Auto Increment|Auto Increment]]
- [[#DROP TABLE|DROP TABLE]]
- [[#Truncate Table|Truncate Table]]
- [[#[Alter Table](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html)|Alter Table]]
- [[#Create DB|Create DB]]
- [[#DROP DATABASE Statement|DROP DATABASE Statement]]

---

## [CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)

**Tables**
A table is an organized collection of data stored in the form of rows and columns. Columns can be categorized as vertical and rows as horizontal. The columns (Header) in a table are called fields while the rows(the actual data) can be referred to as records.

`SHOW TABLES;` : List the Tables that exists.
`SHOW COLUMNS FROM <table_name>;` < == > `DESC <table_name>;` :  Shows name of columns and datatypes.

```mysql
CREATE TABLE _table_name_ (  
    _column1 datatype_,  
    _column2 datatype_,  
    _column3 datatype_,  
   ....  
);
```

Example : Creating `NOT NULL` Table
```mysql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

### CREATE TABLE .. LIKE Statement

Use `CREATE TABLE ... LIKE` to create an empty table based on the definition of another table, including any column attributes and indexes defined in the original table:

```sql
CREATE TABLE new_tbl LIKE orig_tbl;
```


### CREATE TABLE .. SELECT Statement

To create one table from another, add a [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "13.2.10 SELECT Statement") statement at the end of the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "13.1.20 CREATE TABLE Statement") statement:

```sql
CREATE TABLE new_tbl AS SELECT * FROM orig_tbl;
```

### Auto Increment
Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table. Often this is the primary key field that we would like to be created automatically every time a new record is inserted. 

By default, the starting value for `AUTO_INCREMENT` is 1, and it will increment by 1 for each new record.

```sql
CREATE TABLE Persons (  
    Personid int NOT NULL AUTO_INCREMENT,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int,  
    PRIMARY KEY (Personid)  
);
```

To let the `AUTO_INCREMENT` sequence start with another value, use the following SQL statement:

```sql
ALTER TABLE Persons AUTO_INCREMENT=100;
```




## DROP TABLE 

The `DROP TABLE` statement is used to drop an existing table in a database.
```mysql
DROP TABLE table_name;
```

```sql
DROP [TEMPORARY] TABLE [IF EXISTS]
    tbl_name [, tbl_name] ...
    [RESTRICT | CASCADE]
```

## Truncate Table 

The `TRUNCATE TABLE` statement is used to delete the data inside a table, but not the table itself.

```mysql
TRUNCATE TABLE table_name;
```

## [Alter Table](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html)

The `ALTER TABLE` statement is used to add, delete, or modify columns in an existing table.
The `ALTER TABLE` statement is also used to add and drop various constraints on an existing table.

**ADD Column :**
```mysql
ALTER TABLE table_name
ADD column_name datatype;
```

**Drop Column :**
```mysql
ALTER TABLE _table_name_  
DROP COLUMN _column_name_;
```

**Modify Column :**
```mysql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```


## Create DB

The `CREATE DATABASE` statement is used to create a new SQL database.

```mysql
CREATE DATABASE <databasename>;
```

```sql
CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name
    [create_option] ...

create_option: [DEFAULT] {
    CHARACTER SET [=] charset_name
  | COLLATE [=] collation_name
  | ENCRYPTION [=] {'Y' | 'N'}
}
```

## DROP DATABASE Statement

[`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "13.1.24 DROP DATABASE Statement") drops all tables in the database and deletes the database. Be _very_ careful with this statement! To use [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "13.1.24 DROP DATABASE Statement"), you need the [`DROP`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_drop) privilege on the database. [`DROP SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "13.1.24 DROP DATABASE Statement") is a synonym for [`DROP DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/drop-database.html "13.1.24 DROP DATABASE Statement").

```sql
DROP {DATABASE | SCHEMA} [IF EXISTS] db_name
```


