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
static {
    deliveryCharge = 1.5f; // initialize the static variable
    }
```