SOA (Service-Oriented Architecture) is an architectural pattern that involves building software applications by breaking down the functionality into smaller, interconnected services that can be reused across different systems. These services are grouped into different layers, each of which serves a specific purpose. Here is an explanation of the six layers in the SOA architecture:

1.  Data and Application Layer: This layer is responsible for storing, managing, and accessing data and applications used by the services in the other layers. It includes databases, file systems, and application servers.
    
2.  Enterprise Component Layer: This layer provides reusable components that can be used across different services. It includes libraries, frameworks, and middleware that provide functionality such as security, transaction management, and messaging.
    
3.  Service Layer: This layer contains the services themselves. Each service is a self-contained unit of functionality that can be accessed and used by other services or applications.
    
4.  Business Process Layer: This layer is responsible for defining and managing the business processes that use the services. It includes workflow engines, business rules engines, and other tools for managing and automating business processes.
    
5.  Presentation Layer: This layer is responsible for presenting the data and functionality provided by the services to the end-users. It includes user interfaces, web applications, and other tools for presenting data and interacting with the services.
    
6.  Integration Layer: This layer is responsible for integrating the different services and systems that make up the SOA architecture. It includes tools for messaging, routing, and transformation of data between the different services and systems.


SOA stands for Service-Oriented Architecture, which is an architectural approach in which applications make use of services available in the network². SOA defines a way to make software components reusable using interfaces². SOA consists of different layers that interact with each other to provide functionalities and services. Here is a brief explanation of each layer:

- Data & Application layer: This is the lowest layer that contains the data model and the operational systems that store and manipulate data¹⁵.
- Enterprise component layer: This is the layer that contains the service components, which are used to build the services. Service components are functional and technical libraries that encapsulate business logic and data access¹⁵.
- Service layer: This is the layer that contains the services, which are whole-enterprise units of functionality that can be reused by different applications. Services are published and discovered through a common mechanism and communicate using standard protocols¹²⁵.
- Business process layer: This is the layer that contains the business processes, which are sequences of activities that implement business use cases. Business processes can orchestrate multiple services to achieve a specific goal¹²⁵.
- Presentation layer: This is the highest layer that contains the consumer interfaces, which are GUI-based applications for end users accessing the services. Consumer interfaces can also invoke other consumer interfaces to provide a seamless user experience¹²⁵.
- Integration layer: This is an optional layer that provides integration capabilities between different systems or platforms. Integration can be achieved through adapters, connectors, brokers or middleware technologies[^4].

I hope this helps you understand SOA layers better.

Source: Conversation with Bing, 3/17/2023(1) Service-Oriented Architecture - GeeksforGeeks. https://www.geeksforgeeks.org/service-oriented-architecture/ Accessed 3/17/2023.
(2) Service-Oriented Architecture (SOA) - W3schools. https://www.w3schools.in/service-oriented-architecture Accessed 3/17/2023.
(3) SOA Reference Architecture – Description of Layers - The Open Group. https://www.opengroup.org/soa/source-book/soa_refarch/p7.htm Accessed 3/17/2023.
(4) Service-Oriented Architecture - DZone. https://dzone.com/articles/service-oriented-architecture-1 Accessed 3/17/2023.
(5) SOA Architecture | Top 9 Components of SOA architecture - EDUCBA. https://www.educba.com/soa-architecture/ Accessed 3/17/2023.
Monolithic Architecture is **like a big container, wherein all the software components of an app are assembled and tightly coupled, i.e., each component fully depends on each other.**
•    as a single executable unit (like a single java WAR file)  
•    using a single development technology/platform (i.e., JEE or .NET).

![[Pasted image 20230315150622.png]]

Which of the following reasons are the primary drivers that make organizations adopt Service Oriented Architecture principles in order to build/enhance their IT applications?


Making their IT infrastructure more flexible for applications to use a variety of technologies and platforms to achieve the best solutions check

Meet the challenge of having essential business changes to the application go live as soon as possible check


Your client has two web applications developed in different platforms (Angular JS and Node.js respectively). Using web services based approach, is it possible to make them successfully communicate with each other?

Only possible if both the respective web services are hosted on servers using similar operating system and are connected to each other through LAN, WAN or the internet

Not possible at all

Possible even if the web services are hosted on servers running on different operating systems as long as they are connected to each other through LAN, WAN or the internet check

It's only possible if both the respective web services are hosted on the internet (Not LAN or WAN). The operating systems or their servers don't really matter

Explanation :

Two service can communicate with each other on different operating systems

Q2 of 2outlined_flag

The Interest Calculator communicates with webpage using requests and response composed in XML. Why does web service developer uses XML for communication?

It is possible for any computer program to read and extract data XML check

As long as both the service provider and service consumer can communicate with each other using XML, the technology/language used to implement them doesn't matter check

It might be the personal preference of the web service developer

It's a communication standard followed by web services in general. The developer has not much of a choice check

Explanation :

A valid reason to use XML. XML has the potential to transfer self-descriptive data, and has a large following

Explanation :


---

Q1 of 4outlined_flag

In the below options identify the one which is NOT an information that is provided in a web service's WSDL file?

Interface description

End point

HTTP commands or response codes check

Binding protocol

Explanation :

It is not a part of WSDL Description.

Q2 of 4outlined_flag

In the following statements identify the one which is NOT true about UDDI registries?

UDDI registries are out of use in today's IT ethos

UDDI registries were written in plain english check

Microsoft, SAP and IBM maintained the most used public UDDI registries once

UDDI registries can contain contact details of the web service publisher

Explanation :

UDDI uses WSDL to describe the interfaces of the web services

Q3 of 4outlined_flag

The weather app in your mobile phone can send a current temperature request message to weather.com's web service using:

Any transport protocol like HTTP, FTP or STMP

Only HTTP

Only the transport protocol defined in the WSDL's binding data. check

internet

Explanation :

WSDL binding data gives out the transport protocol which should be used for message transfers

Q4 of 4outlined_flag

Identify the operation/interface being invoked in the below SOAP request message.

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <InsertUser xmlns="http://tempuri.org/">
      <username>string</username>
      <password>string</password>
    </InsertUser>
  </soap:Body>
</soap:Envelope>
 

username

password

Insert User check

SOAP: Envelope

Explanation :

Insert User is the interface present in the WSDL. It mentioned the operation which is perform using the SOAP message

---
Which of the following statements describes a business process in the context of SOA layers? 

It is a business policy

It is a series of tasks connected together check

Items are collected and then processed together

Enables interactions between consumers and providers

Explanation :

Business Process Layer plays a central coordinating role in connecting business-level requirements and IT-level solution components

Q2 of 2outlined_flag

In which of the following techniques is the logic of the business process pushed out to the members participating in the SOA architecture? 

Choreography check

Orchestration

Explanation :

The choreography describes the interactions between multiple services and the interaction is given to each and each service.