## TDD

_**TDD**_ is an iterative development process. Each iteration starts with a set of tests written for a new piece of functionality. These tests are supposed to fail during the start of iteration as there will be no application code corresponding to the tests. In the next phase of the iteration, Application code is written with an intention to pass all the tests written earlier in the iteration. Once the application code is ready tests are run.

![[Pasted image 20230207112025.png]]


### Benefits of TDD

1.  Unit test proves that the code actually works
2.  Can drive the design of the program
3.  Refactoring allows improving the design of the code
4.  Low-Level regression test suite
5.  Test first reduce the cost of the bugs

### Drawbacks of TDD

1.  Developer can consider it as a waste of time
2.  The test can be targeted on verification of classes and methods and not on what the code really should do
3.  Test become part of the maintenance overhead of a project
4.  Rewrite the test when requirements change


## ATDD
Acceptance Test-Driven Development (ATDD) methodology was a result of the natural evolution of TDD.It involves driving the entire application development by acceptance tests rather than requirement specifications to bring in the business analysts/customer perspective too.

![[Pasted image 20230207112704.png]]

### Benefits:

1.  **Better quality:** There is a reduction in the acceptance of test defects.
    
2.  **Better efficiency:** There is no code wastage in terms of excess modules.
    
3.  **Better confidence:** The business analyst is assured at each stage that the application is built as per their specifications.
    
4.  **Lesser documentation:** The acceptance tests and unit tests themselves serve as the specification documents. Also, there are no separate handover documents to be passed between business analysts and developers.