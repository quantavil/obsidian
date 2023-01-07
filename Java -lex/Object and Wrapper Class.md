
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

An interface is used to define a generic template which can be implemented by various classes.

-   It contains method signatures and constant declarations
    
-   The methods declared in an interface are implicitly public and abstract and the data fields are implicitly public, static and final, i.e., constants
    
-   An interface can extend more than one interface and a class can implement more than one interface. This can be used to simulate multiple inheritance in Java
    
-   A class can extend from only one class but can implement any number of interfaces
    
-   The implements keyword is used to implement an interface. The classes implementing an interface must implement all the specified methods. Otherwise, they should be made abstract
    
-   An interface creates a type. Hence, its reference can be used to refer to the objects of the classes which implement that interface. This leads to dynamic binding
    

```java
interface Bank {
    float rateOfInterest();
}

class SBI implements Bank {
    public float rateOfInterest() {
        return 9.15f;
    }
}

class PNB implements Bank {
    public float rateOfInterest() {
        return 9.7f;
    }
}

class TestInterface2 {
    public static void main(String[] args) {
        Bank b = new SBI();
        System.out.println("ROI: " + b.rateOfInterest());
    }
}

```


If a class implements multiple interfaces, or an interface extends multiple interfaces, it is known as multiple inheritance.

```java
interface Printable {
    void print();
}

interface Showable {
    void show();
}

class A7 implements Printable, Showable {
    public void print() {
        System.out.println("Hello");
    }

    public void show() {
        System.out.println("Welcome");
    }

    public static void main(String args[]) {
        A7 obj = new A7();
        obj.print();
        obj.show();
    }
}
```

## Try and Catch

```java
class Tester {
    public static void main(String args[]) {
        try {
            // below code do not throw any exception
            int data = 25 / 5;
            System.out.println(data);
        }
        // catch won't be executed
        catch (NullPointerException e) {
            System.out.println(e);
        }
        // executed regardless of exception occurred or not
        finally {
            System.out.println("finally block is always executed");
        }

        System.out.println("rest of phe code...");
    }
}

```