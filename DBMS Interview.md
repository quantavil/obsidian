  ## 1. List different **advantages** of DBMS. 

Answer: The following are the advantages of DBMS

-   **Reducing Data Redundancy**: Redundancy refers to duplicate data.

Consider one example in which, there was a file system with multiple files in it on different locations so it might be duplicate files in it.

-   **Data Consistency:** We will see Data Consistency with an example, consider one bank example in which user A has Rs. 500 in his account and user B has Rs. 100 in an account, they do one transaction where user A transfers the Rs.50 to user B. Now the total balance of user A’s account balance is Rs. 450 and user B’s account balance is Rs. 150.

So you can see that the before transaction amount and after transaction amount is the same, so here is the data consistency.

-   **Data Integrity**: Data Integrity is the term in which data is accurate and consistent in the database. Data Integrity is important based on multiple databases. Because all databases contain data and show the proper data to the proper user.
-   **Data Security**: Only authorized user should access the database. For authenticating purpose all users have a proper username and password.
-   **Privacy:** The privacy in the database in which only the authorized person/users can access the database according to its privacy constraints. Like in social media each user has a different privilege.

## 2. What is **database Schema**? 

Answer: Database schema is a descriptive detail of the database. The database schema is the logical view of the entire database. It defines how data is organized and relate to the data.

The database schema has two types:

-   Physical schema: This type of schema is related to the actual storage of data and data is in which form like in indexes, files, etc. It relates to how data is stored in secondary storage.
-   Logical schema: The logical schema defines the logical constraints that need to be applied to data stored. The logical schema defines tables, integrity constraints and views.

We can also say that database schema is the logical structure of the database and database instance is the actual content of the database.

## 3.What is **database Instance**? 

Answer: Database Instance is a snapshot of the database. It changes with time, on the other hand, in the database schema is difficult to make changes. The database ensures that every instance is in a valid state.

## 4.What is **RDBMS**? 

Answer: RDBMS (Relational Database Management System) is a platform for the developer to make changes or interact with a database like inserting, updating, deleting, creating, altering, etc. All this is done by SQL queries.

## 5.Explain the difference between **primary key, foreign key and a unique key**. 

Answer: Firstly we see the definitions,

-   **Primary Key / Reference Key**: The Primary Key is a column in the table, which contain unique values that's why it’s called as unique identifies. Primary key does not accept _null values_ and _duplicate values_.
-   **Foreign Key:** The Foreign Key is used to connect the two tables. It also has a column in the table and has a field or collection of the field which is the primary key in another table.
-   **Unique Key**: The Unique Key means all fields value are unique. But the main difference between primary key and the unique key is that unique key accepts _null values_, where the primary key is not to accept the _null values_.

## 6.Differentiate between **Char** and **Varchar** in DBMS? 

Answer: char stores only fixed-length character string data types whereas varchar stores variable-length string where an upper limit of length is specified

## 7.Difference between **DDL** and **DML** in DBMS? 

_DDL_: DDL is Data Definition Language which is used to define data structures. For example: create table, alter table are instructions in SQL.

_DML_: DML is Data Manipulation Language which is used to manipulate data itself. For example: insert, update, delete are instructions in SQL.


## 9.What is a **Join**? List its different types. 
The SQL Join clause is used to combine records (rows) from two or more tables in a SQL database based on a related column between the two.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/001/015/original/sql_join.jpg?1631020327)

There are four different types of JOINs in SQL:

-   **(INNER) JOIN:** Retrieves records that have matching values in both tables involved in the join. This is the widely used join for queries.

```sql
SELECT *
FROM Table_A
JOIN Table_B;
SELECT *
FROM Table_A
INNER JOIN Table_B;
```

-   **LEFT (OUTER) JOIN:** Retrieves all the records/rows from the left and the matched records/rows from the right table.

```sql
SELECT *
FROM Table_A A
LEFT JOIN Table_B B
ON A.col = B.col;
```

-   **RIGHT (OUTER) JOIN:** Retrieves all the records/rows from the right and the matched records/rows from the left table.

