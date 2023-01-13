Software quality is the degree to which a process, component or system conforms to the specified requirements and user expectations.

## Characteristics of Software Quality

As per ISO standard model (ISO/IEC 9126), the quality of a software can be evaluated based on its following characteristics.

![[Pasted image 20230113095550.png]]

## Software Testing

Software testing is an activity (or set of activities) performed to compare the expected outcome with the actual outcome of one specific task in the system, component or process and report the defects found in the system.

## Defect

A defect is a fault in the system, component or process due to which the expected outcome and the actual outcome of a test activity do not match.  
The other terms used to refer to a defect are bug, error, anomaly, etc.

**Software Testing** is the generic term applied to all the activities that are performed to ensure that the quality characteristics of the software meet the required/expected standards. 

**The objective of software testing is to eliminate defects in a software by**

1.  Preventing defects from entering the software
    
2.  Identifying and reporting the defects existing in the software

## Catgeorization

At a very high level tests are categorized as

-   **Formal tests** : Tests that document their expected results, actual results and defects found.
    
-   **Informal tests** : Tests that are not documented completely.
![[Pasted image 20230113101944.png]]

### Static Test
![[Pasted image 20230113102043.png]]

### Dynamic Test
![[Pasted image 20230113103214.png]]

## Quality Assurance and Quality Control

![[Pasted image 20230113104117.png]]

## The V-Model

The V-Model is an extension of the Waterfall Model of software development with time represented along the X-axis. It is called so for 2 reasons.

-   The sequence in which the project definition, project implementation and project completion stages are presented, resembles the letter 'V'.
    
-   It represents 'Validation Model' since it elaborates the testing (validation) stage of  Waterfall Model in relation to the other stages in it.

![[Pasted image 20230113113613.png]]

### Unit Testing (UT)

**Entity Tested** : Individual units (modules or functions or libraries) of code

**Objective** : To validate whether the individual units of code return the right outputs for given inputs as specified in the design and whether they conform to coding standards. It uses white box testing techniques.

**Performed by** : Development Team

### Integration Testing (IT)

**Entity Tested** : Groups of individual units of code that are supposed to work together

**Objective** : To validate whether all the individual units of code pass the right information to each other to achieve the objective of the software (or its component) as specified in the design. It uses white box testing techniques.

**Performed by** : Development team

### System Testing (ST)

**Entity Tested** : Software and its components

**Objective** : To validate whether the software and its components are working as stated in the software requirement specification. It uses black box testing techniques.

**Performed by** : Testing team

### User Acceptance Testing (UAT)

**Entity Tested** : Software and its components

**Objective** : To validate whether the software and its components are working as stated in the business requirement specification and are good enough to be deployed for real-time usage. It uses black box testing techniques