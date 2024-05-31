Java is a high-level, object-oriented programming language  It is platform-independent due to its use of the Java Virtual Machine (JVM), which allows Java programs to run on any device or operating system that has the JVM installed. Java is widely used for building enterprise-scale applications, mobile applications (especially Android), web servers, and embedded systems.

### Can java be said to be the complete object-oriented programming language?

Java is not considered a purely object-oriented programming language because it uses primitive data types (such as int, char, etc.) which are not objects. In a purely object-oriented language, everything would be an object. Despite this, Java is highly object-oriented and supports key OOP principles like encapsulation, inheritance, and polymorphism.


### Difference between Heap and Stack Memory in java. And how java utilizes this.

Stack memory is the portion of memory that was assigned to every individual program. And it was fixed. On the other hand, Heap memory is the portion that was not allocated to the java program but it will be available for use by the java program when it is required, mostly during the runtime of the program.

### What do you understand by an instance variable and a local variable?

An instance variable is a variable that is defined within a class and is associated with an instance of that class. Each object of the class has its own copy of the instance variable, and it is used to store the state of the object.

A local variable is a variable that is declared within a method, constructor, or block and is only accessible within that method, constructor, or block. Local variables are not visible outside of their scope and are used for temporary storage of data needed only within the method's execution.

### OOPs

The Object-Oriented Programming (OOP) concept is based on four main principles:

1. **Encapsulation**: This principle refers to bundling the data (attributes) and methods (functions) that operate on the data into a single unit, known as a class. It also involves restricting direct access to some of the object's components, which is typically done through access modifiers like private, protected, and public. Encapsulation helps in protecting the integrity of the data.

2. **Inheritance**: Inheritance allows a new class (subclass or derived class) to inherit properties and behaviors (methods) from an existing class (superclass or base class). This promotes code reuse and establishes a natural hierarchy between classes. The subclass can also override or extend the behaviors of the superclass.

3. **Polymorphism**: Polymorphism enables a single entity to take multiple forms. In OOP, it typically refers to the ability of different classes to be treated as instances of the same class through inheritance. There are two types of polymorphism:
   - **Compile-time (or static) polymorphism**: Achieved through method overloading.
   - **Runtime (or dynamic) polymorphism**: Achieved through method overriding.

4. **Abstraction**: Abstraction involves hiding the complex implementation details and showing only the essential features of the object. It simplifies the interaction with the object by exposing only what is necessary. Abstract classes and interfaces are commonly used to achieve abstraction in OOP.

These principles help in creating modular, reusable, and maintainable code.

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

### Comment on method overloading and overriding by citing relevant examples.

Method overloading is a feature in Java that allows a class to have multiple methods with the same name but with different parameters. This means that methods within a class can have the same name, as long as their parameter lists (number, type, or order of parameters) are different.
```java
class OverloadingHelp {
   public int findarea (int l, int b) {
           int var1;
           var1 = l * b;
           return var1;
   }
   public int findarea (int l, int b, int h) {
           int var2;
           var2 = l * b * h;
           return var2;
   }
}
```