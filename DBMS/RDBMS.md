- [[#What is a relationship in DBMS?|What is a relationship in DBMS?]]
- [[#Types of Relationships in DBMS|Types of Relationships in DBMS]]
	- [[#Types of Relationships in DBMS#One-to-One Relationship|One-to-One Relationship]]
	- [[#Types of Relationships in DBMS#One-to-Many Relationship|One-to-Many Relationship]]
	- [[#Types of Relationships in DBMS#Many-to-Many Relationship|Many-to-Many Relationship]]
- [[#Difference between DBMS and RDBMS|Difference between DBMS and RDBMS]]
- [[#Advantages of relational databases|Advantages of relational databases]]


A relational database collects different types of data sets that use tables, records, and columns. It is used to create a well-defined relationship between database tables so that relational databases can be easily stored. For example of relational databases such as Microsoft SQL Server, Oracle Database, MYSQL, etc.

There are some important parameters of the relational database:

-   It is based on a relational model (Data in tables).
-   Each row in the table with a unique id, key.
-   Columns of the table hold attributes of data.

## What is a relationship in DBMS?

An entity in a database management system is a real-life object distinguishable from other objects. These entities have an attribute that defines the properties and characteristics of the entity.

Examples of an entity can be a student, a car, animals, etc. All these are real-life entities whose data can be stored in a database. A student's attributes can be his Id, course, or semester which can describe a student entity.

## Types of Relationships in DBMS

Three types of relationships can exist between two entities of tables, which are given below and discussed with examples.

-   One-to-One relationship
-   One-to-Many relationship or Many-to-One relationship
-   Many-to-Many relationship

### One-to-One Relationship

This type of relationship holds when a record of one table is related to only one record of another table. An example of such a relationship can be the records of people all over India, where each person can have only one Aadhaar card.

![[example-of-one-to-one-relationship-in-dbms.webp]]

### One-to-Many Relationship

This type of relationship holds when one record of a table is related to many records of another table. An example of such a relationship can be an employee and a project database in which a single employee works on multiple projects simultaneously.

![[example-of-a-one-to-many-relationship-in-dbms.webp]]

### Many-to-Many Relationship

This type of relationship holds when many records of one table are related to many records of another table. An example of such a relationship can be a Course database in which more than one teacher can teach multiple courses.

![[example-of-a-many-to-many-relationship-in-dbms.webp]]

## Difference between DBMS and RDBMS

| No.  | 	DBMS 	| RDBMS  |
| --- | --- | --- |
| 1) | 	DBMS applications store data as file. |	RDBMS applications store data in a tabular form.|
| 2) | 	In DBMS, data is generally stored in either a hierarchical form or a navigational form. |	In RDBMS, the tables have an identifier called primary key and the data values are stored in the form of tables.|
| 3) | 	Normalization is not present in DBMS. |	Normalization is present in RDBMS.|
| 4) | 	DBMS does not apply any security with regards to data manipulation. |	RDBMS defines the integrity constraint for the purpose of ACID (Atomocity, Consistency, Isolation and Durability) property.|
| 5) | 	DBMS uses file system to store data, so there will be no relation between the tables. |	in RDBMS, data values are stored in the form of tables, so a relationship between these data values will be stored in the form of a table as well.|
| 6) | 	DBMS does not support distributed database. |	RDBMS supports distributed database.|
| 7) | 	DBMS is meant to be for small organization and deal with small data. it supports single user. |	RDBMS is designed to handle large amount of data. it supports multiple users.|
| 8) | 	Examples of DBMS are file systems, xml etc.  |	Example of RDBMS are mysql, postgre, sql server, oracle etc.|

## Advantages of relational databases

1.  **Simple Model:** The simplest model of the relational database does not require any complex structure or query to process the databases. It has a simple architectural process as compared to a hierarchical database structure. Its simple architecture can be handled with simple SQL queries to access and design the relational database.
2.  **Data Accuracy:** Relational databases can have multiples tables related to each other through primary and foreign keys. There are fewer chances for duplication of data fields. Therefore the accuracy of data in relational database tables is greater than in any other database system.
3.  **Easy to access Data:** The data can be easily accessed from the relational database, and it does not follow any pattern or way to access the data. One can access any data from a database table using SQL queries. Each table in the associated database is joined through any relational queries such as join and conditional descriptions to concatenate all tables to get the required data.
4.  **Security:** It sets a limit that allows specific users to use relational data in RDBMS.
5.  **Collaborate:** It allows multiple users to access the same database at a time.

