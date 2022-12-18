## ER Diagram

An **Entity Relationship Diagram** in DBMS is a blueprint of the database that can be later implemented as an actual database in the form of tables. It is a **"diagrammatic representation of the database"**.
![[Pasted image 20221217215133.png]]
![[Pasted image 20221217215317.png]]

**Relationships** are associations of one entity with another entity through a foreign key. Each relationship has a name e.g. a Computer is allocated to an Employee.
![[Pasted image 20221217215938.png]]
There can be more than one relationship between entities, e.g. an Employee **works in** a Department while the head of the department (also an employee) **manages** a Department.
![[Pasted image 20221217215952.png]]
A relationship can also exist between instances of the same entity, e.g. an Employee **reports to** a manager (also an Employee).
![[Pasted image 20221217220001.png]]

**Cardinality of relationship** is the number of instances in one entity which is associated to the number of instances in another. For the relationship between Employee and Computer, it helps us answer questions like how many computers can be allocated to an employee, can computers be shared between employees, can employees exist without being allocated a computer etc. e.g. if 0 or 1 computer can be allocated to 0 or 1 employee then the cardinality of relationship between these two entities will be 1:1.

Cardinality of relationships are of three types: 1:1, 1:N and M:N.

![[Pasted image 20221218111443.png]]

**Crow foot notation** is one of the approaches to represent the cardinality of relationship in an ER Model. The notation comprises of four symbols and one of them needs to be used for each entity in a relationship.

![[Pasted image 20221218111525.png]]

Let us say the relationship between employee and computer is such that a computer must be allocated to one and only one employee but an employee can be allocated with zero or any number of computers. Such a relationship is represented by the diagram below:

![[Pasted image 20221218111708.png]]

Foreign keys has to be created in tables in order to establish the relationship between entities.
![[Pasted image 20221218111753.png]]
![[Pasted image 20221218111803.png]]
![[Pasted image 20221218111811.png]]
