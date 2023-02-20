**C++ supports the following data types:**

1.  **Primary** or **Built-in** or **Fundamental data type**
2.  **Derived data types**
3.  **User-defined data types**

![[Pasted image 20230220235313.png]]

## Primary Data Types

These data types are built-in or predefined data types and can be used directly by the user to declare variables

-   **Integer**: Integers typically require 4 bytes of memory space and range from - 2^32 to 2^32 -1.  
-   **Character**: Character data type is used for storing characters.  Characters typically require 1 byte of memory space and range from -128 to 127 or 0 to 255.  
-   **Boolean**: Boolean data type is used for storing Boolean or logical values. A Boolean variable can store either _true_ or _false_. 
-   **Floating Point**: Floating Point data type is used for storing single-precision floating-point values or decimal values. Float variables typically require 4 bytes of memory space. 
-   **Double Floating Point**: Double Floating Point data type is used for storing double-precision floating-point values or decimal values. Double variables typically require 8 bytes of memory space.
-  **void**: Void means without any value. void data type represents a valueless entity. A void data type is used for those function which does not return a value.
- -   **sizeof() operator:** [sizeof() operator](https://www.geeksforgeeks.org/sizeof-operator-c) is used to find the number of bytes occupied by a variable/data type in computer memory.

```ad-info
Range refers to the set of values that a variable or data type can hold or represent.
```

### Data Modifier

![[Pasted image 20230221000825.png]]


| Data Type | Data Modifier | Size (in bytes) | Range                                                           |
|-----------|---------------|----------------|-----------------------------------------------------------------|
| int       |               | 4              | -2^31 to (2^31)-1                                              |
| int       | signed        | 4              | -2^31 to (2^31)-1                                              |
| int       | unsigned      | 4              | 0 to (2^32)-1                                                   |
| int       | short         | 2              | -2^15 to (2^15)-1                                               |
| int       | long          | 4 or 8         | -2^31 to (2^31)-1 (4-byte) or -2^63 to (2^63)-1 (8-byte)          |
| float     |               | 4              | Approximately ±3.40282347 × 10^38 (6-7 significant digits)      |
| double    |               | 8              | Approximately ±1.7976931348623157 × 10^308 (15-16 significant digits) |
| char      |               | 1              | -2^7 to (2^7)-1 or 0 to (2^8)-1, depending on representation     |


1.  signed and unsigned: These modifiers are used to specify whether a data type should be able to store only positive values (unsigned) or both positive and negative values (signed).
    
2.  short and long: These modifiers are used to modify the size of the data type. For example, "short int" is a data type that can store smaller values than a regular "int", while "long int" can store larger values.
    
3.  const: This modifier is used to make a variable immutable, meaning its value cannot be changed once it has been assigned.