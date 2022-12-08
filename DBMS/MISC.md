# GOTO



`SHOW DATABASES;` : List the databases that exist.
`USE <name>;` : The USE statement **tells MySQL to use the named database as the default (current) database for subsequent statements**.
`DROP DATABASE <name>;`: Drop an existing SQL database.

`SELECT DATABASE();` : Displays the currently used database. Return NULL if no Database is currently in use.

If you are already running **mysql** you can execute an SQL script file using the `source` command or `\.` command:

```mysql
mysql> source _file_name_ 
mysql> \. _file_name_
```

```bash
c:\xampp\mysql\bin
λ cd c:\xampp\mysql\bin

c:\xampp\mysql\bin
λ mysql.exe -u root
```

## Comments

```mysql
mysql> SELECT 1+1;     # This comment continues to the end of line
mysql> SELECT 1+1;     -- This comment continues to the end of line
mysql> SELECT 1 /* this is an in-line comment */ + 1;
mysql> SELECT 1+
/*
this is a
multiple-line comment
*/
1;
```

## Aliases 
The `AS` command is used to rename a column or table with an alias. An alias only exists for the duration of the query.

```mysql
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```
