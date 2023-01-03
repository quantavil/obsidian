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
3. Multiple constructors in a class
4.  Default Constructor

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


#### Parametrized Constructor

A Java constructor can also accept one or more parameters. Such constructors are known as parameterized constructors (constructor with parameters).

```java
class Main {

  String languages;

  // constructor accepting single value
  Main(String lang) {
    languages = lang;
    System.out.println(languages + " Programming Language");
  }

  public static void main(String[] args) {

    // call constructor by passing a single value
    Main obj1 = new Main("Java");
    Main obj2 = new Main("Python");
    Main obj3 = new Main("C");
  }
}
```

> [!Output]
> Java Programming Language
Python Programming Language
C Programming Language


#### Multiple constructors in a class

A class can have multiple constructors to initialize different members. Based on the arguments passed, the respective constructor is called.

```java
class Customer {
	public String customerId;
	public String customerName;
	public long contactNumber;
	public String address;
	public Customer() {
		System.out.println("Parameterless constructor called");
	}
	public Customer(String cId, String cName, long contact, String add) {
		System.out.println("Parameterized constructor called");
		customerId = cId;
		customerName = cName;
		contactNumber = contact;
		address = add;
	}
}

```

```java
public class Tester {
	public static void main(String args[]) {
		Customer customer1 = new Customer("C103", "Jacob", 5648394590L,
				"13th Street, New York");
		Customer customer2 = new Customer();
	}
}
```

> [!Output]
> Parameterized constructor called
Parameterless constructor called


#### Default Constructor

```java
class Main {

  int a;
  boolean b;

  public static void main(String[] args) {

    // A default constructor is called
    Main obj = new Main();

    System.out.println("Default Value:");
    System.out.println("a = " + obj.a);
    System.out.println("b = " + obj.b);
  }
}
```

> [!Output]
> Default Value:
a = 0
b = false


## this Keyword

The `this` keyword refers to the current object in a method or constructor.
### 1) this: to refer current class instance variable

The this keyword can be used to refer current class instance variable. If there is ambiguity between the instance variables and parameters, this keyword resolves the problem of ambiguity.

```java
class Tester {
	int a;
	Tester(int a) {
		a = a;
	}

	public static void main(String[] args) {
		Tester r = new Tester(100);
		System.out.println(r.a);
	}
}
```

In the above example, parameters (formal arguments) and instance variables are same. So, we are using this keyword to distinguish local variable and instance variable.

```java
class Tester {
	int a;
	Tester(int a) {
		this.a = a;
	}

	public static void main(String[] args) {
		Tester r = new Tester(100);
		System.out.println(r.a);
	}
}
```

### 2) this() : to invoke current class constructor
The this() constructor call can be used to invoke the current class constructor. It is used to reuse the constructor. In other words, it is used for constructor chaining.


```java
class Tester {
	int a;
	Tester() {
		System.out.println("This is default Constructor");
	}
	Tester(int a) {
		this();
		System.out.println(a);
	}

	public static void main(String[] args) {
		Tester r = new Tester(100);
		
	}
}
```
> [!Output]
> This is default Constructor


If `.java` file contains top level (not nested) `public` class, it has to have the same name as that public class. So if you have class like `public class A{...}` it needs to be placed in `A.java` file. Because of that **we can't have two public classes in one `.java` file**.

If having two public classes would be allowed then, and lets say aside from public `A` class file would also contain `public class B{}` it would require from `A.java` file to be _also_ named as `B.java` but files can't have two (or more) names (at least in all systems on which Java can be run).

So assuming your code is placed in `StaticDemoShow.java` file you have two options:

1.  If you want to have other class in same file make them non-public (lack of visibility modifier will represent _default/package-private_ visibility)
    
    ```java
     class StaticDemo { // It can no longer public
    
         static int a = 3;
         static int b = 4;
    
         static {
             System.out.println("Voila! Static block put into action");
         }
    
         static void show() {
             System.out.println("a= " + a);
             System.out.println("b= " + b);
         }
    
     }
    
     public class StaticDemoShow { // Only one top level public class in same .java file
         public static void main() {
             StaticDemo.show();
         }
     }
    ```
    
2.  Move all public classes to their own `.java` files. So in your case you would need to split it into two files:
    
    -   StaticDemo.java
        
        ```java
          public class StaticDemo { // Note: same name as name of file
        
              static int a = 3;
              static int b = 4;
        
              static {
                  System.out.println("Voila! Static block put into action");
              }
        
              static void show() {
                  System.out.println("a= " + a);
                  System.out.println("b= " + b);
              }
        
          }
        ```
        
    -   StaticDemoShow.java
        
        ```java
          public class StaticDemoShow { 
              public static void main() {
                  StaticDemo.show();
              }
          }
        ```

## Memory Management

When a new Customer object referenced by customerObj will be created in the memory.

But how does it happen? 

The memory is logically divided into two primary sections - **Stack** and **Heap**.

-   All local variables and method invocations are stored in the stack
    
-   All objects along with their instance variables are stored in the heap


![[Pasted image 20230103204341.png]]
```ad-note
Please note that reference variables are also local variables. Reference variables are local variables which stores the address of another memory location.
```

**Step 1:** The reference variable is created in the stack.
![[Pasted image 20230103204514.png]]

**Step 2:** The object is created in the heap.
![[Pasted image 20230103204527.png]]

**Step 3:** The reference variable in the stack refers to the object in the heap.
![[Pasted image 20230103204545.png]]

```ad-note
-   One reference variable can point to one and only one object at a time.
    
-   One object can be referenced by multiple reference variables at any given point of time.
```


Sometimes, even though a resource in a program is unreachable or not in use, the memory used by that resource is not deallocated. This is called **Memory leak** and is undesirable.
Java, on the other hand, has a **garbage collector** which automatically deallocates the memory used by such resources. This prevents memory leak.

### When an object does not have any reference, it becomes eligible for garbage collection.

**Case 1** - **Objects eligible for garbage collection**

-   When the reference variable pointing to the object is initialized to null, the object will not have any reference.
![[Pasted image 20230103204740.png]]

```java
public class Tester {
	public static void main(String[] args) {
		// Object creation
		Customer customerObj = new Customer("C101", "Stephen Abram",
				7856341287L, "D089, St. Louis Street, Springfield, 62729");
		// Reference variable initialized to null
		customerObj = null;
	}
}

```

**Case 2 - Objects eligible for garbage collection**

-   When the reference variable is initialized to a new object and there is no reference to the previous object

![[Pasted image 20230103204836.png]]

```java
public class Tester {
	public static void main(String[] args) {
		// Object creation
		Customer customerObj = new Customer("C101", "Stephen Abram",
				7856341287L, "D089, St. Louis Street, Springfield, 62729");
		// New object is set to the same reference
		customerObj = new Customer("C102", "James", 7898766723L,
				"D199, St. Louis Street, Springfield, 62729");
	}
}
```


