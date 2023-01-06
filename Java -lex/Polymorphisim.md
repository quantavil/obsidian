Polymorphism is the ability of an object to take different forms, i.e., a single action that can be performed in different ways. So, polymorphism means many forms.

Polymorphism is of two types:

-   Static polymorphism
    
-   Dynamic polymorphism

## Static Polymorphism 

Polymorphism that gets resolved during compile time is known as **static polymorphism** or **compile time polymorphism**. This polymorphism is achieved using overloading of the methods in the same class, called as **Method overloading**.

Method overloading allows the programmer to have multiple methods with the same name in the same class, but differing in their signature.

Signature can differ by

-   the number of parameters
    
-   the data type of parameters
    
-   the order of the parameters
    

Note: We cannot overload methods by their return type, i.e., two or more methods are not overloaded if they differ only in their return type.


## Dynamic Polymorphism

**Dynamic polymorphism** is a process or mechanism in which a call to an overridden method is to resolve at runtime rather than compile-time. It is also known as [**runtime polymorphism**](https://www.javatpoint.com/runtime-polymorphism-in-java) or **dynamic method dispatch**. We can achieve dynamic polymorphism by using the [**method overriding**](https://www.javatpoint.com/method-overriding-in-java).

### Method Overriding

It provides a specific implementation to a method that is already present in the parent class. it is used to achieve run-time polymorphism. Remember that, it is not possible to override the **static** method. Hence, we cannot override the main() method also because it is a static method.