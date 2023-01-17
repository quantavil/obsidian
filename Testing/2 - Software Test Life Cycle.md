The development team works based on the SDLC to build a software. Similarly, the testing team works based on the Software Test Life Cycle (STLC) to test a software. The STLC consists of four distinct stages which are sequential.

![[Pasted image 20230113121501.png]]

## Requirements Analysis

Requirements for the software to be built, are collected from the end users/clients by analysts and are documented in the form of **Software Requirements Specifications (SRS)**.

### Significance
-   Requirements are the basis to develop and validate a software. 
-   It provides the basis for planning the project, estimating the cost and predicting risks, if any. 
-   An incorrect or missing requirement will result in a bad or unusable software, no matter how perfectly all the other stages of the SDLC and STLC are executed.


### 1. Functional Requirements

A functional requirement defines the function(s) of a software system or its component. A function is defined in terms of the required output data/behavior of a software (or its component) for a specific combination of input data and/or actions.

In general, functional requirements state WHAT the system should do.
Functional requirements are generally the first to be validated.


### 2. Non-Functional Requirements

Non-functional requirements define the constraints under which functional requirements shall operate. They are also called as 'quality attributes' of the system.

In general, non-functional requirements state HOW the system should be.

Some of the major types of non-functional requirements are

1.  **Hardware constraints** Minimum hardware, database, connectivity configurations under which the software should be able to function.  
2.  **Performance** Acceptable response times of each component in different possible situations. 
3.  **Usability** UI characteristics, ease of use for a specific user group.
4.  **Security** These requirements define the access levels to different categories of information present in the system; authentication methodologies, encryption standards 
5.  **Compliance** Compliance to internal design standards(E.g., branding), government and legal standards(disclaimers, warnings, informational elements, information collected, etc.), 

### Characteristics of Good requirement

1. **Completeness**

An SRS document is considered to be complete if 

-   All the user's/customer's expectations documented in higher level requirements, like Business Requirement Specification (BRS) document, have been addressed in the SRS document and nothing has been missed out.
    
-   All significant aspects, both functional and non-functional, of each requirement specification has been addressed. 

```ad-example
The requirement statement "_Allow the user to login to the system only if the user id and password combination is authenticated by the security module._" is an incomplete requirement because it does not tell what the system is supposed to do if either the user id or password is invalid.
```


2. **Unambiguity**

A requirement specification said to be unambiguous if each stated requirement has only one possible interpretation to all the project stakeholders- users, developers and testers.

```ad-example
The requirement statement "_The User_ID field shall not accept input longer than 25 characters_" is ambiguous because it can be interpreted in any of the following possible ways

-   Throw an error message whenever the user enters more than 25 characters in the User_ID field.
    
-   Do not respond for any inputs from the keyboard after the user has typed 25 characters in the User_ID field.

```


3. **Consistency**

A software requirement is said to inconsistent if it does not agree with or conflicts with

-   Any higher level requirements like the BRS document.
-   Another software requirement in the same SRS document.
-   Inputs and outputs of existing software and their interfaces with which the new software or it's components need to communicate.
    
```ad-example
The following requirement statements are in conflict with each other.

"Every page in the software application must have a 'Home' link at the bottom of the page and anytime the user clicks it, immaterial of the page or the state of activity in that page, the software should navigate to the home page"

"If an error message is displayed in page 4, the user should not be allowed to navigate to any page until all the errors for the corresponding page are fixed"
```

4. **Testability**

A requirement specification is testable if and only if there exists some finite cost-effective process with which a tester can check that the software product meets that requirement.


## Testing Planning and design

Once the requirements are finalized, the testing team enters the test planning and design phase where it needs to plan System Testing(ST) activities in such a way so that the quality objectives of the software are accomplished by

-   Ensuring optimum test coverage
    
-   Using available resources
    
-   Staying within the specified timelines
    
-   Keeping the predictable risks under control

### Contents of a Test Plan Document

As per IEEE 829-2008, also known as the 829 Standard for Software Test Documentation, a Test Plan Document needs to possess the following information.

**Test Plan Identifier** 
**Introduction :** A high-level outline of the AUT and necessity for the present testing activity. 
**Test Items :** The software and/or its specific components which have to be tested.
**Features to be tested**
**Features not to be tested** 
**Approach** 
**Item Pass/Fail Criteria**
**Suspension criteria and resumption criteria** 
**Test deliverables** 
**Test tasks** 
**Environmental needs** 
**Staffing and training needs** 
**Responsibilities** 
**Schedule** 
**Planning risks and contingencies**
**Approvals** 

### Designing Test Cases

Test designing is the act of creating and documenting the set of test cases (test suite) to be used for testing the software.

A well designed test suite, upon execution, would be able to objectively state the quality of the software in terms of 

-   Test coverage
-   Number of defects found

#### Test coverage

-   Test coverage is a measure of the size or amount of software that has been validated using the test suite.
    
-   Based on the measuring unit used, test coverage can be stated in two ways.

**Code coverage**

-   Test coverage is expressed in terms of number of program statements tested. ~ done by  white box testser

**Specification coverage**

-   Test coverage is expressed in terms of number of requirements in the SRS that have been tested. ~ done by black box tester

#### Coverage Effectiveness

-   A test suite design is said to **effective** if 100% test coverage is achieved by its test cases.
-   Exhaustive testing may / may not be possible

#### Coverage Efficiency

-   If you take exit criteria (when the testing should stop) from the test plan document into account, then you will understand that you have to achieve 100% test coverage with as less number test cases as possible.

**Test case optimization** is the process limiting the number of test cases, on the basis of sound principles and scientific assumptions, required to achieve maximum test coverage.

The techniques that testers use to optimize their test cases can be classified into three groups, as shown below:

-   Structure based techniques
    
-   Specification based techniques
    
-   Experience techniques

##### When and by whom are structure based tests done?

Developers, who have coding skills and code visibility, perform structure based tests during the Component Testing level to make sure that 100% of the application is covered in terms of source code structure.


1.  Statement coverage
2.  Decision coverage
3.  Path coverage
4.  Condition coverage



