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

Some of the major types of non-functional requirements are:

1.  **Hardware constraints**: Minimum hardware, database, connectivity configurations under which the software should be able to function. This will give insights into the required configuration for the test environments.
    
2.  **Performance**: Acceptable response times of each component in different possible situations. These requirements should be tested in an environment (hardware configuration) as close as possible to the real-time environment and will require specialized technical knowledge on hardware configurations and performance testing software.
    
3.  **Usability**: UI characteristics, ease of use for a specific user group (E.g., accessibility characteristics for differently-abled users), etc. Testing these requirements requires testers with specialized skill-sets on design.
    
4.  **Security**: These requirements define the access levels to different categories of information present in the system; authentication methodologies, encryption standards for personal data, payment information, etc. Testing these requirements requires specialized skill set in terms of knowledge of security protocols and hacking methods.
    
5.  **Compliance**: Compliance to internal design standards(E.g., branding), government and legal standards(disclaimers, warnings, informational elements, information collected, etc.), accessibility standards for use by differently abled users. These requirements might be tested and certified by third party organizations or independent test groups.

### Characteristics of Good requirement

**Completeness**

An SRS document is considered to be complete if 

-   All the user's/customer's expectations documented in higher level requirements, like Business Requirement Specification (BRS) document, have been addressed in the SRS document and nothing has been missed out.
    
-   All significant aspects, both functional and non-functional, of each requirement specification has been addressed. 
    
-   It states the expected responses of the software (and its components) to all possible classes of input data, both valid and invalid, in all possible situations. 
    
-   Definition of all business-specific/software-specific abbreviations in its full form and their meanings.
    

**Example:** The requirement statement "_Allow the user to login to the system only if the user id and password combination is authenticated by the security module._" is an incomplete requirement because it does not tell what the system is supposed to do if either the user id or password is invalid.

**Unambiguity**

A requirement specification said to be unambiguous if each stated requirement has only one possible interpretation to all the project stakeholders- users, developers and testers.

**Example:** The requirement statement "_The User_ID field shall not accept input longer than 25 characters_" is ambiguous because it can be interpreted in any of the following possible ways

-   Throw an error message whenever the user enters more than 25 characters in the User_ID field.
    
-   Do not respond for any inputs from the keyboard after the user has typed 25 characters in the User_ID field.
    
-   Truncate the contents of the User_ID field to 25 characters once the user moves the cursor out of that field.
    

Whenever a word used in a specific context might have several meanings, it must be included in a glossary where its meaning is more precise.

**Example:** The terms like '_Acceptable Response Time_' must be made more specific in terms of measurable units like 3 seconds.

**Consistency**

A software requirement is said to inconsistent if it does not agree with or conflicts with

-   Any higher level requirements like the BRS document.
    
-   Another software requirement in the same SRS document.
    
-   Inputs and outputs of existing software and their interfaces with which the new software or it's components need to communicate.
    

**Example:** The following requirement statements are in conflict with each other.

"_Every page in the software application must have a 'Home' link at the bottom of the page and anytime the user clicks it, immaterial of the page or the state of activity in that page, the software should navigate to the home page_"

"_If an error message is displayed in page 4, the user should not be allowed to navigate to any page until all the errors for the corresponding page are fixed_"

**Testability**

A requirement specification is testable if and only if there exists some finite cost-effective process with which a tester can check that the software product meets that requirement.

A requirement cannot be tested by the tester if he/she does not have access to the required hardware configuration or software configuration due to cost and time factors.

Also as a general thumb rule,

-   All ambiguous requirements are not testable as there is no single outcome that can be called completely correct or completely wrong.
    
-   All inconsistent requirements are not testable as it is impossible to prove that the system is either working or not working as per the requirement.