```sql
SELECT *
FROM Table_A A
RIGHT JOIN Table_B B
ON A.col = B.col;
```

-   **FULL (OUTER) JOIN:** Retrieves all the records where there is a match in either the left or right table.

```sql
SELECT *
FROM Table_A A
FULL JOIN Table_B B
ON A.col = B.col;
```

## 10. What is a **Self-Join**? 

A self JOIN is a case of regular join where a table is joined to itself based on some relation between its own column(s). Self-join uses the INNER JOIN or LEFT JOIN clause and a table alias is used to assign different names to the table within the query.

SELECT A.emp_id AS "Emp_ID",A.emp_name AS "Employee",

B.emp_id AS "Sup_ID",B.emp_name AS "Supervisor"

FROM employee A, employee B

WHERE A.emp_sup = B.emp_id;


## 11. What are **Constraints** in SQL?

Constraints are used to specify the rules concerning data in the table. It can be applied for single or multiple fields in an SQL table during the creation of the table or after creating using the ALTER TABLE command. The constraints are:

-   **NOT NULL** - Restricts NULL value from being inserted into a column.
-   **CHECK** - Verifies that all values in a field satisfy a condition.
-   **DEFAULT** - Automatically assigns a default value if no value has been specified for the field.
-   **UNIQUE** - Ensures unique values to be inserted into the field.
-   **INDEX** - Indexes a field providing faster retrieval of records.
-   **PRIMARY KEY** - Uniquely identifies each record in a table.
-   **FOREIGN KEY** - Ensures referential integrity for a record in another table.

## 12. What is an **Index**?
It quick lookup of data in a column or columns of a table. It enhances the speed of operations accessing data from a database table at the cost of additional writes and memory to maintain the index data structure.

```sql
CREATE INDEX index_name   /* Create Index */
ON table_name (column_1, column_2);
DROP INDEX index_name;   /* Drop Index */
```

## 13. What is a **Query**?

A query is a request for data or information from a database table or combination of tables. A database query can be either a select query or an action query.

```sql
SELECT fname, lname    /* select query */
FROM myDb.students
WHERE student_id = 1;
```

```sql
UPDATE myDB.students    /* action query */
SET fname = 'Captain', lname = 'America'
WHERE student_id = 1;
```

## 14. What is a **Subquery**? 

A subquery is a query within another query, also known as a **nested query** or **inner query**. It is used to restrict or enhance the data to be queried by the main query, thus restricting or enhancing the output of the main query respectively. For example, here we fetch the contact information for students who have enrolled for the maths subject:

```sql
SELECT name, email, mob, address
FROM myDb.contacts
WHERE roll_no IN (
 SELECT roll_no
 FROM myDb.students
 WHERE subject = 'Maths');
```

## 15. What is the **SELECT** statement?

SELECT operator in SQL is used to select data from a database. The data returned is stored in a result table, called the result-set.

```sql
SELECT * FROM myDB.students;
```

## 16. What are some common **clauses used with SELECT** query in SQL?

Some common SQL clauses used in conjuction with a SELECT query are as follows:

-   **WHERE** clause in SQL is used to filter records that are necessary, based on specific conditions.
-   **ORDER BY** clause in SQL is used to sort the records based on some field(s) in ascending (**ASC**) or descending order (**DESC)**.

```sql
SELECT *
FROM myDB.students
WHERE graduation_year = 2019
ORDER BY studentID DESC;
```

-   **GROUP BY** clause in SQL is used to group records with identical data and can be used in conjunction with some aggregation functions to produce summarized results from the database.
-   **HAVING** clause in SQL is used to filter records in combination with the GROUP BY clause. It is different from WHERE, since the WHERE clause cannot filter aggregated records.

```sql
SELECT COUNT(studentId), country
FROM myDB.students
WHERE country != "INDIA"
GROUP BY country
HAVING COUNT(studentID) > 5;
```

## 17. What are **UNION, MINUS and INTERSECT** commands?

