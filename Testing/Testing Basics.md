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

## Categorization

At a very high level tests are categorized as

-   **Formal tests** : Tests that document their expected results, actual results and defects found.
    
-   **Informal tests** : Tests that are not documented completely.
![[Pasted image 20230113101944.png]]

#### Static Test
![[Pasted image 20230113102043.png]]

#### Dynamic Test
![[Pasted image 20230113103214.png]]

## Quality Assurance and Quality Control

![[Pasted image 20230113104117.png]]

## The V-Model

![[Pasted image 20230113113613.png]]
The V Model in software testing is a graphical representation of the software development life cycle (SDLC) that integrates the testing process into each phase of the software development process. The V-shape of the model represents the linear flow of the process, where each phase of the development process has a corresponding testing phase that verifies the results of the development phase.

The V Model is divided into two main sections: the left side represents the development process, and the right side represents the testing process. The development phases include requirements gathering and analysis, design, implementation, and testing. The testing phases include unit testing, integration testing, system testing, and acceptance testing.

In this model, each testing phase is initiated as soon as the corresponding development phase is completed. For example, unit testing begins as soon as the code has been written, and acceptance testing begins as soon as the system has been integrated and tested.

The V Model emphasizes the importance of testing at every stage of the software development process, from the early stages of requirements gathering to the final stages of acceptance testing. This helps to ensure that the software meets the requirements, is of high quality, and is ready for release.

#### Levels of Testing :

1.  **Requirements Gathering and Analysis:** In this phase, the requirements of the software are gathered and analyzed to ensure that they are complete, accurate, and feasible.
    
2.  **Design:** In this phase, the software design is created, which includes the architecture and the detailed design of the software.
    
3.  **Unit Testing (UT):** In this phase, individual units or components of the software are tested to verify that they are functioning correctly.
    
4.  **Integration Testing (IT):** In this phase, the integrated software components are tested to ensure that they work together as expected.
    
5.  **System Testing (ST):** In this phase, the complete software system is tested to ensure that it meets the specified requirements and is ready for release.
    
6. **User Acceptance Testing (UAT):** In this phase, the software is tested by the end-users or the customer to ensure that it meets their needs and expectations.
	Types of UAT :
	- Alpha Testing : performed by dev team, on project site.
	- Beta Testing : performed by actual user, in real time.
