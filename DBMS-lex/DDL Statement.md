
# Create Table
```sql
CREATE TABLE table_name  
(   
  column1 datatype [ NULL | NOT NULL ],  
  column2 datatype [ NULL | NOT NULL ],  
  ...  
  column_n datatype [ NULL | NOT NULL ]  
);  
```


# Constraints
Constraints are classified into different types based on the number of columns they act upon as well as on the way they are specified.

![[Pasted image 20221228113906.png]]
![[Pasted image 20221228113955.png]]

Various constraints that can be created on database tables are:

-   **NOT NULL**
    
-   **PRIMARY KEY**
    
-   **CHECK**
    
-   **UNIQUE**
    
-   **FOREIGN KEY**
    

We can also specify DEFAULT value for a column. Oracle database does not consider DEFAULT as a constraint.
# Alter Table

We need to use **ALTER TABLE** command through which the structure of the existing table can be changed without any loss of data. It can also be used to rename a column, change the data type of a column and to add or remove constraints.

![[Pasted image 20221228095803.png]]

