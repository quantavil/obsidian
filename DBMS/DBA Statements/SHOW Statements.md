# [SHOW](https://dev.mysql.com/doc/refman/8.0/en/show.html)

- [[#SHOW CREATE TABLE Statement|SHOW CREATE TABLE Statement]]
- [[#SHOW TABLES Statement|SHOW TABLES Statement]]
- [[#SHOW CREATE DATABASE Statement|SHOW CREATE DATABASE Statement]]
- [[#SHOW DATABASES Statement|SHOW DATABASES Statement]]
- [[#SHOW TRIGGERS Statement|SHOW TRIGGERS Statement]]

## SHOW CREATE TABLE Statement

```sql
SHOW CREATE TABLE tbl_name
```

Shows the [`CREATE TABLE`](https://dev.mysql.com/doc/refman/8.0/en/create-table.html "13.1.20 CREATE TABLE Statement") statement that creates the named table. To use this statement, you must have some privilege for the table. This statement also works with views.

```sql
mysql> SHOW CREATE TABLE t\G
*************************** 1. row ***************************
       Table: t
Create Table: CREATE TABLE `t` (
  `id` int NOT NULL AUTO_INCREMENT,
  `s` char(60) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
```

## SHOW TABLES Statement

```sql
SHOW [EXTENDED] [FULL] TABLES
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW TABLES`](https://dev.mysql.com/doc/refman/8.0/en/show-tables.html "13.7.7.39 SHOW TABLES Statement") lists the non-`TEMPORARY` tables in a given database. You can also get this list using the [**mysqlshow _`db_name`_**](https://dev.mysql.com/doc/refman/8.0/en/mysqlshow.html "4.5.7 mysqlshow — Display Database, Table, and Column Information") command. The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates which table names to match. The `WHERE` clause can be given to select rows using more general conditions, as discussed in [Section 26.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "26.8 Extensions to SHOW Statements").

## SHOW CREATE DATABASE Statement

```sql
SHOW CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name
```

Shows the [`CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/create-database.html "13.1.12 CREATE DATABASE Statement") statement that creates the named database. If the `SHOW` statement includes an `IF NOT EXISTS` clause, the output too includes such a clause. [`SHOW CREATE SCHEMA`](https://dev.mysql.com/doc/refman/8.0/en/show-create-database.html "13.7.7.6 SHOW CREATE DATABASE Statement") is a synonym for [`SHOW CREATE DATABASE`](https://dev.mysql.com/doc/refman/8.0/en/show-create-database.html "13.7.7.6 SHOW CREATE DATABASE Statement").

```sql
mysql> SHOW CREATE DATABASE test\G
*************************** 1. row ***************************
       Database: test
Create Database: CREATE DATABASE `test` /*!40100 DEFAULT CHARACTER SET utf8mb4
                 COLLATE utf8mb4_0900_ai_ci */ /*!80014 DEFAULT ENCRYPTION='N' */

mysql> SHOW CREATE SCHEMA test\G
*************************** 1. row ***************************
       Database: test
Create Database: CREATE DATABASE `test` /*!40100 DEFAULT CHARACTER SET utf8mb4
                 COLLATE utf8mb4_0900_ai_ci */ /*!80014 DEFAULT ENCRYPTION='N' */
```


## SHOW DATABASES Statement

```sql
SHOW {DATABASES | SCHEMAS}
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "13.7.7.14 SHOW DATABASES Statement") lists the databases on the MySQL server host. [`SHOW SCHEMAS`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "13.7.7.14 SHOW DATABASES Statement") is a synonym for [`SHOW DATABASES`](https://dev.mysql.com/doc/refman/8.0/en/show-databases.html "13.7.7.14 SHOW DATABASES Statement"). The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates which database names to match. The `WHERE` clause can be given to select rows using more general conditions, as discussed in [Section 26.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "26.8 Extensions to SHOW Statements").


## SHOW TRIGGERS Statement

```sql
SHOW TRIGGERS
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr]
```

[`SHOW TRIGGERS`](https://dev.mysql.com/doc/refman/8.0/en/show-triggers.html "13.7.7.40 SHOW TRIGGERS Statement") lists the triggers currently defined for tables in a database (the default database unless a `FROM` clause is given). This statement returns results only for databases and tables for which you have the [`TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_trigger) privilege. The [`LIKE`](https://dev.mysql.com/doc/refman/8.0/en/string-comparison-functions.html#operator_like) clause, if present, indicates which table names (not trigger names) to match and causes the statement to display triggers for those tables. The `WHERE` clause can be given to select rows using more general conditions, as discussed in [Section 26.8, “Extensions to SHOW Statements”](https://dev.mysql.com/doc/refman/8.0/en/extended-show.html "26.8 Extensions to SHOW Statements").