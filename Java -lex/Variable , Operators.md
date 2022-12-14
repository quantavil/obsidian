Some of the keywords in Java language are listed below: 

![[Pasted image 20221201214039.png]]

Data is stored in **variables**. A variable is a named memory location which holds some value. The value stored in a variable can vary during the execution of the program.

In Java, an **identifier** is the name given to a variable, method or class to uniquely identify it. 

In Java, following rules apply to the identifier name: 

-   It can contain alphanumeric characters([a-z], [A-Z], [0-9]), dollar sign ($), underscore (_) 
    
-   It should not start with a digit ([0-9]) 
    
-   It should not have spaces 
    
-   It should not be a Java keyword 
    
-   It is case-sensitive 
    
-   It has no length restrictions

## Data type

**Data type** defines the type of data that can be stored in the variable and the memory required by

![[Pasted image 20221201214336.png]]

![[Pasted image 20221201214449.png]]

## [Operators](https://www.geeksforgeeks.org/operators-in-java)

**Operators** are the symbols used to perform specific operations. There are various operators that can be used for different purposes.

The operators are categorized as: 

-   Unary 
    
-   Arithmetic  
    
-   Relational 
    
-   Logical 
    
-   Ternary 
    
-   Assignment 
    
-   Bitwise

**Unary operators** act upon only one operand and perform operations such as increment, decrement, negating an expression or inverting a boolean value.

![[Pasted image 20221201224653.png]]

**Arithmetic operators** are used to perform basic mathematical operations like addition, subtraction, multiplication and division

![[Pasted image 20221201232211.png]]

**Relational operators** are used to compare two values. The result of all the relational operations is either true or false.

![[Pasted image 20221201232228.png]]

**Logical operators** are used to combine two or more relational expressions or to negate the result of a relational expression.

![[Pasted image 20221201232251.png]]

**Ternary operator** is used as a single line replacement for if-then-else statements and acts upon three operands. 

**Syntax:** 

```java
<condition> ? <value if condition is true> : < value if condition is false>

```

**Example:**
```java
public static void main(String args[]) {
	int numOne = 10;
	int numTwo = 5;
	int min = (numOne < numTwo) ? numOne : numTwo;
	System.out.println(min); //Output will be 5
}
```

**Assignment operator** is used to assign the value on the right hand side to the variable on the left hand side of the operator.

![[Pasted image 20221201232633.png]]

**Bitwise operators** are used to performing the manipulation of individual bits of a number. They can be used with any integral type (char, short, int, etc.).

You will now have a look at some of the bitwise operators and how they work.

- **Bitwise OR(|)**
    
It returns bit by bit OR of the input values. If either of the bits is 1, then it gives 1, else it gives 0. 
 
E.g. - The output of 10 | 5 is 15.
![[Pasted image 20221202102925.png]]

- **Bitwise AND(&)** 
It returns bit by bit AND of the input values. If both the bits are 1, then it gives 1, else it gives 0.

E.g. - The output of 10 & 5 is 0.
   ![[Pasted image 20221202102944.png]]

-  **Java Left Shift Operator**

The left shift operator shifts all bits towards the left by a certain number of specified bits. It is denoted by `<<`.

![Bits are shifted one position left and 0 is added to the last position](https://cdn.programiz.com/sites/tutorial2program/files/java-left-shift-operator.png "Java Left Shift Operator")

```java
class Main {
  public static void main(String[] args) {
    
    int number = 2;
   
    // 2 bit left shift operation 
    int result = number << 2;
    System.out.println(result);    // prints 8
  }
}
```

- **Java Signed Right Shift Operator**

The signed right shift operator shifts all bits towards the right by a certain number of specified bits. It is denoted by `>>`.

When we shift any number to the right, the least significant bits (rightmost) are discarded and the most significant position (leftmost) is filled with the sign bit. For example,

```
// right shift of 8
8 = 1000 (In Binary)

// perform 2 bit right shift
8 >> 2:
1000 >> 2 = 0010 (equivalent to 2)
```

```java
class Main {
  public static void main(String[] args) {
    
    int number1 = 8;
    int number2 = -8;
    
    // 2 bit signed right shift
    System.out.println(number1 >> 2);    // prints 2
    System.out.println(number2 >> 2);    // prints -2
  }
}
```


- **Java Unsigned Right Shift Operator**

Java also provides an unsigned right shift. It is denoted by `>>>`.
Here, the vacant leftmost position is filled with **0** instead of the sign bit. For example,

```
// unsigned right shift of 8
8 = 1000

8 >>> 2 = 0010

// unsigned right shift of -8
-8 = 1000 (see calculation above)

-8 >>> 2 = 0010
```

```java
class Main {
  public static void main(String[] args) {
    
    int number1 = 8;
    int number2 = -8;
    
    // 2 bit signed right shift
    System.out.println(number1 >>> 2);    // prints 2
    System.out.println(number2 >>> 2);    // prints 1073741822
  }
}
```