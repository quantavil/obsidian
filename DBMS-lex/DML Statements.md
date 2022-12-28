Insert statement is used to add tuples (records) to the table. It supports three alternate syntaxes as shown below:

![[Pasted image 20221228144021.png]]

If column names are not used then values must be provided for all columns in the order of their specification during table creation.

If column names are used then the data provided in the values clause must have the same data type of column at same position.

Multiple rows can be inserted through a single INSERT statement only when it is used with SELECT statement. You will learn about SELECT QUERY shortly.

**Syntax: (Inserting a single record using the Values keyword):**

```sql
INSERT INTO table  
(column1, column2, ... column_n )  
VALUES  
(expression1, expression2, ... expression_n );   
```

**Syntax: (Inserting multiple records using a SELECT statement):**

```sql
INSERT INTO table  
(column1, column2, ... column_n )  
SELECT expression1, expression2, ... expression_n  
FROM source_table  
WHERE conditions;  
```

```sql
INSERT INTO suppliers  
(supplier_id, supplier_name)  
SELECT age, address  
FROM customers  
WHERE age > 20;  
```

## Select Statement

With the SELECT clause of a SELECT command statement, we specify the columns that we want to be displayed in the query result and, optionally, which column headings we prefer to see above the result table.

![[Pasted image 20221228150435.png]]

## Order of Query Execution

A SELECT statement can have many clauses so it is important to understand the order in which these are executed to provide the result. However, for ease of understanding we can refer to the execution order by FJWGHSDO.

![[Pasted image 20221228153619.png]]

A quick way to remember this is to use the mnemonic "Frank John's Wicked Grave Haunts Several Dull Owls". In this section we will focus on FROM, WHERE, SELECT and DISTINCT keywords.

The first step is always the FROM clause as we need to identify the tables from which data has to be fetched.

SELECT must be always be executed after the WHERE clause, e.g. we can have a query