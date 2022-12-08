There are several kinds of variables in Python:

-   **Instance variables** in a class: these are called fields or attributes of an object
-   **Local Variables**: *Variables* in a method or block of code
-   **Parameters**: Variables in *method* declarations
-   **Class variables**: This variable is shared between all objects of a class

## What is an Instance Variable in Python?

**If the value of a variable varies from *object* to object, then such variables are called instance variables**. For every object, a separate copy of the instance variable will be created.

![Declare Instance variable in Python](https://pynative.com/wp-content/uploads/2021/07/create_declare_instance_variable.png)

Instance variables are declared inside a method using the `self` keyword. We use a constructor  to define and initialize the instance variables. 
```python
class Student:
    # constructor
    def __init__(self, name, age):
        # Instance variable
        self.name = name
        self.age = age
	# instance method access instance variable 
    def show(self):
        print('Name:', stud.name, 'Age:', self.age) # Within the class in instance method by using the object reference (self)
	
# create object
stud = Student("Jessa", 20)

print('Before')
[[accessing]] instance variable
print('Name:', stud.name, 'Age:', stud.age)

# modify instance variable
stud.name = 'Emma'
stud.age = 15

print("After")
# call instance method 
stud.show()

# accessing instance variable using getattr() i.e. getattr(Object, 'instance_variable')
print('Name:', getattr(stud, 'name'))

```


>Before
>Name: Jessa Age: 20
>After
>Name: Emma Age: 15
>Name: Emma


![instance variables and methods](https://pynative.com/wp-content/uploads/2021/03/instance_variables_and_methods.png)


## Dynamically Add Instance Variable to a Object

We can add instance variables from the outside of class to a particular object. 

**Syntax**
`object_referance.variable_name = value`

```python
class Student:
    def __init__(self, name, age):
        # Instance variable
        self.name = name
        self.age = age

# create object
stud = Student("Jessa", 20)

print('Before')
print('Name:', stud.name, 'Age:', stud.age)

# add new instance variable 'marks' to stud
stud.marks = 75
print('After')
print('Name:', stud.name, 'Age:', stud.age, 'Marks:', stud.marks)

```


>Before
>Name: Jessa Age: 20
>
>After
>Name: Jessa Age: 20 Marks: 75


**Note**:

-   We cannot add an instance variable to a class from outside because instance variables belong to objects.
-   **Adding an instance variable to one object will not be reflected the remaining objects** because every object has a separate copy of the instance variable.

## Dynamically Delete Instance Variable

In Python, we use the `del` statement and `delattr()` function to delete the attribute of an object. Both of them do the same thing.

-   `del` statement: The `del` keyword is used to delete objects. In Python, everything is an object, so the `del` keyword can also be used to delete variables, lists, or parts of a list, etc.
-   `delattr()` function: Used to delete an instance variable dynamically.

```python
class Student:
    def __init__(self, roll_no, name):
        # Instance variable
        self.roll_no = roll_no
        self.name = name
    def show(self):
        print(self.roll_no, self.name)

# create object
s1 = Student(10, 'Jessa')
s1.show()

# del name
del s1.name
# Try to access name variable
print(s1.name)

s2 = Student(27, 'Marco')
s2.show()

# delete instance variable using delattr()
delattr(s2, 'roll_no')
s2.show()
```

>10 Jessa
>AttributeError: 'Student' object has no attribute 'name'
>27 Marco
>AttributeError: 'Student' object has no attribute 'roll_no'



## Access Instance Variable From Another Class

We can access instance variables of one class from another class using object reference. It is useful when we implement the concept of [[Inheritance]], and we want to access the parent class instance variable from a child class.

## List all Instance Variables of a Object

We can get the list of all the instance variables the object has. Use the `__dict__` function of an object to get all instance variables along with their value.

```python
class Student:
    def __init__(self, roll_no, name):
        # Instance variable
        self.roll_no = roll_no
        self.name = name

s1 = Student(10, 'Jessa')
print('Instance variable object has')
print(s1.__dict__)

# Get each instance variable
for key_value in s1.__dict__.items():
    print(key_value[0], '=', key_value[1])

```

>Instance variable object has
>{'roll_no': 10, 'name': 'Jessa'}
>
>roll_no = 10
>name = Jessa


## What is an Class Variable in Python?

If the **value of a *variable* is not varied from object to object**, such types of variables are called class variables or static variables.
Class variables are **shared by all instances of a class**. Unlike instance variable, the value of a class variable is not varied from object to object.
![](https://pynative.com/wp-content/uploads/2021/07/create_and_access_class_variable.png)

```python
class Student:
    # Class variable
    school_name = 'ABC School '

    # constructor
    def __init__(self, name, roll_no):
        self.name = name
        self.roll_no = roll_no

    # Instance method
    def show(self):
        print(self.name, self.roll_no, Student.school_name)

# create Object
s1 = Student('Emma', 10)
print('Before')
s1.show()

# Accesing Class Variable
print(s1.school_name)
# Modify class variable
Student.school_name = 'XYZ School'
print('After')
s1.show()
```


## Class Variable vs Instance variables

| Instance Variable | Class Variable |
| --- | --- |
| Instance variables are not shared by objects. Every object has its own copy of the instance attribute | Class variables are shared by all instances.|
| Instance variables are declared inside the constructor i.e., the `__init__()` method. | Class variables are declared inside the class definition but outside any of the instance methods and constructors. |
| It is gets created when an instance of the class is created. | It is created when the program begins to execute. |
