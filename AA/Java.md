- [[#Can java be said to be the complete object-oriented programming language?|Can java be said to be the complete object-oriented programming language?]]
- [[#Difference between Heap and Stack Memory in java. And how java utilizes this.|Difference between Heap and Stack Memory in java. And how java utilizes this.]]
- [[#What do you understand by an instance variable and a local variable?|What do you understand by an instance variable and a local variable?]]
- [[#Why we use object-oriented programming?|Why we use object-oriented programming?]]
- [[#Why we use object-oriented programming?#TERMINOLOGIES|TERMINOLOGIES]]
- [[#What are the main features of OOPs?|What are the main features of OOPs?]]
- [[#What are the main features of OOPs?#Data Abstraction|Data Abstraction]]
	- [[#Data Abstraction#Advantages|Advantages]]
	- [[#Data Abstraction#Real Life Example|Real Life Example]]
- [[#What are the main features of OOPs?#Encapsulation|Encapsulation]]
	- [[#Encapsulation#Advantages|Advantages]]
	- [[#Encapsulation#Real Life Example|Real Life Example]]
- [[#What are the main features of OOPs?#Polymorphism|Polymorphism]]
	- [[#Polymorphism#Advantages|Advantages]]
	- [[#Polymorphism#Real Life Example|Real Life Example]]
- [[#What are the main features of OOPs?#Inheritance|Inheritance]]
	- [[#Inheritance#Advantages|Advantages]]
	- [[#Inheritance#Real Life Example|Real Life Example]]
- [[#What are the main features of OOPs?#Why OOPs is so Popular / Advantages of OOPs /Why do we need oops|Why OOPs is so Popular / Advantages of OOPs /Why do we need oops]]
- [[#What are the main features of OOPs?#What is Overloading and Overriding?|What is Overloading and Overriding?]]
- [[#What are the main features of OOPs?#What is Constructor ?|What is Constructor ?]]
- [[#What are the main features of OOPs?#What are the default values assigned to variables and instances in java?|What are the default values assigned to variables and instances in java?]]
- [[#What are the main features of OOPs?#equals() vs ==|equals() vs ==]]
- [[#What are the main features of OOPs?#Briefly explain the concept of constructor overloading|Briefly explain the concept of constructor overloading]]
- [[#What are the main features of OOPs?#Method overloading and method overriding|Method overloading and method overriding]]
- [[#What are the main features of OOPs?#Class, Object, Constructor|Class, Object, Constructor]]
- [[#What are the main features of OOPs?#Explain the use of final keyword in variable, method and class.|Explain the use of final keyword in variable, method and class.]]
- [[#What are the main features of OOPs?#Super|Super]]

Java is a high-level, object-oriented programming language  It is platform-independent due to its use of the Java Virtual Machine (JVM), which allows Java programs to run on any device or operating system that has the JVM installed. Java is widely used for building enterprise-scale applications, mobile applications (especially Android), web servers, and embedded systems.

### Can java be said to be the complete object-oriented programming language?

Java is not considered a purely object-oriented programming language because it uses primitive data types (such as int, char, etc.) which are not objects. In a purely object-oriented language, everything would be an object. Despite this, Java is highly object-oriented and supports key OOP principles like encapsulation, inheritance, and polymorphism.


### Difference between Heap and Stack Memory in java. And how java utilizes this.

Stack memory is the portion of memory that was assigned to every individual program. And it was fixed. On the other hand, Heap memory is the portion that was not allocated to the java program but it will be available for use by the java program when it is required, mostly during the runtime of the program.

### What do you understand by an instance variable and a local variable?

An instance variable is a variable that is defined within a class and is associated with an instance of that class. Each object of the class has its own copy of the instance variable, and it is used to store the state of the object.

A local variable is a variable that is declared within a method, constructor, or block and is only accessible within that method, constructor, or block. Local variables are not visible outside of their scope and are used for temporary storage of data needed only within the method's execution.

## Why we use object-oriented programming?

Object-oriented programming is the programming paradigm that is defined using objects. Objects can be considered as real-world instances of entities like class, that have some characteristics and behaviors.  

-   OOPs helps users to understand the software easily, although they don’t know the actual implementation.
-   With OOPs, the readability, understandability, and maintainability of the code increases multifold.
-   Even very big software can be easily written and managed easily using OOPs.
### TERMINOLOGIES
-   **Class** - A class is a group of objects that share common properties and 
  behavior. It is a blueprint or template from which objects are created.  
    
-   **Object**- Object is any real-world entity that can have some characteristics or which can perform some tasks. It is also called the instance of a class

---

## What are the main features of OOPs?

### Data Abstraction

1.  Data abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.
2.  Hiding the implementation and displaying only the functionality to the users.

#### Advantages

1.  It reduces the complexity of viewing things.
2.  Reduces the duplication of the code

#### Real Life Example

*Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of the car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of the accelerator, brakes, etc in the car.*

### Encapsulation

 The basic idea of Encapsulation is to wrap up both data and methods into one single unit. The way that data and methods are organized does not matter to the end-user

#### Advantages

1.  Encapsulation protects an object from unwanted access by clients.
2.  Simplifies the maintenance of the application

#### Real Life Example

*A Real-Life Example of Encapsulation is a School Bag.*

### Polymorphism

Polymorphism is the ability to exit in many forms. We can construct various classes to have methods with the same name while creating class methods.

Polymorphism is divided into two types:  

-   **Compile Time Polymorphism** - Compile time polymorphism, also known as Static Polymorphism, refers to the type of Polymorphism that happens at compile time. What it means is that the compiler decides what shape or value has to be taken by the entity in the picture.  
    
-   **Runtime Polymorphism** - Runtime polymorphism, also known as Dynamic Polymorphism, refers to the type of Polymorphism that happens at the run time. What it means is it can't be decided by the compiler. Therefore what shape or value has to be taken depends upon the execution. Hence the name Runtime Polymorphism.

#### Advantages

1.  It helps the programmer to reuse the codes, i.e. classes once written, tested and implemented can be reused as required. Saves a lot of time.
2.  A single variable can be used to store multiple data types.

#### Real Life Example

*Like a man at the same time is a father, a husband, an employee. So the same person possesses different behavior in different situations. This is called polymorphism.*

### Inheritance

Inheritance is a feature of OOPs which allows subclasses classes to inherit properties from the parent class.  

%%Types of Inheritance

-   **Single inheritance** - When a class inherits from a single class, it is known as a single inheritance
    
-   **Multiple inheritances** - Multiple inheritances come into the picture when a class inherits from more than one base class.  
      
    Parent 1 && Parent2 → child
    
-   **Multilevel inheritance** - When there is a chain of inheritance, it is known as multilevel inheritance.  
      
    Example: Animal → Dog → Puppy  
    Puppy Inherits from the Dog Class, Dog class inherits from the Class Animal.
    
-   **Hierarchical inheritance** - When two or more classes inherit a single class, it is known as hierarchical inheritance.  
      
    Example: Animal → Dog = Cats
    
-   **Hybrid inheritance** - Hybrid inheritance is a combination of multiple and multi-level inheritances.ance** - Hybrid inheritance is a combination of multiple and multi-level inheritances.%%

#### Advantages

The main advantages of inheritance are code reusability and readability. When a child class inherits the properties and functionality of the parent class, we need not to write the same code again in the child class. This makes it easier to reuse the code, makes us write less code and the code becomes much more readable.

#### Real Life Example

*If there is a class such as ‘vehicle’, other classes like ‘car’, ‘bike’, etc can inherit common properties from the vehicle class.*


### Why OOPs is so Popular / Advantages of OOPs /Why do we need oops

1) OOP provides a clear modular structure for programs

2) OOP makes it easy to maintain and modify existing code

3) Code Reusability : We can build the programs from standard working modules that communicate with one another, rather than having to start writing the code from scratch which leads to saving of development time and higher productivity,

5) OOP language allows to break the program into the bit-sized problems that can be solved easily (one object at a time).
---

### What is Overloading and Overriding?

When two or more methods in the same class have the same name but different parameters, it's called Overloading.  

When the method name and parameters are the same in the superclass and the child class, it's called Overriding.  

---

### What is Constructor ?
Constructors are **generally used for instantiating an object**, It is a method that is called when an object is created. 


### What are the default values assigned to variables and instances in java?

There are no default values assigned to the variables in java. We need to initialize the value before using it. Otherwise, it will throw a compilation error of (**Variable might not be initialized**).

### equals() vs ==

| equals()                                                                                                           | ==                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------- |
| This is a method defined in the Object class.                                                                      | It is a binary operator in Java.                                                                                                        |
| This method is used for checking the equality of contents between two objects as per the specified business logic. | This operator is used for comparing addresses (or references), i.e checks if both the objects are pointing to the same memory location. |

### Briefly explain the concept of constructor overloading

Constructor overloading is the process of creating multiple constructors in the class consisting of the same name with a difference in the constructor parameters. Depending upon the number of parameters and their corresponding types, distinguishing of the different types of constructors is done by the compiler.

```java
class Hospital {
int variable1, variable2;
double variable3;
public Hospital(int doctors, int nurses) {
 variable1 = doctors;
 variable2 = nurses;
}
public Hospital(int doctors) {
 variable1 = doctors;
}
public Hospital(double salaries) {
 variable3 = salaries
}
}
```

### Method overloading and method overriding 

1. **Method Overloading**:
   - Method overloading occurs when multiple methods in the same class have the same name but different parameter lists (number, type, or order of parameters).
   - It allows a class to have several methods with the same name, each providing different functionality based on the parameters they accept.
   - Method overloading is determined at compile time (static polymorphism).
   - Example:

```java
public class Calculator {
    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Method to add three integers (overloaded version)
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

2. **Method Overriding**:
   - Method overriding occurs when a subclass provides a specific implementation for a method that is already defined in its superclass.
   - It allows a subclass to provide its own implementation of a method inherited from the superclass, thus modifying or extending its behavior.
   - Method overriding is determined at runtime (dynamic polymorphism).
   - Example:

```java
public class Animal {
    // Method to make a sound
    public void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

public class Dog extends Animal {
    // Method overriding to provide specific implementation for Dog
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}
```

In summary, method overloading allows multiple methods with the same name but different parameters within the same class, while method overriding allows a subclass to provide its own implementation of a method inherited from a superclass.
### Class, Object, Constructor

class in Java is a blueprint or template for creating objects. It defines the properties (attributes) and behaviors (methods) that objects of the class will have.
**object** is an instance of a class representing a real-world entity, 
constructor is a special type of method in Java that is automatically called when an object of a class is created. 

### Explain the use of final keyword in variable, method and class.

In Java, the final keyword is used as defining something as constant /final and represents the non-access modifier.

- **final variable:**
    - When a variable is declared as final in Java, the value can’t be modified once it has been assigned.
    - If any value has not been assigned to that variable, then it can be assigned only by the constructor of the class.
- **final method:**
    - A method declared as final cannot be overridden by its children's classes.
    - A constructor cannot be marked as final because whenever a class is inherited, the constructors are not inherited. Hence, marking it final doesn't make sense. Java throws compilation error saying - `modifier final not allowed here`
- **final class:**
    - No classes can be inherited from the class declared as final. But that final class can extend other classes for its usage

### Super

The `super` keyword in Java is used to refer to the superclass (parent class) of the current class. It can be used in the following ways:

1. **Accessing superclass members**: 
   - `super.method()` - Calls a method from the superclass.
   - `super.variable` - Accesses a variable from the superclass.

2. **Constructor chaining**: 
   - `super()` - Calls the superclass constructor. This must be the first statement in a subclass constructor.

3. **Accessing overridden methods or variables**: 
   - `super.method()` - Calls the overridden method in the superclass.
   - `super.variable` - Accesses the overridden variable in the superclass.

Overall, the `super` keyword provides a way to access superclass members and constructors, allowing for code reuse and providing flexibility in class hierarchies.