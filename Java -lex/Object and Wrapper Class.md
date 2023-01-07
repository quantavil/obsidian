
-   equals() compares objects to check for equality
    
-   By default, equals() uses memory address to compare objects for equality (just like ==)
    
-   To make it work for different requirements, it needs to be overridden in the classes

-   hashCode() uses an object's data to generate a hash value, which should be a 32 bit integer
    
-   By default, it derives the hash value based on the memory address of the object being used
    
-   If two objects are equal according to the equals() method, hashCode() must produce the same integer value for the two objects
    
-   It is important to understand that if the hash codes of two objects are same, it doesn't prove that the objects are equal, i.e., it is possible for two unequal objects to have the same hash codes. 
    
-   hashCode() uses a formula to generate an integer based on the same attribute
    
-   Any formula can be used for generating the hash code as long as it generates the same value for same objects

## Abstraction

The abstract keyword signifies that something is not complete. It can be used with classes and methods.

An abstract method is a method without any definition, i.e., the body. The signature of an abstract method must be preceded by the abstract keyword.

```java
public abstract double payBill(double totalPrice);
```

An abstract class is a class which is incomplete and **cannot be instantiated**.

```java
abstract public class Customer {}

```
Some points that you should be knowing about abstract class are:

-   An abstract class encapsulates the common behaviors of all its child classes with the help of abstract methods
    
-   Concrete (non-abstract) classes which extend an abstract class must implement all the abstract methods. Otherwise, they should be made abstract as well.
    
-   If a class contains at least one abstract method, the class should be abstract.
    
-   A class can be made abstract even without any abstract methods.

- Thus, **abstract classes** enforce **inheritance** (since they can’t be instantiated)

- **abstract methods** enforce **overriding** (since they are incomplete with no implementation)


## 

An **interface in Java** is a blueprint of a class. It has static constants and abstract methods.

The interface in Java is _a mechanism to achieve [abstraction](https://www.javatpoint.com/abstract-class-in-java)_. There can be only abstract methods in the Java interface, not method body. It is used to achieve abstraction and multiple [inheritance in Java](https://www.javatpoint.com/inheritance-in-java).

In other words, you can say that interfaces can have abstract methods and variables. It cannot have a method body.