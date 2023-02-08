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