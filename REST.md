## Introduction to REST Assured

### REST architecture

-   REST stands for Representational State Transfer.
-   REST is a software architecture style that relies on a stateless communications protocol, most commonly, HTTP.
-   REST structures message data in XML, YAML or any other format that is machine-readable. JSON is now the most popular format being used in REST Services.
-   In REST architecture, a REST Server simply provides access to resources and the REST client accesses and presents the resources. Here each resource is identified by URIs/ Global IDs. 

### URI – Uniform Resource Identifier

-   A Uniform Resource Identifier (URI) is a string of characters used to identify a resource. Such identification enables interaction with representations of the resource over a network.
-   Each resource is identified by one or more Uniform Resource Identifiers (URIs). To access the resource, an application calls an HTTP operation(Method) on one of the resource's URIs.

### RESTFul services

-   Web services based on REST Architecture are known as RESTful Web Services.
-   These web services use HTTP methods to implement the concept of REST architecture. A RESTful web service usually defines a URI (Uniform Resource Identifier), which is a service that provides resource representation in JSON format using HTTP Methods

## REST Assured
    
-   Rest Assured is a Java library that offers a domain-specific language(DSL) to create and maintain tests for RESTful APIs. Integration of Rest Assured with TestNG and JUnit can also be done.
-   To simplify the testing and validation of REST APIs, Rest Assured was developed.
-   One of the most significant features of Rest Assured is that to check the contents present in the response, we can make use of the XML path and JSON path. We can parse the response data and test specific elements of their properties using XML and JSON path.
    
-   REST Assured can also be used to validate and verify the responses of all the requests that are supported by REST Assured, viz., GET, PUT, DELETE, PATCH, and HEAD requests. 
-   The methods/skill required for validation of responses received from the server is given by Rest-Assured Library. For e.g. we can verify the Status code, Status message, Headers and even the body of the response. This makes Rest-Assured a very flexible library that can be used for testing.