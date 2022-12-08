- [[#Why Use Java?|Why Use Java?]]
- [[#How Does Java Programming Language Work?|How Does Java Programming Language Work?]]
- [[#Execution Process of Java Program|Execution Process of Java Program]]
	- [[#Execution Process of Java Program#JIT compiler.|JIT compiler.]]
- [[#What are the differences between C++ and Java?|What are the differences between C++ and Java?]]
- [[#JAVA Terminology|JAVA Terminology]]
	- [[#JAVA Terminology#What are the differences between JVM, JRE and JDK in Java?|What are the differences between JVM, JRE and JDK in Java?]]
	- [[#JAVA Terminology#Garbage Collector|Garbage Collector]]
	- [[#JAVA Terminology#Class Path|Class Path]]
- [[#Main Features Of Java|Main Features Of Java]]
	- [[#Main Features Of Java#Java Applications|Java Applications]]
- [[#Simple Program in Java|Simple Program in Java]]
- [[#Conclusion|Conclusion]]

Java is a class-based object-oriented simple programming language. Though we can not consider it to be fully object-oriented as it supports primitive datatypes. It is a general-purpose, high-level programming language that helps programmers and developers to write a code once and run it anywhere.

**Java is considered both a compiled and interpreted language.** It is because Java source code is first compiled to bytecode which is then interpreted by Java Virtual Machine. Java Virtual Machine interprets the bytecode and converts it to platform specific machine code. Hence, Java is also called a platform-independent programming language.

Java is a programming language that James Gosling developed at Sun Microsystems_Inc in the year 1995, which later on was taken into possession by the Oracle Corporation in 2009.

-   We can call it a high-level (makes the development of programs easy and much more user-friendly) programming language which makes it very convenient for us to write, compile and debug Java programs.
-   Java is a class-based object-oriented programming language that implements the principle of _write once code anywhere_.
-   Since Java applications are compiled to byte-code, they can run on any JVM-supported machine.
-   Java codes are very similar to C/C++, which makes them easier to understand.

## Why Use Java?

1. Object-Oriented
2. Portable
3. Simple
4. Secure
5. Robust
6. Platform Independent
7. Architecture neutral

## How Does Java Programming Language Work?

![How Does Java Programming Language Work](https://scaler.com/topics/images/how-does-java-programming-language-work.webp)


## Execution Process of Java Program

1.  **Creation of a Java Program** - Creating Java program with .java extension.

2.  **Compiling a Java Program**-

First, the source ‘.java’ file is passed through the compiler, which then encodes the source code into a machine-independent encoding, known as Bytecode

![Compiling a Java program](https://scaler.com/topics/images/compiling-a-java-program.webp)



```ad-faq
While converting the source code into the bytecode, the compiler follows the following steps:

**Step 1: Parse**: Reads a set of *.java* source files and maps the resulting token sequence into AST (Abstract Syntax Tree)-Nodes.
**Step 2: Enter**: Enters symbols for the definitions into the symbol table.
**Step 3: Process annotations:** If Requested, processes annotations found in the specified compilation units.
**Step 4: Attribute**: Attributes the Syntax trees. This step includes name resolution, type checking and constant folding.
**Step 5: Flow**: Performs dataflow analysis on the trees from the previous step. This includes checks for assignments and reachability.
**Step 6: Desugar**: Rewrites the AST and translates away some syntactic sugar.
**Step 7: Generate**: Generates ‘.Class’ files. 

```

3. **Loading the Program into the Memory by Java Virtual Machine**- A lot of memory is required by JVM when you want to load the .class file extension before the execution. The task of ClassLoader is to load the required classes and interfaces to the JVM when required.
![Loading the program](https://scaler.com/topics/images/loading-the-program.webp)

4.  **Java Virtual Machine verification for bytecode**- 
After the bytecode of a class is loaded by the class loader, it has to be inspected by the bytecode verifier, whose job is to check that the instructions don’t perform damaging actions.

```ad-faq
The following are some of the checks carried out: 

-   Variables are initialized before they are used.
-   Method calls match the types of object references.
-   Rules for accessing private data and methods are not violated.
-   Local variable accesses fall within the runtime stack.
-   The run-time stack does not overflow.
-   If any of the above checks fail, the verifier doesn’t allow the class to be loaded.
```

5.  **Java Program Execution**-
This is the final stage encountered by the java program, and its job is to convert the loaded bytecode into machine code , it is done by JIT

###  JIT compiler.

-   JIT stands for Just-In-Time and it is used for improving the performance during run time. It does the task of compiling parts of byte code having similar functionality at the same time thereby reducing the amount of compilation time for the code to run.

-   The compiler is nothing but a translator of source code to machine-executable code. But what is special about the JIT compiler? Let us see how it works:
    -   First, the Java source code (.java) conversion to byte code (.class) occurs with the help of the javac compiler.
    -   Then, the .class files are loaded at run time by JVM and with the help of an interpreter, these are converted to machine understandable code.
    -   JIT compiler is a part of JVM. When the JIT compiler is enabled, the JVM analyzes the method calls in the .class files and compiles them to get more efficient and native code. It also ensures that the prioritized method calls are optimized.
    -   Once the above step is done, the JVM executes the optimized code directly instead of interpreting the code again. This increases the performance and speed of the execution.

![[java.jpg]]

## What are the differences between C++ and Java?

| Comparison Index | C++ | Java |
| --- | --- | --- |
| **Platform-independent** | C++ is platform-dependent. | Java is platform-independent. |
| **Mainly used for** | C++ is mainly used for system programming. | Java is mainly used for application programming. It is widely used in window, web-based, enterprise and mobile applications. |
| **Design Goal** | C++ was designed for systems and applications programming. It was an extension of [C programming language](https://www.javatpoint.com/corejava-interview-questionsc-programming-language-tutorial). | Java was designed and created as an interpreter for printing systems but later extended as a support network computing. It was designed with a goal of being easy to use and accessible to a broader audience. |
| **Goto** | C++ supports the [goto](https://www.javatpoint.com/corejava-interview-questionscpp-goto-statement) statement. | Java doesn't support the goto statement. |
| **Multiple inheritance** | C++ supports multiple inheritance. | Java doesn't support multiple inheritance through class. It can be achieved by [interfaces in java](https://www.javatpoint.com/corejava-interview-questionsinterface-in-java). |
| **Operator Overloading** | C++ supports [operator overloading](https://www.javatpoint.com/corejava-interview-questionscpp-overloading). | Java doesn't support operator overloading. |
| **Pointers** | C++ supports [pointers](https://www.javatpoint.com/corejava-interview-questionscpp-pointers). You can write pointer program in C++. | Java supports pointer internally. However, you can't write the pointer program in java. It means java has restricted pointer support in Java. |
| **Compiler and Interpreter** | C++ uses compiler only. C++ is compiled and run using the compiler which converts source code into machine code so, C++ is platform dependent. | Java uses compiler and interpreter both. Java source code is converted into bytecode at compilation time. The interpreter executes this bytecode at runtime and produces output. Java is interpreted that is why it is platform independent. |
| **Call by Value and Call by reference** | C++ supports both call by value and call by reference. | Java supports call by value only. There is no call by reference in java. |
| **Structure and Union** | C++ supports structures and unions. | Java doesn't support structures and unions. |
| **Virtual Keyword** | C++ supports virtual keyword so that we can decide whether or not override a function. | Java has no virtual keyword. We can override all non-static methods by default. In other words, non-static methods are virtual by default. |
| **Hardware** | C++ is nearer to hardware. | Java is not so interactive with hardware. |

## JAVA Terminology

![Bytecode in the Development process](https://scaler.com/topics/images/bytecode-in-the-development-process.webp)

-   **JDK**- For making java programs, we need some tools that are provided by JDK (Java Development Kit). JDK is the package that contains various tools, Compiler, Java Runtime Environment, etc.
-   **JRE** -  To execute the java program we need an environment. (Java Runtime Environment) JRE contains a library of Java classes +  JVM. **What are JAVA Classes?**  It contains some predefined methods that help Java programs to use that feature, build and execute. _**For example**_ - there is a system class in java that contains the print-stream method, and with the help of this, we can print something on the console.
-   **JVM** - (Java Virtual Machine) JVM  is a part of JRE that executes the Java program at the end.  Actually, it is part of JRE, but it is software that converts bytecode (.class file) into machine-executable code to execute on hardware.


### What are the differences between JVM, JRE and JDK in Java?

| Criteria | JDK  | JRE | JVM |
| --- | --- | --- | --- |
| Abbreviation | Java Development Kit | Java Runtime Environment | Java Virtual Machine |
| Definition | JDK is a complete software development kit for developing Java applications. It comprises JRE, JavaDoc, compiler, debuggers, etc. | JRE is a software package providing Java class libraries, JVM and all the required components to run the Java applications. | JVM is a platform-dependent, abstract machine comprising of 3 specifications - document describing the JVM implementation requirements, computer program meeting the JVM requirements and instance object for executing the Java byte code and provide the runtime environment for execution. |
| Main Purpose | JDK is mainly used for code development and execution. | JRE is mainly used for environment creation to execute the code. | JVM provides specifications for all the implementations to JRE. |
| Tools provided | JDK provides tools like compiler, debuggers, etc for code development | JRE provides libraries and classes required by JVM to run the program. | JVM does not include any tools, but instead, it provides the specification for implementation. |
| Summary | JDK = (JRE) + Development tools | JRE = (JVM) + Libraries to execute the application | JVM = Runtime environment to execute Java byte code. |

### Garbage Collector

Within Java, the programmers cannot delete the objects. Hence, to delete or recollect a memory, JVM has a Garbage Collector. These Garbage Collectors can recollect those objects which have not been referenced.  
This ensures that the memory resource is used efficiently, but it provides no guarantee that there would be sufficient memory for the program execution.

### Class Path

Class path is a particular file path where both the Java runtime and Java compiler look for .class files to appear.


## Main Features Of Java

There are the following features in Java Programming Language.

-   **Simple:** Java is easy to learn. The syntax of Java is based on C++ which makes easier to write the program in it.
  
-   **Object-Oriented:** Java follows the object-oriented paradigm which allows us to maintain our code as the combination of different type of objects that incorporates both data and behavior.
  
-   **Portable:** Java supports read-once-write-anywhere approach. We can execute the Java program on every machine. Java program (.java) is converted to bytecode (.class) which can be easily run on every machine.
  
-   **Platform Independent:** Java is a platform independent programming language. It is different from other programming languages like C and C++ which needs a platform to be executed. Java comes with its platform on which its code is executed. Java doesn't depend upon the operating system to be executed.
  
-   **Secured:** Java is secured because it doesn't use explicit pointers. Java also provides the concept of ByteCode and Exception handling which makes it more secured.
  
-   **Robust:** Java is a strong programming language as it uses strong memory management. The concepts like Automatic garbage collection, Exception handling, etc. make it more robust.
  
-   **Architecture Neutral:** Java is architectural neutral as it is not dependent on the architecture. In C, the size of data types may vary according to the architecture (32 bit or 64 bit) which doesn't exist in Java.
  
-   **Interpreted:** Java uses the Just-in-time (JIT) interpreter along with the compiler for the program execution.

### Java Applications

-   **High Performance:** Java is faster than other traditional interpreted programming languages because Java bytecode is "close" to native code. It is still a little bit slower than a compiled language (e.g., C++).
  
-   **Multithreaded:** We can write Java programs that deal with many tasks at once by defining multiple threads. The main advantage of multi-threading is that it doesn't occupy memory for each thread. It shares a common memory area. Threads are important for multi-media, Web applications, etc.
  
-   **Distributed:** Java is distributed because it facilitates users to create distributed applications in Java. RMI and EJB are used for creating distributed applications. This feature of Java makes us able to access files by calling the methods from any machine on the internet.
  
-   **Dynamic:** Java is a dynamic language. It supports dynamic loading of classes. It means classes are loaded on demand. It also supports functions from its native languages, i.e., C and C++.

## Simple Program in Java

Let's have a deeper understanding of how a java program works.

```java
// Example program in java.

/* Here, we import classes 
from the packages. */
import java.io.*;

// This is the main class.
public class Main {

  // This is the main driver method.
  public static void main(String[] args) {
    // This is the standard print statement
    System.out.println("Welcome to ScalerTopics");
  }
}
```

**Output**

```java
Welcome to ScalerTopics
```

**Explanation**

**1. //** - This symbol in the code represents Comments in Java. 

```java
// I am a single-line comment.
/* I am a multi-line comment. */
```

**2. import java.io.**- Import is a keyword that includes the class we use in the code. This is used to import all the classes of the io package. Java's io package includes a set of input and output streams used to read or write files and input or output.

**3. public class**-The data and methods that need to be used in the program are included in the class. Methods define the behavior of the class.

**4. public static**-Static methods do not require objects to get called. They can be executed using the dot operator with the class name.

**5. void**- Does not return any value. It's an empty void.

**6. main()**- Name of the method. Entry point method where JVM runs the program.

**7. (String[ ] args)**- These are used as command-line arguments and are passed as strings.

**8. System.out.println**- This command prints the contents provided within the print statement.

## Conclusion

-   Java can be a class-based object-oriented programming language designed to minimize implementation dependencies as much as possible.
-   Java is a high-level, easily understandable language with syntax similar to C/C++.
-   Java is platform-independent, and this makes it better than any other programming language. Java implements the _write once run anywhere_ principle.
-   Java is a portable, simple, secure, and robust programming language well-suited for large codebases.
-   The JDK is a development environment for building applications, applets, and components using the Java programming language.
-   The JDK includes tools useful for developing and testing programs written in the Java programming language and running on the Java platform.
-   JRE is made up of multiple elements altogether, and they are: Java virtual machine (JVM), Java class libraries, and Java class loader.
-   Both JDK and JRE require JVM, which is specifically responsible for converting bytecode into machine-specific code.
-   JVM is platform-dependent; it carries out a variety of tasks, such as memory management. In addition, JVM may execute programs that have been converted to Java bytecode from other programming languages.
-   Garbage collector in Java is used to recollect those objects which can not be referenced anymore.
-   Classpath is a particular file path where both the Java runtime and Java compiler look for .class files to appear.
-   Java is used in Multithreaded, distributed, dynamic, and high-performance applications.




