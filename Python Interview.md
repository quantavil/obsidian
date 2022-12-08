            
## SDLC

Software Development Life Cycle (SDLC) is a process used by the software industry to design, develop and test high quality softwares.


## Stages :

Stage 1: Planning and Requirement Analysis

Stage 2: Defining Requirements

Stage 3: Designing the Product Architecture

Stage 4: Building or Developing the Product

Stage 5: Testing the Product

Stage 6: Deployment in the Market and Maintenance

## What are the main concepts of Object-Oriented Programming ?

An object-oriented paradigm is to design the program using classes and objects. That mimics the real world entities.

Main concepts of OOP are:

-   **Class**: A class is a user defined blueprint or prototype from which objects are created. Unlike the primitive data structures, classes are data structures that the user defines. They make the code more manageable.

· **Object**: An Object is an identifiable entity with some characteristics and behavior. An Object is an instance of a Class. When a class is defined, no memory is allocated but when it is instantiated (i.e. an object is created) memory is allocated.

-   **Polymorphism**: Polymorphism is the ability to exit in many forms. We can construct various classes to have methods with the same name while creating class methods.

Example: We can take a boy as a real-world example. This boy can be a student, a player, and a writer. So that this boy can exist in different ways in different situations.

-   **Inheritance:** It specifies that the child object acquires all the properties and behaviors of the parent object. By using inheritance, we can create a class which uses all the properties and behavior of another class. (The new class is known as a derived class or child class, and the one whose properties are acquired is known as a base class or parent class. It provides the re-usability of the code.)

let's assume that there is a class as Vehicle. All vehicles are not the same. We can inherit common properties like color, size, type from the parent vehicle class and create classes like Car, Bus, Bike.

-   **Encapsulation:** Encapsulation is based on the concept of having the data and code into a single unit to hide the internal workings of the code to an end-user and from being modified by accident.

For example: medical capsule. This capsule mixes few types of medicines and stored in one capsule.

-   **Abstraction**: In abstraction, it displays only the important information by hiding the implementation part.

Example: mobile phones. On a mobile phone, we can perform so many actions like making a call, sending messages, take pictures, download software and etc. We perform a lot of things but here also we don't know the inside process of these things. Which means the implementation parts are hidden.

**3.** **Access Modifiers****?** 

In most of the object-oriented languages access modifiers are used to limit the access to the variables and functions of a class. There are three types of access modifiers, they are - **private**, **public** and **protected**.

Access modifiers play an important role to protect the data from unauthorized access as well as protecting it from getting manipulated.

Access Modifier: Public


The members declared as Public are accessible from outside the Class through an object of the class. 

_# defining a class Employee_

class Employee:

 _# constructor_

 def __init__(self, name, sal):

 self.name = name;

 self.sal = sal;

Access Modifier: Protected

The members declared as Protected are accessible from outside the class but only in a class derived from it that is in the child or subclass. _ _uses single underscore_

_# defining a class Employee_

class Employee:

 _# constructor_

 def __init__(self, name, sal):

 self._name = name; _# protected attribute_

 self._sal = sal; _# protected attribute_

Access Modifier: Private

These members are only accessible from within the class. No outside Access is allowed. ___uses double underscore_

_# defining class Employee_

class Employee:

 def __init__(self, name, sal):

 self.__name = name; _# private attribute_

 self.__sal = sal; _# private attribute_

## Why do we need oops

1) OOP provides a clear modular structure for programs

2) OOP makes it easy to maintain and modify existing code

3) Code Reusability : We can build the programs from standard working modules that communicate with one another, rather than having to start writing the code from scratch which leads to saving of development time and higher productivity,

5) OOP language allows to break the program into the bit-sized problems that can be solved easily (one object at a time).

## List Vs Tuple

-   The key difference between the tuples and lists is that while the tuples are immutable objects the lists are mutable. This means that tuples cannot be changed while the lists can be modified.

-   As lists are mutable, Python needs to allocate an extra memory block in case there is a need to extend the size of the list object after it is created. In contrary, as tuples are immutable and fixed size, Python allocates just the minimum memory block required for the data.

-   As a result, tuples are more memory efficient than the lists.

## What is Decorator

Basically, a decorator takes in a function, adds some functionality and returns it. functions are passed as an argument into another function and then called inside the wrapper function.

## Deep copy vs Shallow copy

import copy

-   Deep copy means that any changes made to a copy of object do not reflect in the original object. copy.deepcopy()
-   Shallow copy means that any changes made to a copy of object also reflect in the original object. copy.copy()

The pointer points to same copy of object class.