The **UNION** operator combines and returns the result-set retrieved by two or more SELECT statements.  
The **MINUS** operator in SQL is used to remove duplicates from the result-set obtained by the second SELECT query from the result-set obtained by the first SELECT query and then return the filtered results from the first.  
The **INTERSECT** clause in SQL combines the result-set fetched by the two SELECT statements where records from one match the other and then returns this intersection of result-sets.


## 18. What is **Cursor**? How to use a Cursor?

A database cursor is a control structure that allows for the traversal of records in a database. Cursors, in addition, facilitates processing after traversal, such as retrieval, addition, and deletion of database records. They can be viewed as a pointer to one row in a set of rows.

**Working with SQL Cursor:**

1.  **DECLARE** a cursor after any variable declaration. The cursor declaration must always be associated with a SELECT Statement.
2.  Open cursor to initialize the result set. The **OPEN** statement must be called before fetching rows from the result set.
3.  **FETCH** statement to retrieve and move to the next row in the result set.
4.  Call the **CLOSE** statement to deactivate the cursor.
5.  Finally use the **DEALLOCATE** statement to delete the cursor definition and release the associated resources.


## 19. What are **Entities** and **Relationships**?

**Entity**: An entity can be a real-world object, either tangible or intangible, that can be easily identifiable. For example, in a college database, students, professors, workers, departments, and projects can be referred to as entities. Each entity has some associated properties that provide it an identity.

**Relationships**: Relations or links between entities that have something to do with each other. For example - The employee's table in a company's database can be associated with the salary table in the same database.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/001/016/original/Entities_and_Relationships.jpg?1631024896)

## 20. List the different **types of relationships** in SQL.

-   **One-to-One** - This can be defined as the relationship between two tables where each record in one table is associated with the maximum of one record in the other table.
-   **One-to-Many & Many-to-One** - This is the most commonly used relationship where a record in a table is associated with multiple records in the other table.
-   **Many-to-Many** - This is used in cases when multiple instances on both sides are needed for defining a relationship.
-   **Self-Referencing Relationships** - This is used when a table needs to define a relationship with itself.

## 21. What is an **Alias** in SQL?

It is a temporary name assigned to the table or table column for the purpose of a particular SQL query.
An alias is represented explicitly by the *AS* keyword but in some cases, the same can be performed without it as well. Nevertheless, using the AS keyword is always a good practice.

```sql
SELECT A.emp_name AS "Employee"  /* Alias using AS keyword */
B.emp_name AS "Supervisor"
FROM employee A, employee B   /* Alias without AS keyword */
WHERE A.emp_sup = B.emp_id;
```

## 22. What is a **View**?

A view in SQL is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/001/017/original/SQL_View.jpg?1631025207)


## 23. What is **Denormalization**?

Denormalization is the inverse process of normalization, where the normalized schema is converted into a schema that has redundant information. The performance is improved by using redundancy and keeping the redundant data consistent. The reason for performing denormalization is the overheads produced in the query processor by an over-normalized structure.

## 24. What are the various **forms of Normalization**?

Normal Forms are used to eliminate or reduce redundancy in database tables. The different forms are as follows:

-   **First Normal Form:**  
    A relation is in first normal form if every attribute in that relation is a **single-valued attribute**. If a relation contains a composite or multi-valued attribute, it violates the first normal form. Let's consider the following **students** table. Each student in the table, has a name, his/her address, and the books they issued from the public library -


-   **Second Normal Form:**

A relation is in second normal form if it satisfies the conditions for the first normal form and does not contain any partial dependency. A relation in 2NF has **no partial dependency**, i.e., it has no non-prime attribute that depends on any proper subset of any candidate key of the table. Often, specifying a single column Primary Key is the solution to the problem. Examples -


-   **Third Normal Form**

A relation is said to be in the third normal form, if it satisfies the conditions for the second normal form and there is **no transitive dependency** between the non-prime attributes, i.e., all non-prime attributes are determined only by the candidate keys of the relation and not by any other non-prime attribute.


