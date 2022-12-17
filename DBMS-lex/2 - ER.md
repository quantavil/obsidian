## ER Diagram

An **Entity Relationship Diagram** in DBMS is a blueprint of the database that can be later implemented as an actual database in the form of tables. It is a **"diagrammatic representation of the database"**.
![[Pasted image 20221217215133.png]]
![[Pasted image 20221217215317.png]]

**Relationships** are associations of one entity with another entity through a foreign key. Each relationship has a name e.g. a Computer is allocated to an Employee.

![](https://lex.infosysapps.com/content-store/Infosys/Infosys_Ltd/Public/lex_auth_012702276559421440626/web-hosted/assets/relationship-01.png)

There can be more than one relationship between entities, e.g. an Employee **works in** a Department while the head of the department (also an employee) **manages** a Department.

![](https://lex.infosysapps.com/content-store/Infosys/Infosys_Ltd/Public/lex_auth_012702276559421440626/web-hosted/assets/relationship-02.png)

A relationship can also exist between instances of the same entity, e.g. an Employee **reports to** a manager (also an Employee).

![](https://lex.infosysapps.com/content-store/Infosys/Infosys_Ltd/Public/lex_auth_012702276559421440626/web-hosted/assets/relationship-03.png)