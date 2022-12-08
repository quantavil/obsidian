


**Identifier** : An identifier is a name given to entities like class, functions, variables, etc. Identifiers are *case-sensitive*
`temperature = 98.6`
This command establishes temperature as an identifier (also known as a name), and then associates it with the object expressed on the right-hand side of the equal sign, in this case a floating-point object with value 98.6

# Creating and Using Objects

## Instantiation  
The process of creating a new instance of a class is known as instantiation. In  general, the syntax for instantiating an object is to invoke the constructor of a class.  For example, if there were a class named Widget, we could create an instance of  that class using a syntax such as w = Widget( ), assuming that the constructor does  not require any parameters. If the constructor does require parameters, we might  use a syntax such as Widget(a, b, c) to construct a new instance

## Calling Methods  
Python supports traditional functions (see Section 1.5) that are invoked with a syn- tax such as sorted(data), in which case data is a parameter sent to the function. Python’s classes may also define one or more methods (also known as member functions), which are invoked on a specific instance of a class using the dot (“.”)  operator. For example, Python’s list class has a method named sort that can be invoked with a syntax such as data.sort( ). This particular method rearranges the contents of the list so that they are sorted.

When using a method of a class, it is important to understand its behavior. Some methods return information about the state of an object, but do not change that state. These are known as accessors. Other methods, such as the sort method of the list class, do change the state of an object. These methods are known as mutators or update methods

![[Pasted image 20221016215821.png]]