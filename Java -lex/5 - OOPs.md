## Pass by Value

Whenever a value of a *primitive data type is passed*, the values are copied from the actual parameters to the formal parameters. 
```ad-info
Formal parameters are those parameters that are defined during function definition and Actual parameters are those which are passed during the function call in other Function.
```

This kind of parameter passing is known as **pass by value**. In pass by value, both the actual and formal parameters point to different memory locations and the values are copied in both the memory locations.

```java
class Main {
    public static void main(String[] args) {

        int number = 25;
        System.out.println("Before calling display method = " + number);
        display(number);
        System.out.println("After calling display method = " + number);
    }

    public static void display(int num) {
        num =100;
        System.out.println("Inside display method = "+ num );

    }
}
```

> [!Output]
> Before calling display method = 25
Inside display method = 100
After calling display method = 25

## Pass by reference

When an *object ( including non-primitive data types)* is passed as a parameter, the formal and the actual parameters both refer to the same object and hence the same memory location. 
Therefore, the changes made inside the method to the formal parameters are reflected in the actual parameters also. This kind of parameter passing is known as **pass by reference**.

```java
class Main {
    public static void main(String[] args) {

        int[] values = { 23, 37, 29 };
        System.out.println(" Before displayAray Method , first element  = " + values[0]);
        displayArray(values);
        System.out.println(" After displayAray Method , first element  = " + values[0]);

    }

    public static void displayArray(int[] values) {
        System.out.println("Inside displayArray method , first element = " + values[0]);
        values[0] = 100;
    }
}
```

> [! Output]
 Before displayAray Method , first element  = 23
Inside displayArray method , first element = 23
 After displayAray Method , first element  = 100

## Constructor

A **constructor** in Java is a special method that is used to initialize class variables at the time of object creation. 

Each time an object is created using the new() keyword, a constructor is called. A constructor can be created by the programmer. If the developer does not create any constructor, then, Java provides a default constructor.

```java
class Test {
  Test() {
    // constructor body
  }
}
```

### Types of Constructor

In Java, constructors can be divided into 3 types:

1.  No-Arg Constructor / Parameterless Constructor
2.  Parameterized Constructor
3.  Default Constructor

#### Parameterless  Constructor
A constructor with no arguments is known as a **parameterless constructor**. If you don’t define a constructor in a class, then Java creates a default parameterless constructor and initializes the default values to the class variables based on the data type.

```java
class Main {

  int i;

  // constructor with no parameter
  private Main() {
    i = 5;
    System.out.println("Constructor is called");
  }

  public static void main(String[] args) {

    // calling the constructor without any parameter
    Main obj = new Main();
    System.out.println("Value of i: " + obj.i);
  }
}
```