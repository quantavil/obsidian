## Procedural Programming
- Focus is on processes or actions that a program takes
- Programs are typically a collection of functions
- Data is declared separately
- Data is passed as arguments into functions
- Fairly easy to learn

### Limitations 
- Functions need to know the structure of the data.
- if the structure of the data changes many functions must be changed
- As programs get larger they become more:
	- difficult to understand
	- difficult to maintain
	- difficult to extend
	- difficult to debug
	-  difficult to reuse code
	- fragile and easier to break

## What Is OOP ?
- Classes and Objects
- focus is on classes that model real-world domain entities
- allows developers to think at a higher level of abstraction
- used successfully in very large programs
- **Encapsulation :**
	- objects contain data AND operations that work on that data
	- Abstract Data Type (ADT)
  
-  **Information-hiding :**
	- implementation-specific logic can be hidden
	- users of the class code to the interface since they don't need to know the implementation
	- more abstraction
	- easier to test, debug, maintain and extend

- **Reusability :**
	- easier to reuse classes in other applications
	- faster development
	- higher quality

- **inheritance :**
	- can create new classes in term of existing classes
	- reusability
	- polymorphic classes

### Limitations 
- Not a panacea (a universal remedy):
	- OO Programming won't make bad code better
	- not suitable for all types of problems
	- not everything decomposes to a class
- Learning curve:
	- usually a steeper leaning curve, especially for C++
	- many OO languages, many variations of OO concepts
- Design:
	- usually more up-front design is necessary to create good models and hierarchies
- Programs can be:
	- larger in size
	- slower
	- more complex

   
## Classes and Objects
- Classes
	- blueprint from which objects are created
	- a user-defined data-type
	- has attributes (data)
	- has methods (functions)
	- can hide data and methods
	- provides a public interface
- Example classes : Account, Employee, Image, std::vector, std::string

- Objects
	- created from a class
	- represents a specific instance of a class
	- can create many, many objects
	- each has its own identity
	- each can use the defined class methods
- Example Account objects
	- Frank's account is an instance of an Account
	- Jim's account is an instance of an Account
	- Each has its own balance, can make deposits, withdrawals, etc.


>`std::vector<int> scores;                   here vector is class and score is object
>std::string name;`                       here string is class and name is object  

Note : **An instance is a specific representation of an object**
## What is a Class in C++?

A class in C++ is a user-defined type or data structure declared with a keyword class that has data and functions as its members. A class can be used by declaring an instance of that class which is nothing but an object in C++.

## What is an Object in C++?
A class is merely a blueprint of data. An object is a data structure that is an instance of a class. So when a class is created no memory is allocated but when an instance is created by declaring an object, memory is then allocated to store data and perform required functions on them.

![[object-in-cpp.webp]]

## Defining Class in C++

A Class is defined by a keyword class followed by a class_name (user's choice) and a block of curly brackets with semicolons after the block. The block starts with access specifiers followed by data members and member functions.

**Note:** Access specifier defines how the members of the class can be accessed. In C++, there are 3 types of access specifiers: public, private, and protected.

-   **public:** members can be accessed outside the class.
-   **private:** members cannot be accessed outside the class.
-   **protected:** members cannot be accessed(viewed) from outside the class, but can be accessed in inherited classes(subclasses).

**Syntax:**

```cpp
class ClassName
{
    Access specifier: 
    Data members;
    Member Functions()
    {
        // member function defintion
    }
};

```

**Example :**

```cpp
class Dog{                         // class ClassName
    public:                        //Access specifiers
        string breed, color;       //Data members

        void displayColor(){       //Member functions
            cout<<color<<" ";
        }

        void displayBreed(){
            cout<<breed<<" ";
        }
};                                // end with semicolon
```

## Declaring Objects in C++

When a class is defined only the blueprint of data structure is defined as no memory is allocated. To use data and its member function we can declare objects. We can declare objects by mentioning the class followed by the user-defined object name.

**Syntax:**

```cpp
Class ObjectName;
```

**Example:**

```cpp
Dog dog; 
```

## Significance of Class and Object in C++

The concept of class and object in C++ allows real-life analogies to be included in the programming. Using classes, data is given the highest importance. The following are some of the significant points to keep in mind:

-   **Data hiding**: Using access specifiers, a class stops data from being accessed from the outside world. Classes have the ability to set permissions to limit who has access to the data.
-   **Code Reusability**: With the aid of inheritance, you may reduce code redundancy by employing reusable code. Similar functionality and features can be inherited by other classes, making the code cleaner.
-   **Data binding**: The data elements and their associated operations are bonded together under one umbrella, increasing the data's security.
-   **Flexibility**: The principle of polymorphism allows you to use a class in a variety of ways. This increases the flexibility of a program.