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

 - **Left shift operator(<<)** 
It takes two operators and left shifts the bits of the first operand. The second operand decides the number of places to shift. It fills 0 on voids left as a result. 

E.g. - The output of 10<<1 is 20 if the numbers are stored in 32 bit system.

-   **Signed Right shift operator(>>)**
    
    It takes two operators and right shifts the bits of the first operand. The second operand decides the number of places to shift. It fills 0 on voids left as a result if the first operand is positive else it fills 1.
    

     E.g. -

             **Example of positive number**

             The output of 10>>1 is 5.

              10 is represented as 00000000 00000000 00000000 00001010.

              After right shifting by 1 bit, the result becomes 00000000 00000000 00000000 00000101 which is 5.

             **Example of negative number**

             The output of -10>>1 is -5.

             -10 is represented as 11111111 11111111 11111111 11110110.

             After right shifting by 1 bit, the result becomes 11111111 11111111 11111111 11111011 which is -5.

-   **Unsigned Right shift operator(>>>)**

     It takes two operators and right shifts the bits of the first operand. The second operand decides the number of places to shift. It fills       0 on voids left as a result.

     E.g. -

             **Example of positive number**

             The output of 10>>>1 is 5.

              10 is represented as 00000000 00000000 00000000 00001010.

              After right shifting by 1 bit, the result becomes 00000000 00000000 00000000 00000101 which is 5.

             **Example of negative number**

             The output of -10>>>1 is 214783643.

             -10 is represented as 11111111 11111111 11111111 11110110.

             After right shifting by 1 bit, the result becomes 01111111 11111111 11111111 11111011 which is 214783643.
             
```java
// Java program to illustrate
// bitwise operators

public class operators {
	public static void main(String[] args)
	{
		// Initial values
		int a = 5;
		int b = 7;

		// bitwise and
		// 0101 & 0111=0101 = 5
		System.out.println("a&b = " + (a & b));

		// bitwise or
		// 0101 | 0111=0111 = 7
		System.out.println("a|b = " + (a | b));

		// bitwise xor
		// 0101 ^ 0111=0010 = 2
		System.out.println("a^b = " + (a ^ b));

		// bitwise not
		// ~00000000 00000000 00000000 00000101=11111111 11111111 11111111 11111010
		// will give 2's complement (32 bit) of 5 = -6
		System.out.println("~a = " + ~a);

		// can also be combined with
		// assignment operator to provide shorthand
		// assignment
		// a=a&b
		a &= b;
		System.out.println("a= " + a);
	}
}

```

**[Shift Operator in Java](https://www.geeksforgeeks.org/shift-operator-in-java/?ref=gcse)**