-   **Boyce-Codd Normal Form**

A relation is in Boyce-Codd Normal Form if satisfies the conditions for third normal form and for every functional dependency, Left-Hand-Side is super key. In other words, a relation in BCNF has non-trivial functional dependencies in form X –> Y, such that X is always a super key. For example - In the above example, Student_ID serves as the sole unique identifier for the Students Table and Salutation_ID for the Salutations Table, thus these tables exist in BCNF. The same cannot be said for the Books Table and there can be several books with common Book Names and the same Student_ID.

## 26. What are the **TRUNCATE, DELETE and DROP** statements?

**DELETE** statement is used to delete rows from a table.

```sql
DELETE FROM Candidates
WHERE CandidateId > 1000;
```

**TRUNCATE** command is used to delete all the rows from the table and free the space containing the table.

```sql
TRUNCATE TABLE Candidates;
```

**DROP** command is used to remove an object from the database. If you drop a table, all the rows in the table are deleted and the table structure is removed from the database.

```sql
DROP TABLE Candidates;
```
\



## 27. What are **Aggregate and Scalar** functions?

An aggregate function performs operations on a collection of values to return a single scalar value. Aggregate functions are often used with the GROUP BY and HAVING clauses of the SELECT statement. Following are the widely used SQL aggregate functions:

-   **AVG()** - Calculates the mean of a collection of values.
-   **COUNT()** - Counts the total number of records in a specific table or view.
-   **MIN()** - Calculates the minimum of a collection of values.
-   **MAX()** - Calculates the maximum of a collection of values.
-   **SUM()** - Calculates the sum of a collection of values.
-   **FIRST()** - Fetches the first element in a collection of values.
-   **LAST()** - Fetches the last element in a collection of values.

**Note:** All aggregate functions described above ignore NULL values except for the COUNT function.

A scalar function returns a single value based on the input value. Following are the widely used SQL scalar functions:

-   **LEN()** - Calculates the total length of the given field (column).
-   **UCASE()** - Converts a collection of string values to uppercase characters.
-   **LCASE()** - Converts a collection of string values to lowercase characters.
-   **MID()** - Extracts substrings from a collection of string values in a table.
-   **CONCAT()** - Concatenates two or more strings.
-   **RAND()** - Generates a random collection of numbers of a given length.
-   **ROUND()** - Calculates the round-off integer value for a numeric field (or decimal point values).
-   **NOW()** - Returns the current date & time.
-   **FORMAT()** - Sets the format to display a collection of values.

## 28. What is **User-defined function**? What are its various types?

The user-defined functions in SQL are like functions in any other programming language that accept parameters, perform complex calculations, and return a value. They are written to use the logic repetitively whenever required. There are two types of SQL user-defined functions:

-   Scalar Function: As explained earlier, user-defined scalar functions return a single scalar value.
-   Table-Valued Functions: User-defined table-valued functions return a table as output.
    -   **Inline:** returns a table data type based on a single SELECT statement.
    -   **Multi-statement:** returns a tabular result-set but, unlike inline, multiple SELECT statements can be used inside the function body.

## 29. What are the differences between **OLTP** and **OLAP**?

**OLTP** stands for **Online Transaction Processing**, is a class of software applications capable of supporting transaction-oriented programs. An important attribute of an OLTP system is its ability to maintain concurrency. OLTP systems often follow a decentralized architecture to avoid single points of failure. These systems are generally designed for a large audience of end-users who conduct short transactions. Queries involved in such databases are generally simple, need fast response times, and return relatively few records. A number of transactions per second acts as an effective measure for such systems.

**OLAP** stands for **Online Analytical Processing**, a class of software programs that are characterized by the relatively low frequency of online transactions. Queries are often too complex and involve a bunch of aggregations. For OLAP systems, the effectiveness measure relies highly on response time. Such systems are widely used for data mining or maintaining aggregated, historical data, usually in multi-dimensional schemas.


## 30. What is Collation? What are the different types of Collation Sensitivity?

