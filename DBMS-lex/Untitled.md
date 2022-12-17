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

**Domain, Attribute, Tuple, and Relations**

---

**Attributes**

In relational model terminology all the column headers are called attributes. Consider a table STUDENT. In this table there are three column headers, it means this table has three attributes **RollNo, Name, Address

Roll No

 Name

Address

2

Komal

Delhi









**

**Domain**

**“The set of permitted values for each attribute is called domain” or “A domain is referred to in a relation schema by the attribute name and has a set of associated values”.** A domain D is a set of atomic values. By Atomic we mean that each value in the domain is individual as far as the relational model is concerned. “The data type describing the types of values that can appear in each column is represented by a domain of possible values.” For example Set_phone_number can be declared as of character strings. The data type for Employee_ages is an integer number between 15 and 80. For academic_deaprtment_names, the data type is the set of all characters strings that represent valid department names. A domain is thus given a name, data type, and format.

**Tuples / Records**

**In relational model terminology all the rows are called tuples or records in the relation. Consider a table STUDENT. In this table there are six rows, it means there six tuples or records in this table

[![](https://sites.google.com/site/merasemester/_/rsrc/1305106444614/dbm/relational-model/tuple_record.bmp)](https://sites.google.com/site/merasemester/dbm/relational-model/tuple_record.bmp?attredirects=0)

**

**Relation schema**

**“The relation schema describes the column headers for the table or relation”.** A relation schema R denoted by R (A1, A2, A3…An), is made up of a relation name R and a list of attributes A1, A2, A3… An. Each attribute Aj, is the name of role played by some domain D in the relation schema R. D is called domain of Aj and is denoted by **dom (Aj)**. A relation schema is used to describe a relation R, and R is called the name of this relation. **“The degree (or arity) of a relation is the number of attributes of its relation schema”.**  
An example of a relation schema for a relation degree seven, which describes university students, is the following  
  
STUDENT (Name, RollNo, HomePhone, Address, OfficePhone, Age, GPA)  
Using the data type of each attribute, the definition is sometimes written as:  
STUDENT (Name: string, RollNo: string, HomePhone: string, Address: string, OfficePhone: string, Age: number, GPA: real)


## Data Integrity 

Data integrity refers to maintaining and assuring the accuracy and consistency of data over its entire life-cycle. Database Systems ensure data integrity through constraints which are used to restrict data that can be entered or modified in the database. Database Systems offer three types of integrity constraints:

![[Pasted image 20221217205839.png]]

A **Candidate Key** is a minimal set of columns/attributes that can be used to uniquely identify a single row/tuple in a relation. Candidate Keys are identified during database design, considering the basic business rules of the database. Consider the following relation with regards to a business firm:

![[Pasted image 20221217210115.png]]
A **Primary** **Key** is the candidate key that is chosen to uniquely identify a row in a relation. The mandatory and desired attributes for a primary key are:

![[Pasted image 20221217210149.png]]

A **Foreign Key** is a set of one or more columns in the child table whose values are required to match with corresponding columns in the parent table. Foreign key establishes a relationship between these two tables. Foreign key columns identified in child tables must refer to the primary key or unique key of the parent table. The child table can contain NULL values. Let us take an example of Employee and Computer tables as given below:

![[Pasted image 20221217210237.png]]