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


