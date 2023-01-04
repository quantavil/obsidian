Strings behave a bit differently when a new instance of String class is created. When you create a string using the new() keyword, JVM places the literal in the constant pool and also creates a new string object in heap memory. The reference variable points to the object in the heap memory.

![[Pasted image 20230103234230.png]]

## Array

An **array** is a collection of values of the same data type, stored in contiguous memory locations and referred by the same name. It holds a fixed number of values, decided at the time of array declaration.

In order to use array in Java, you need to declare an array along with a datatype. You can declare, create and initialize an array in the following ways:

-   **Declaring and initializing the array in one line:**

Syntax:
```java
dataType[ ] arrayVarName = {elementsOfArraySeparatedByComma};
```

```java
long[ ] restaurantContacts = { 9992346725L, 9992346726L, 9992346727L };
```

-   **Creating the array using new:** 
    

Syntax:

```java
dataType[ ] arrayVarName = new dataType[size];
arrayVarName[index] = element;

```

```java
long[ ] restaurantContacts = new long [3]; // Creating an array of size 3 of long datatype
restaurantContacts [0] = 9992346725L;
restaurantContacts [1] = 9992346726L;
restaurantContacts [2] = 9992346727L;

```


-   **Declaring and creating the array in different lines:** 

Syntax:

```java
dataType [] arrayVarName;
arrayVarName = new dataType[size];
arrayVarName[index] = element;

```

```java
long[] restaurantContacts;
restaurantContacts = new long[3];
restaurantContacts[0] = 9992346725L;
restaurantContacts[1] = 9992346726L;
restaurantContacts[2] = 9992346727L;

```
### Accessing array using loop

- **Using For Loop**
```java
public class Tester {
	public static void main(String[] args) {
		long[] restaurantContacts = { 9992346725L, 9992346726L, 9992346727L };
		for (int index = 0; index < restaurantContacts.length; index++) {
			// Accessing element at position index
			System.out.println(restaurantContacts[index]);
		}
	}
}

```

- **Using For Each loop**

```java
for (dataType variable: array) { 
	//body of the loop 
} 
```

```java
public class Tester {
	public static void main(String[] args) {
		long[] restaurantContacts = { 9992346725L, 9992346726L, 9992346727L };
		for (long contactNumber : restaurantContacts) {
			System.out.println(contactNumber);
		}
	}
}
```