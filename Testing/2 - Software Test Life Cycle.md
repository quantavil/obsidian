The development team works based on the SDLC to build a software. Similarly, the testing team works based on the Software Test Life Cycle (STLC) to test a software. The STLC consists of four distinct stages which are sequential.

![[Pasted image 20230113121501.png]]

## Requirements Analysis

Requirements for the software to be built, are collected from the end users/clients by analysts and are documented in the form of Software Requirements Specifications (SRS).

A Software Requirements Specification is a documented definition of a condition or ability that needs to be possessed by a system or its component to attain an objective of the user.

### Significance

Requirement analysis is the first and the most significant stage in the SDLC as well as STLC because:

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