Polymorphism is the ability of an object to take different forms, i.e., a single action that can be performed in different ways. So, polymorphism means many forms.

Polymorphism is of two types:

-   Static polymorphism
    
-   Dynamic polymorphism

![[Pasted image 20230106094658.png]]

## Static Polymorphism 

Polymorphism that gets resolved during compile time is known as **static polymorphism** or **compile time polymorphism**. This polymorphism is achieved using overloading of the methods in the same class, called as **Method overloading**.

### Method Overloading

Method overloading allows the programmer to have multiple methods with the same name in the same class, but differing in their signature.

Signature can differ by

-   the number of parameters
    
-   the data type of parameters
    
-   the order of the parameters
    

Note: We cannot overload methods by their return type, i.e., two or more methods are not overloaded if they differ only in their return type.

```java
class Demo {

	// Method 1
	// Multiplication of 2 numbers
	static int Multiply(int a, int b) {

		// Return product
		return a * b;
	}

	// Method 2
	static int Multiply(int a, int b, int c) {

		// Return product
		return a * b * c;
	}
}

public class Main {
	public static void main(String[] args) {

		System.out.println(Demo.Multiply(2, 4));
		System.out.println(Demo.Multiply(2, 7, 3));
	}
}

```

## Dynamic Polymorphism

**Dynamic polymorphism** is a process or mechanism in which a call to an overridden method is to resolve at runtime rather than compile-time. It is also known as [**runtime polymorphism**](https://www.javatpoint.com/runtime-polymorphism-in-java) or **dynamic method dispatch**. We can achieve dynamic polymorphism by using the [**method overriding**](https://www.javatpoint.com/method-overriding-in-java).

### Method Overriding

It provides a specific implementation to a method that is already present in the parent class. it is used to achieve run-time polymorphism. Remember that, it is not possible to override the **static** method. Hence, we cannot override the main() method also because it is a static method.

-   The name of the method must be the same as the name of the parent class method.
-   The number of parameters and the types of parameters must be the same as in the parent class.
-   There must exist an IS-A relationship (inheritance).

```java
public class Demo {
	public static void main(String args[]) {
		// assigning a child class object to a parent class reference
		Fruits fruits = new Mango();
		// invoking the method
		fruits.color();
	}
}

// parent class
class Fruits {
	public void color() {
		System.out.println("Parent class method is invoked.");
	}
}

// derived or child class that extends the parent class
class Mango extends Fruits {
	// overrides the color() method of the parent class
	@Override
	public void color() {
		System.out.println("The child class method is invoked.");
	}
}
```

> [!Output]
> The child class method is invoked.

