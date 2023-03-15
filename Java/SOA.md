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