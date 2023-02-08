The persistence phenomenon consists of three core components: **data, medium and storage**


1.  The **data** that needs to be persisted can be:
    
    -   **Raw data:** which is collected from a file or any other source in the form of bytes.
        
    -   **Java object:** which is the data contained in the object of a Java class.
        
2.  To persist the data, Java provides **media** like : %%how to persist%%
    
    -   I/O Streams and Serialization
        
    -   JDBC
        
    -   ORM Frameworks like Hibernate
        
3.  RAM or secondary **storage** device like hard drive can be used to persist the data. Additionally, logical storage devices like Database or file system(local and remote) can also be used as a placeholder for the data.
    

In this course, we will focus on **how to persist** data.


## Object-Relational impedance mismatch 
JDBC, I/O and Serialization does not solve the problem of data persistence effectively. For a medium to be effective, it needs to take care of the fundamental difference in the way Object Oriented Programs(OOP) and RDBMS deals with the data.

-   In Object Oriented Programming language like Java, the data will be stored in hierarchical and interrelated **objects.**
-   In relational database the data is stored in a **tabular** format or relations.

The mismatches are:
-   **Granularity:** Mismatch between the number of classes in object model and number of tables in relational model.
-   **Inheritance or Subtype:** Inheritance is an object oriented paradigm which is not available in RDBMS.
-   **Associations:** In object oriented programming, association is represented using reference variables, whereas, in relational model foreign keys are used for associating two tables. 
-   **Identity:** In Java, object equality is determined by "=="  operator or "equals()" method, whereas, in RDBMS primary key is used to uniquely identify the records.
-   **Data Navigation:** In Java, dot(.) operator is used to travel through object network, whereas, in RDBMS join operation is used to navigate between related records.

To Solve Object-Relational Impedance Mismatch we use ORM **Object Relational Mapping**:
-   The lower level interaction with database is handled by the ORM. Framing and executing the database dependent queries is taken care by the ORM framework.
-  No need of SQL
-   ORM allows the developer to concentrate on the business logic and work with the object model.
-   ORM is database independent.(Portable)

Object Relational Mapping (ORM) is a programming technique for mapping Java Entity class to a relational database table, where
-   **Java Entity class** is mapped to a **table**
-   **Data members** of a class are mapped to **table columns**
-   **Instance** of a Java Entity class is mapped to a **record** in a table

```ad-example
![[Pasted image 20230208121051.png]]

In this example,

-   Java **Entity class Account** is mapped to a **table Account**
    
-   **Data members id and balance** of Account class are mapped to the **table columns Id and Balance**
    
-   **Instance of Account** class with values 1001(id) and 50000(balance) is a **record(row) in a table**
```

**Java Persistence API (JPA)** was released by Java Community Process, to standardize the persistence process. It provides certain functionality and standard to ORM tools. e.g. EclipseLink, OpenJPA and Hibernate.

**Advantages of Hibernate Framework :**

-  1) Open Source and Lightweight
-  2) Fast Performance 
-  3) Database Independent Query
	HQL (Hibernate Query Language) is the object-oriented version of SQL. It generates the database independent queries. So you don't need to write database specific queries. 
-  4) Automatic Table Creation
-  5) Simplifies Complex Join
	Fetching data from multiple tables is easy in hibernate framework.
