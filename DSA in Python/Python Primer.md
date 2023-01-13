


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

### The bool Class

The bool class is used to manipulate logical (Boolean) values, and the only two instances of that class are expressed as the literals True and False.

### The int Class

Typical literals for integers include 0, 137, and −23. 
You can express an integral value using binary, octal, or hexadecimal. That can be done by using a prefix of the number .
0b1011 --> 0b is binary
0o52 --> 0o is octal
0x7f --> 0x is Hexadecimal

The integer constructor int() returns
```python
default --> 0
int(3.14) --> 3
int(-3.9) --> 3
int('137') --> 137
int('hello') --> Error: ValueError
```

### The float Class

The float class is the sole floating-point type in Python, using a fixed-precision representation

```python
float(2) --> 2.0
float('3.14') --> Error: ValueError
```

### Sequence Types: The list, tuple, and str Classes

#### The list Class
A list instance stores a sequence of objects. A list is a referential structure, as it technically stores a sequence of references to its element. Elements of a list may be arbitrary objects (including the None object). Lists are array-based sequences and are zero-indexed, thus a list of length n has elements indexed from 0 to n−1 inclusive.

Python uses the characters [ ] as delimiters for a list literal, with [ ] itself being an empty list

```python
list( 'hello' ) --> ['h' , 'e' , 'l' , 'l' , 'o' ]
```

#### The tuple Class
The tuple class provides an immutable version of a sequence, and therefore its instances have an internal representation that may be more streamlined than that of a list. 

```python
# Syntax
()
(14,)
(14)
```

#### The str Class 
Python’s str class is specifically designed to efficiently represent an immutable sequence of characters, based upon the Unicode international character set.

```python
# Syntax
print("hello") --> hello
print('hello') --> hello
print('Don\'t worry') --> Don't worry # \ is escape character
print('C:\\Python\\') --> C:\Python\

\n --> newline
\t --> newtab

```


```python
# ''' or """ is Delimiter The advantage of such triple-quoted strings is that newline characters can be embedded naturally (rather than escaped as \n). or for multiline String

print('''Welcome to the GPA calculator.
Please enter all your letter grades', one \tper line.
Enter a blank line to designate the end.''')
```

```output
Welcome to the GPA calculator.
Please enter all your letter grades', one       per line.
Enter a blank line to designate the end.
```

#### The set and frozenset Classes

This is based on a data structure known as a hash table 
The first is that the set does not maintain the elements in any particular order. The second is that only instances of immutable types can be added to a Python set.
Therefore, objects such as integers, floating-point numbers, and character strings are eligible to be elements of a set. It is possible to maintain a set of tuples, but not a set of lists or a set of sets, as lists and sets are mutable. The frozenset class is an immutable form of the set type, so it is legal to have a set of frozensets.

```python
{1,4,5};
set('hello') --> {'h','e','l','o'}
```

#### The dict Class

Python’s dict class represents a dictionary, or mapping, from a set of distinct keys to associated values.

```python
{ 'ga' : 'Irish' , 'de' : 'German' }

# Alternatively, the constructor accepts a sequence of key-value pairs as a parameter, as in dict(pairs)
pairs = [( 'ga' , 'Irish' ), ( 'de' , 'German' )]
dict(pairs) --> { 'ga' : 'Irish' , 'de' : 'German' }
```
