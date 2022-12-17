Software Applications that utilizes data are relied upon to meet a few necessities of end-users. Let us take the example of a Facebook application.
![[Pasted image 20221217192455.png]]

Data is stored in flat files and can be accessed using any programming language. The file-based approach suffers following problems:

1.  Dependency of program on physical structure of data
    
2.  Complex process to fetch data
    
3.  Loss of data on simultaneous access
    
4.  Inability to give access based on record (Security)
    
5.  Data redundancy

A **Database** is a shared collection of logically related data and description of these data, designed to meet the information needs of an organization.

A **Database Management System(DBMS)** is a software system that enables users to define, create, maintain, and control access to the database.

An **Application Program** communicates with a database by issuing an appropriate request (typically a SQL statement)

![[Pasted image 20221217192759.png]]

Database systems are categorized into four types based upon the underlying structure used to store data. These database systems in chronological order of their evolution are Hierarchical, Network, Relational and NoSql. We will now get a brief overview of these database management systems.

![[Pasted image 20221217193541.png]]

-  Relational Databases store data in relations i.e. tables. Each relation must have a name.
![[Pasted image 20221217194826.png]]
![[Pasted image 20221217194846.png]]
Cardinality of relation is the number of rows it contains. e.g. Cardinality of relation below is 4.
Degree of relation is the number of attributes it contains. e.g. Degree of relation below is 5.
![[Pasted image 20221217194938.png]]