Collation refers to a set of rules that determine how data is sorted and compared. Rules defining the correct character sequence are used to sort the character data. It incorporates options for specifying case sensitivity, accent marks, kana character types, and character width. Below are the different types of collation sensitivity:

-   **Case sensitivity:** **A** and **a** are treated differently.
-   **Accent sensitivity:** **a** and **á** are treated differently.
-   **Kana sensitivity:** Japanese kana characters Hiragana and Katakana are treated differently.
-   **Width sensitivity:** Same character represented in single-byte (half-width) and double-byte (full-width) are treated differently.

## 31. What is a Stored Procedure?

A stored procedure is a subroutine available to applications that access a relational database management system (RDBMS). Such procedures are stored in the database data dictionary. The sole disadvantage of stored procedure is that it can be executed nowhere except in the database and occupies more memory in the database server. It also provides a sense of security and functionality as users who can't access the data directly can be granted access via stored procedures.

```sql
DELIMITER $$
CREATE PROCEDURE FetchAllStudents()
BEGIN
SELECT *  FROM myDB.students;
END $$
DELIMITER ;
```

![](https://s3.ap-south-1.amazonaws.com/myinterviewtrainer-domestic/public_assets/assets/000/001/024/original/Stored_Procedure.jpg?1631032812)

## 32. What is a Recursive Stored Procedure?

A stored procedure that calls itself until a boundary condition is reached, is called a recursive stored procedure. This recursive function helps the programmers to deploy the same set of code several times as and when required. Some SQL programming languages limit the recursion depth to prevent an infinite loop of procedure calls from causing a stack overflow, which slows down the system and may lead to system crashes.

```sql
DELIMITER $$     /* Set a new delimiter => $$ */
CREATE PROCEDURE calctotal( /* Create the procedure */
   IN number INT,   /* Set Input and Ouput variables */
   OUT total INT
) BEGIN
DECLARE score INT DEFAULT NULL;   /* Set the default value => "score" */
SELECT awards FROM achievements   /* Update "score" via SELECT query */
WHERE id = number INTO score;
IF score IS NULL THEN SET total = 0;   /* Termination condition */
ELSE
CALL calctotal(number+1);   /* Recursive call */
SET total = total + score;   /* Action after recursion */
END IF;
END $$     /* End of procedure */
DELIMITER ;     /* Reset the delimiter */
```


## 33. What is Pattern Matching in SQL?

SQL pattern matching provides for pattern search in data if you have no clue as to what that word should be. This kind of SQL query uses wildcards to match a string pattern, rather than writing the exact word. The LIKE operator is used in conjunction with **SQL Wildcards** to fetch the required information.

-   **Using the % wildcard to perform a simple search**

The % wildcard matches zero or more characters of any type and can be used to define wildcards both before and after the pattern. Search a student in your database with first name beginning with the letter K:

```sql
SELECT *
FROM students
WHERE first_name LIKE 'K%'
```

-   **Omitting the patterns using the NOT keyword**

Use the NOT keyword to select records that don't match the pattern. This query returns all students whose first name does not begin with K.

```sql
SELECT *
FROM students
WHERE first_name NOT LIKE 'K%'
```

-   **Matching a pattern anywhere using the % wildcard twice**

Search for a student in the database where he/she has a K in his/her first name.

```sql
SELECT *
FROM students
WHERE first_name LIKE '%Q%'
```

-   **Using the _ wildcard to match pattern at a specific position**

The _ wildcard matches exactly one character of any type. It can be used in conjunction with % wildcard. This query fetches all students with letter K at the third position in their first name.

```sql
SELECT *
FROM students
WHERE first_name LIKE '__K%'
```

-   **Matching patterns for a specific length**

The _ wildcard plays an important role as a limitation when it matches exactly one character. It limits the length and position of the matched results. For example - 

```sql
SELECT *   /* Matches first names with three or more letters */
FROM students
WHERE first_name LIKE '___%'

SELECT *   /* Matches first names with exactly four characters */
FROM students
WHERE first_name LIKE '____'
```

