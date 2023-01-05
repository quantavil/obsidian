When a variable is declared as **Static**, then a single copy of the variable is created and shared among all objects at the class level. Memory allocation for such variables happen only once when the class is loaded in the memory. These variables are also known as class-level variables.

Since static variables and instance variables are both members of the class, they are often referred to as **member variables**.


- We can't access non static variable in static method (Cannot make a static reference to  the non-static field name)

- The Static method cant refer to this or super keyword. i.e. we can't use this or super keyword inside static method

- We can access static method inside normal methods


**Syntax**

```java
private static float deliveryCharge; //Declaration of static variable 
```

```java
private static float deliveryCharge = 1.5f; 

```

### **Static blocks** 

**Static blocks** are used to initialize static variables when it cannot be done in a single line. They can also be used to add preprocessing if required.

```java
// Java program to demonstrate use of static blocks
  
class Test
{
    // static variable
    static int a = 10;
    static int b;
      
    // static block
    static {
        System.out.println("Static block initialized.");
        b = a * 4;
    }
  
    public static void main(String[] args)
    {
       System.out.println("from main");
       System.out.println("Value of a : "+a);
       System.out.println("Value of b : "+b);
    }
}
```

> [!Output]
> Static block initialized.
from main
Value of a : 10
Value of b : 40


### Static Variable

When a variable is declared as static, then a single copy of the variable is created and shared among all objects at the class level. Static variables are, essentially, global variables. All instances of the class share the same static variable.

**Important points for static variables:**

-   We can create static variables at the class level only.
-   static block and static variables are executed in the order they are present in a program.

```java
// Java program to demonstrate execution
// of static blocks and variables
  
class Test
{
    // static variable
    static int a = m1();
      

    // static method
    static int m1() {
        System.out.println("from m1");
        return 20;
    }
      
    // static method(main !!)
    public static void main(String[] args)
    {
       System.out.println("Value of a : "+a);
       System.out.println("from main");
    }
}
```

> [!Output]
> from m1
Value of a : 20
from main


### Static methods

When a method is declared with the _static_ keyword, it is known as the static method. The most common example of a static method is the _main( )_ method.
Any static member can be accessed before any objects of its class are created, and without reference to any object.

-   They can only directly call other static methods.
-   They can only directly access static data.
-   They cannot refer to [this](https://www.geeksforgeeks.org/this-reference-in-java/) or [super](https://www.geeksforgeeks.org/super-keyword/) in any way.

```java
// Java program to demonstrate restriction on static methods
  
class Test
{
    // static variable
    static int a = 10;
      
    // instance variable
    int b = 20;
      
    // static method
    static void m1()
    {
        a = 20;
        System.out.println("from m1");
          
         // Cannot make a static reference to the non-static field b
         b = 10; // compilation error
                  
         // Cannot make a static reference to the 
                 // non-static method m2() from the type Test
         m2();  // compilation error
           
         //  Cannot use super in a static context
         System.out.println(super.a); // compiler error 
    }
      
    // instance method
    void m2()
    {    
        System.out.println("from m2");
    }
      
      
      
    public static void main(String[] args)
    {
        // main method 
    }
}
```

## Association

Association is a relation between two separate classes which establishes through their Objects. Association can be one-to-one, one-to-many, many-to-one, many-to-many. In Object-Oriented programming, an Object communicates to another object to use functionality and services provided by that object. **Composition** and **Aggregation** are the two forms of association.


## Inheritance

**Inheritance in Java** is a mechanism in which one object acquires all the properties and behaviors of a parent object.
In terms of OOP, a child class inherits all the non-private attributes and methods.

```java
class Customer {
	//Parent/Super/Base class
}
class RegularCustomer extends Customer {        // RegularCustomer is a Customer
	//Child/Sub/Derived class
}
class Guest extends Customer {                  // Guest is a Customer
	//Child/Sub/Derived class
}
```

### Terms used in Inheritance

-   **Class:** A class is a group of objects which have common properties. It is a template or blueprint from which objects are created.
-   **Sub Class/Child Class:** Subclass is a class which inherits the other class. It is also called a derived class, extended class, or child class.
-   **Super Class/Parent Class:** Superclass is the class from where a subclass inherits the features. It is also called a base class or a parent class.
-   **Reusability:** As the name specifies, reusability is a mechanism which facilitates you to reuse the fields and methods of the existing class when you create a new class. You can use the same fields and methods already defined in the previous class.

-  We can't access private members of class through inheritance.
- Method Overriding is only possible through Inheritance.


![[Pasted image 20230105142136.png]]
![[Pasted image 20230105142206.png]]

```ad-note
Multiple inheritance is not supported in Java through class.


```bash
Consider a scenario where A, B, and C are three classes. The C class inherits A and B classes. If A and B classes have the same method and you call it from child class object, there will be ambiguity to call the method of A or B class.
```


```java

```

The main advantages of inheritance are:

-   Code reusability - The codes are defined only once and can be used multiple times. We define the functionalities in the parent class and any number of child classes can use the functionalities at any time.
    
-   Saves time and effort due to reusability of code.
    
-   Inheritance makes the application code more flexible to changes
    
-   Inheritance results in better organization of codes into smaller and simpler compilation units which makes the code more readable and easy to debug


## Super Keyword

- super is used to refer immediate parent class instance variable.
- super can be used to invoke parent class method.
- super is used to invoke parent class constructor.


```java
class Person {
    int id;
    String name;
    String color = "white";

    Person() {
        System.out.println("Parameterless Constructor of Parent Class");
    }

    Person(int id, String name) {
        this.id = id;
        this.name = name;
    }

    void eat() {
        System.out.println("eating...");
    }
}

class Emp extends Person {
    float salary;

    Emp() {
        super();
        super.eat(); // invoke parent class method.
    }

    Emp(int id, String name, float salary) {

        super(id, name);// reusing parent constructor
        this.salary = salary;
    }

    void display() {
        System.out.println(id + " " + name + " " + salary);
        System.out.println(super.color);//refering to parent instance variable
    }

}

class Tester {
    public static void main(String[] args) {
        Emp e1 = new Emp(1, "ankit", 45000f);
        e1.display();
        Emp e2 = new Emp();
        e2.display();
    }
}
```


