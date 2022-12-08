![C++ Interview Questions](https://static.javatpoint.com/interview/images/cpp-interview-questions.png)

### 1) What is C++?

C++ is an object-oriented programming language created by Bjarne Stroustrup. It was released in 1985.
C++ is a superset of C with the major addition of classes in C language.
Initially, Stroustrup called the new language "C with classes". However, after sometime the name was changed to C++. The idea of C++ comes from the C increment operator ++.

___

### 2) What are the **advantages** of C++?

C++ doesn't only maintains all aspects from C language, it also simplifies memory management and adds several features like:

-   C++ is a highly portable language means that the software developed using C++ language can run on any platform.
-   C++ is an object-oriented programming language which includes the concepts such as classes, objects, inheritance, polymorphism, abstraction.
-   C++ has the concept of inheritance. Through inheritance, one can eliminate the redundant code and can reuse the existing classes.
-   Data hiding helps the programmer to build secure programs so that the program cannot be attacked by the invaders.
-   Message passing is a technique used for communication between the objects.
-   C++ contains a rich function library.

___

### 3) What is the **difference between C and C++**?

Following are the differences between C and C++:

| C | C++ |
| --- | --- |
| C language was developed by Dennis Ritchie. | C++ language was developed by Bjarne Stroustrup. |
| C is a structured programming language. | C++ supports both structural and object-oriented programming language. |
| C is a subset of C++. | C++ is a superset of C. |
| In C language, data and functions are the free entities. | In the C++ language, both data and functions are encapsulated together in the form of a project. |
| C does not support the data hiding. Therefore, the data can be used by the outside world. | C++ supports data hiding. Therefore, the data cannot be accessed by the outside world. |
| C supports neither function nor operator overloading. | C++ supports both function and operator overloading. |
| In C, the function cannot be implemented inside the structures. | In the C++, the function can be implemented inside the structures. |
| Reference variables are not supported in C language. | C++ supports the reference variables. |
| C language does not support the virtual and friend functions. | C++ supports both virtual and friend functions. |
| In C, scanf() and printf() are mainly used for input/output. | C++ mainly uses stream cin and cout to perform input and output operations. |

### 4) What is the **difference between reference and pointer**?

Following are the differences between reference and pointer:

| Reference | Pointer |
| --- | --- |
| Reference behaves like an alias for an existing variable, i.e., it is a temporary variable. | The pointer is a variable which stores the address of a variable. |
| Reference variable does not require any indirection operator to access the value. A reference variable can be used directly to access the value. | Pointer variable requires an indirection operator to access the value of a variable. |
| Once the reference variable is assigned, then it cannot be reassigned with different address values. | The pointer variable is an independent variable means that it can be reassigned to point to different objects. |
| A null value cannot be assigned to the reference variable. | A null value can be assigned to the reference variable. |
| It is necessary to initialize the variable at the time of declaration. | It is not necessary to initialize the variable at the time of declaration. |

___

### 5) What is a **class**?

The class is a user-defined data type. The class is declared with the keyword class. The class contains the data members, and member functions whose access is defined by the three modifiers are private, public and protected. The class defines the type definition of the category of things. It defines a datatype, but it does not define the data it just specifies the structure of data.

You can create N number of objects from a class.

___

### 6) What are the various **OOPs** concepts in C++?

The various OOPS concepts in C++ are:

![C++ Interview Questions](https://static.javatpoint.com/interview/images/cpp-interview-questions2.png)

-   **Class:**

The class is a user-defined data type which defines its properties and its functions. For example, Human being is a class. The body parts of a human being are its properties, and the actions performed by the body parts are known as functions. The class does not occupy any memory space. Therefore, we can say that the class is the only logical representation of the data.

-   **Object:**

An object is a run-time entity. An object is the instance of the class. An object can represent a person, place or any other item. An object can operate on both data members and member functions. The class does not occupy any memory space. When an object is created using a new keyword, then space is allocated for the variable in a heap, and the starting address is stored in the stack memory. When an object is created without a new keyword, then space is not allocated in the heap memory, and the object contains the null value in the stack.

-   **Inheritance:**

Inheritance provides reusability. Reusability means that one can use the functionalities of the existing class. It eliminates the redundancy of code. Inheritance is a technique of deriving a new class from the old class. The old class  is known as the base class, and the new class is known as derived class.

#### Note: The visibility-mode can be public, private, protected.

-   **Encapsulation:**

Encapsulation is a technique of wrapping the data members and member functions in a single unit. It binds the data within a class, and no outside method can access the data. If the data member is private, then the member function can only access the data.

-   **Abstraction:**

Abstraction is a technique of hiding the internal details for the simplicity and showing only the functionality to the user.

-   **Data binding:**

Data binding is a process of binding the application UI and business logic. Any change made in the business logic will reflect directly to the application UI.

-   **Polymorphism:**

Polymorphism means multiple forms. Polymorphism means having more than one function with the same name but with different functionalities. Polymorphism is of two types:

1.  Static polymorphism is also known as early binding.
2.  Dynamic polymorphism is also known as late binding.

___

### 7) What are the different types of **polymorphism** in C++?

Polymorphism: Polymorphism means multiple forms. It means having more than one function with the same function name but with different functionalities.

**Polymorphism is of two types:**

![C++ Interview Questions](https://static.javatpoint.com/interview/images/cpp-interview-questions3.png)

-   **Runtime polymorphism**

Runtime polymorphism is also known as dynamic polymorphism. Function overriding is an example of runtime polymorphism. Function overriding means when the child class contains the method which is already present in the parent class. Hence, the child class overrides the method of the parent class. In case of function overriding, parent and child class both contains the same function with the different definition. The call to the function is determined at runtime is known as runtime polymorphism.

-   **Compile time polymorphism**

Compile-time polymorphism is also known as static polymorphism. The polymorphism which is implemented at the compile time is known as compile-time polymorphism. Method overloading is an example of compile-time polymorphism.

**Method overloading:** Method overloading is a technique which allows you to have more than one function with the same function name but with different functionality.

Method overloading can be possible on the following basis:

-   The return type of the overloaded function.
-   The type of the parameters passed to the function.
-   The number of parameters passed to the function.

-   In the above example, mul() is an overloaded function with the different number of parameters.

___

### 8) Define **namespace** in C++.

-   The namespace is a logical division of the code which is designed to stop the naming conflict.
-   The namespace defines the scope where the identifiers such as variables, class, functions are declared.
-   The main purpose of using namespace in C++ is to remove the ambiguity. Ambiquity occurs when the different task occurs with the same name.
-   For example: if there are two functions exist with the same name such as add(). In order to prevent this ambiguity, the namespace is used. Functions are declared in different namespaces.
-   C++ consists of a standard namespace, i.e., std which contains inbuilt classes and functions. So, by using the statement "using namespace std;" includes the namespace "std" in our program.
-   **Syntax of namespace:**

___

### 9) Define **token** in C++.

A token in C++ can be a keyword, identifier, literal, constant and symbol.

___

### 10) Who was the **creator** of C++?

Bjarne Stroustrup.

___

### 11) Which operations are permitted on pointers?

Following are the operations that can be performed on pointers:

-   **Incrementing or decrementing a pointer**: Incrementing a pointer means that we can increment the pointer by the size of a data type to which it points.

**There are two types of increment pointers:**

**1\. Pre-increment pointer**: The pre-increment operator increments the operand by 1, and the value of the expression becomes the resulting value of the incremented. Suppose ptr is a pointer then pre-increment pointer is represented as ++ptr.




**2\. Post-increment pointer**: The post-increment operator increments the operand by 1, but the value of the expression will be the value of the operand prior to the incremented value of the operand. Suppose ptr is a pointer then post-increment pointer is represented as ptr++.



### 12) Define **'std'.**

Std is the default namespace standard used in C++.

___

### 15) What is the full form of STL in C++?

STL stands for Standard Template Library.

___

### 16) What is an **object**?

The Object is the instance of a class. A class provides a blueprint for objects. So you can create an object from a class. The objects of a class are declared with the same sort of declaration that we declare variables of basic types.

___

### 17) What are the C++ **access specifiers / modifiers**?

The access specifiers are used to define how to functions and variables can be accessed outside the class.

There are three types of access specifiers:

-   **Private**: Functions and variables declared as private can be accessed only within the same class, and they cannot be accessed outside the class they are declared.
-   **Public**: Functions and variables declared under public can be accessed from anywhere.
-   **Protected**: Functions and variables declared as protected cannot be accessed outside the class except a child class. This specifier is generally used in inheritance.

___

### 18) What is **Object Oriented Programming** (OOP)?

OOP is a methodology or paradigm that provides many concepts. The basic concepts of Object Oriented Programming are given below:

**Classes and Objects**: Classes are used to specify the structure of the data. They define the data type. You can create any number of objects from a class. Objects are the instances of classes.

**Encapsulation**: Encapsulation is a mechanism which binds the data and associated operations together and thus hides the data from the outside world. Encapsulation is also known as data hiding. In C++, It is achieved using the access specifiers, i.e., public, private and protected.

**Abstraction**: Abstraction is used to hide the internal implementations and show only the necessary details to the outer world. Data abstraction is implemented using interfaces and abstract classes in C++.

Some people confused about Encapsulation and abstraction, but they both are different.

**Inheritance**: Inheritance is used to inherit the property of one class into another class. It facilitates you to define one class in term of another class.

___

### 19) What is the difference between an **array and a list**?

-   An Array is a collection of homogeneous elements while a list is a collection of heterogeneous elements.
-   Array memory allocation is static and continuous while List memory allocation is dynamic and random.
-   In Array, users don't need to keep in track of next memory allocation while In the list, the user has to keep in track of next location where memory is allocated.

___

### 20) What is the difference between **new() and malloc()**?

-   new() is a preprocessor while malloc() is a function.
-   There is no need to allocate the memory while using "new" but in malloc() you have to use sizeof().
-   "new" initializes the new memory to 0 while malloc() gives random value in the newly allotted memory location.
-   The new() operator allocates the memory and calls the constructor for the object initialization and malloc() function allocates the memory but does not call the constructor for the object initialization.
-   The new() operator is faster than the malloc() function as operator is faster than the function.

___

### 21) What are the methods of exporting a function from a DLL?

There are two ways:

-   By using the DLL's type library.
-   Taking a reference to the function from the DLL instance.

___

### 22) Define **friend function**.

Friend function acts as a friend of the class. It can access the private and protected members of the class. The friend function is not a member of the class, but it must be listed in the class definition. The non-member function cannot access the private data of the class. Sometimes, it is necessary for the non-member function to access the data. The friend function is a non-member function and has the ability to access the private data of the class.


**Following are the characteristics of a friend function:**

-   The friend function is not in the scope of the class in which it has been declared.
-   Since it is not in the scope of the class, so it cannot be called by using the object of the class. Therefore, friend function can be invoked like a normal function.
-   A friend function cannot access the private members directly, it has to use an object name and dot operator with each member name.
-   Friend function uses objects as arguments.


___

### 23) What is a **virtual function**?

-   A virtual function is used to replace the implementation provided by the base class. The replacement is always called whenever the object in question is actually of the derived class, even if the object is accessed by a base pointer rather than a derived pointer.
-   A virtual function is a member function which is present in the base class and redefined by the derived class.
-   When we use the same function name in both base and derived class, the function in base class is declared with a keyword virtual.
-   When the function is made virtual, then C++ determines at run-time which function is to be called based on the type of the object pointed by the base class pointer. Thus, by making the base class pointer to point different objects, we can execute different versions of the virtual functions.

**Rules of a virtual function:**

-   The virtual functions should be a member of some class.
-   The virtual function cannot be a static member.
-   Virtual functions are called by using the object pointer.
-   It can be a friend of another class.
-   C++ does not contain virtual constructors but can have a virtual destructor.

___

### 24) When should we use **multiple inheritance**?

You can answer this question in three manners:

1.  Never
2.  Rarely
3.  If you find that the problem domain cannot be accurately modeled any other way.

___

### 25) What is a **destructor**?

A Destructor is used to delete any extra resources allocated by the object. A destructor function is called automatically once the object goes out of the scope.

**Rules of destructor:**

-   Destructors have the same name as class name and it is preceded by tilde.
-   It does not contain any argument and no return type.

___

### 26) What is an **overflow erro**r?

It is a type of arithmetical error. It happens when the result of an arithmetical operation been greater than the actual space provided by the system.

___

### 27) What is **overloading**?

-   When a single object behaves in many ways is known as overloading. A single object has the same name, but it provides different versions of the same function.
-   C++ facilitates you to specify more than one definition for a function name or an operator in the same scope. It is called function overloading and operator overloading respectively.
-   **Overloading is of two types:**

![C++ Interview Questions](https://static.javatpoint.com/interview/images/cpp-interview-questions4.png)

**1\. Operator overloading:** Operator overloading is a compile-time polymorphism in which a standard operator is overloaded to provide a user-defined definition to it. For example, '+' operator is overloaded to perform the addition operation on data types such as int, float, etc.

**Operator overloading can be implemented in the following functions:**

-   Member function
-   Non-member function
-   Friend function


**2\. Function overloading:** Function overloading is also a type of compile-time polymorphism which can define a family of functions with the same name. The function would perform different operations based on the argument list in the function call. The function to be invoked depends on the number of arguments and the type of the arguments in the argument list.

___

### 28) What is **function overriding**?

If you inherit a class into a derived class and provide a definition for one of the base class's function again inside the derived class, then this function is called overridden function, and this mechanism is known as function overriding.

___

### 29) What is **virtual inheritance**?

Virtual inheritance facilitates you to create only one copy of each object even if the object appears more than one in the hierarchy.

___

### 30) What is a **constructor**?

A Constructor is a special method that initializes an object. Its name must be same as class name.

___

### 31) What is the purpose of the **"delete"** operator?

The "delete" operator is used to release the dynamic memory created by "new" operator.

___

### 32) Explain this **pointer**?

This pointer holds the address of the current object.

___

### 33) What does Scope **Resolution operator** do?

A scope resolution operator(::) is used to define the member function outside the class.

___

### 34) What is the difference between **delete and delete\[\]**?

Delete \[\] is used to release the array of allocated memory which was allocated using new\[\] whereas delete is used to release one chunk of memory which was allocated using new.

___

### 35) What is a **pure virtual function**?

The pure virtual function is a virtual function which does not contain any definition. The normal function is preceded with a keyword virtual. The pure virtual function ends with 0.


___

### 36) What is the difference between **struct and class**?

| Structures | class |
| --- | --- |
| A structure is a user-defined data type which contains variables of dissimilar data types. | The class is a user-defined data type which contains member variables and member functions. |
| The variables of a structure are stored in the stack memory. | The variables of a class are stored in the heap memory. |
| We cannot initialize the variables directly. | We can initialize the member variables directly. |
| If access specifier is not specified, then by default the access specifier of the variable is "public". | If access specifier is not specified, then by default the access specifier of a variable is "private". |
| The instance of a structure is a "structure variable". |  |
| **Declaration of a structure:**
```
struct structure_name
{
   // body of structure;
} ;

```

 | **Declaration of class:**

```
class class_name
{
   // body of class;
} 

```

 |
| A structure is declared by using a struct keyword. | The class is declared by using a class keyword. |
| The structure does not support the inheritance. | The class supports the concept of inheritance. |
| The type of a structure is a value type. | The type of a class is a reference type. |

___

### 37) What is a **class template**?

A class template is used to create a family of classes and functions. For example, we can create a template of an array class which will enable us to create an array of various types such as int, float, char, etc. Similarly, we can create a template for a function, suppose we have a function add(), then we can create multiple versions of add().


___

### 38) What is the difference between **function overloading and operator overloading**?

**Function overloading:** Function overloading is defined as we can have more than one version of the same function. The versions of a function will have different signature means that they have a different set of parameters.

**Operator overloading:** Operator overloading is defined as the standard operator can be redefined so that it has a different meaning when applied to the instances of a class.

___

### 39) What is a **virtual destructor**?

A virtual destructor in C++ is used in the base class so that the derived class object can also be destroyed. A virtual destructor is declared by using the ~ tilde operator and then virtual keyword before the constructor.

#### Note: Constructor cannot be virtual, but destructor can be virtual.

**Let's understand this through an example**

-   Example without using virtual destructor

In the above example, delete b will only call the base class destructor due to which derived class destructor remains undestroyed. This leads to the memory leak.

When we use the virtual destructor, then the derived class destructor is called first, and then the base class destructor is called.


