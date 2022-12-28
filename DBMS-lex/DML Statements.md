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

