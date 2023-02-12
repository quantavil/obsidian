
The need for Software Testing: loss of money, time, reputation, and life

Software Quality: is the degree to which a process, component or system conforms to the specified requirements and user expectations


## Characteristics of Software Quality

- **Functionality**: how accurately does it perform the task stated in the requirements?
- **Reliability**: How capable to maintain the required level of performance over period of time
- **Usability**: How simple it is for the users to understand, learn and operate the software.
- **Efficiency**: economically does it consume available hw resources to maintain the required level of performance of its function
- **Maintainability**:  How simple it is to analyze the software/sw, make changes and test those changes whenever modification became necessary
- **Portability**: How simple it is to install, remove or replace sw and how easy it is for other sw to integrate with it.


## Software Testing

Software testing is an activity (or set of activities) performed to compare the expected outcome with the actual outcome of one specific task in the system, component or process and report the defects found in the system.


## Defect
A defect is a fault in the system, component or process due to which the expected outcome and the actual outcome of a test activity do not match.  

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

1.  **Walkthrough:** *Informal Process* the artifact is prepared by one team and reviewed by another team. The meeting led by the author. We don't have to submit any documents after the meeting. But if there are any chances of defect, we will communicate it in the meeting
2.  **Technical Review:** *Semi-formal* artifact is prepared by ne newbie(novice) of one team and it will be reviewed an expert of the same team. The expert will lead the meeting. It is your call, the errors can be documented/ communicated orally.     
3.  **Inspection:** *Formal Process* It's already prepared, we are waiting for the approval to proceed to the next stage. For that, the higher authorities have to sign off the artifacts. Moderator will lead the meeting. The creator and higher authorities will be participants of the meeting. We have to document the errors and track it periodically.
4.  **Static Analysis:** to analyze and predict the dynamic behavior (after execution of code) *Informal* - if the team is going to review it. *Formal* - if one among the team member other than the Author analyze it. The meeting is not mandatory. It might be documented if its formal, if not it can be avoided.
![[Pasted image 20230113102043.png]]

#### Dynamic Test
Testing will be done with execution of code.(application, GUI, Code).
Black Box and White box-
1. Black box:-
 We don't have visibility of code. You can see the application, so you are check the users perspective checking the presentation layer/GUI(Graphical user Interface- User interface) It is done is user’s perspective. in order to find if any bugs/ defect is present.
   
2. White box:-
 Visibility of codes and application. We will match the code and application. and if there are any defect present, we can locate it in the code. It is done in the Programmers perspective.


## Quality Assurance and Quality Control

The main difference between SQA and SQC is that SQA focuses on the process of software development and testing, while SQC focuses on the actual testing of the software.
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


**SDLC :-** Software Development Life cycle.
**STLC :-** Software Test Life Cycle.

**SRS -** Software  Requirement specification, It is the document which has the Requirements specified.

## How S/W testing is done:
1. Requirement Analysis
2. Test Planning and Design
3. Test Execution Phase
4. Test Closure phase

### Requirement Analysis Phase

1. **Software Requirement Specification (SRS) :** Document definition of a condition or ability that needs to be possessed by a system or its component to attain an objective of the user

2. **Functional and Non Functional Requirements:**
- Functional - state what the system should do
eg: gender field by default `<blank>`, drop-down - male or female
if the field is blank and click submit button - shall display an error message.

- Non Functional requirements: How the system should be
	Hardware Constraint: min hardware, database, connectivity configuration under which sw should be able to function
	Performance: Acceptable response times of each component in different possible situations
	Usability: ease of use for specific group user.
	Security: define the access level to different categories of information present in the system.
	Compliance: internal design standard, government and legal standards, accessibility standards.
	
3. **Characteristics of Good Requirements:**
- Completeness - nothing is missed out, fun and nonfunctional should be addressed, all expected responses should be addressed abbreviation full form 
- Unambiguity: each requirement has only one possible interpretation.
- Consistency: Any higher level requirement like the BRS or SRS should be consistent 
	Ex: BRS - Navigate to home page (every page link should be there)
	SRS - If an error msg is displayed in page 4, and user should not allowed to navigate.
- Testability - Ex: loading time should not drop below 5 sec as long as user exceed 1 million users