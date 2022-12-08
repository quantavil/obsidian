           

**1.** **What is a pointer? Give an example.** 

**Answer:** Pointer is a variable that stores the address of another variable. Pointers allow passing variables by references using the address. For example –

**int** a = 23;

**int** *ptr = &a;

cout << ptr;

**2.** **What is Null Pointer, Dangling Pointer, Void Pointer, Wild Pointer**

**Answer**:

**Null Pointer:** NULL Pointer is a pointer which is pointing to nothing. In case, if we don’t have address to be assigned to a pointer, then we can simply use NULL.

**Dangling Pointer:** A pointer pointing to a memory location that has been deleted (or freed) is called dangling pointer.

**Void pointer:** is a a pointer that points to some data location in storage, which doesn’t have any specific type. Void refers to the type. 

**Wild Pointer:** A pointer which has not been initialized to anything (not even NULL) is known as wild pointer. The pointer may be initialized to a non-NULL garbage value that may not be a valid address.

**3.** **What is the difference between reference and pointer****?** 

**Answer:** Pointer stores the address of a variable, but the reference is just a copy of a variable with a different name. References have to be initialized, whereas pointer need not be. To initialize pointer, we use the dereference operator,

**int** a;

**int** *ptr = &a;

// We use the & reference operator to initialize reference variable.

**int** a = 20;

**int** &**ref** = a;

**4.** **Tell me one disadvantage of using C++.** 

**Answer:** There is no built-in support for threads. If they ask more, you can say it doesn’t support garbage collection

**5.** **What is friend function/class?** 

**Answer:**

-   **Friend function –** if a function is marked as a ‘friend’ of a particular class, it can access the protected and private members of the class.
-   **Friend class –** same as function, if a class is marked as friend of another class, it can access the protected and private members of that class.

Example –

**class** **Student** {

private: int roll;

public: friend class Teacher;

};

**Class** **Teacher**{

private: float marks;

public: void getRollNumber(Student& stud){

cout << stud.roll;

}

};

**6.** **What are Structs and how are they different from Classes?** 

**Answer:** Struct is a customized data type that contains other data types. For example,

**struct** **Student** {

**int** rollNumber;

**char** section;

**void** **getName**();

};

-   Members of a class are private by default, to make a variable public, we need to add the public modifier. In a struct, by default members are public and if we need any private members, we have to use a modifier.
-   A class can be inherited but structs cannot.

**7.** **Explain some important differences between C & C++.** 

**Answer:** 

**C**

**C++**

C is a procedural language, hence there is no concept of classes, objects, inheritance, encapsulation, and polymorphism.

C++ is an Object-Oriented language. Polymorphism, encapsulation and inheritance are the essences of OOPS.

**8.** **What is preprocessor?** 

**Answer:** The preprocessors are the directives, which give instructions to the compiler to preprocess the information before actual compilation starts. All preprocessor directives begin with #,


### 1\. What are the different data types present in C++?

The 4 data types in C++ are given below:

-   Primitive Datatype(basic datatype). Example- char, short, int, float, long, double, bool, etc.
-   Derived datatype. Example- array, pointer, etc.
-   Enumeration. Example- enum
-   User-defined data types. Example- structure, class, etc.

### 2\. What is the difference between C and C++?

The main difference between C and C++ are provided in the table below:

| C | C++ |
| --- | --- |
| C is a procedure-oriented programming language. | C++ is an object-oriented programming language. |
| C does not support data hiding. | Data is hidden by encapsulation to ensure that data structures and operators are used as intended. |
| C is a subset of C++ | C++ is a superset of C. |
| Function and operator overloading are not supported in C | Function and operator overloading is supported in C++ |
| Namespace features are not present in C | Namespace is used by C++, which avoids name collisions. |
| Functions can not be defined inside structures. | Functions can be defined inside structures. |
| calloc() and malloc() functions are used for memory allocation and free() function is used for memory deallocation. | new operator is used for memory allocation and deletes operator is used for memory deallocation. |
