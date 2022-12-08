Inside a *Class*, we can define the following three types of methods.

-   **Instance methods**: Used to access or modify the object state. If we use *Instance variables* inside a method, such methods are called instance methods. It must have a `self` parameter to refer to the current object.
-   **Class methods**: Used to access or modify the class state. In method implementation, if we use only *class variables*, then such type of methods we should declare as a class method. The class method has a `cls` parameter which refers to the class.
- **Static method** : is a general utility method that performs a task in isolation. This method doesn’t have access to the instance and class variable.

![Python Class Method vs. Static Method vs. Instance Method](https://pynative.com/wp-content/uploads/2021/08/python_class_method_vs_static_method_vs_instance_method.png)

## What is Instance Methods in Python

If we use instance variables inside a method, such methods are called instance methods. **The instance method performs a set of actions on the data/value provided by the instance variables.**


![Instance method in Python](https://pynative.com/wp-content/uploads/2021/08/instance_method_in_python.png)



## Modify Instance Variables inside Instance Method

Let’s create the instance method `update()` method to modify the student age and roll number when student data details change.

**Output**:

```
class VIII
Roll Number: 20 Name: Emma Age: 14
class IX
Roll Number: 35 Name: Emma Age: 15
```



## Dynamically Add Instance Method to a Object

Usually, we add methods to a class body when defining a class. However, Python is a dynamic language that allows us to add or delete instance methods at runtime. 

-   When class is in a different file, and you don’t have access to modify the class structure
-   You wanted to extend the class functionality without changing its basic structure because many systems use the same structure.

```python
def func(obj):
  print 'I am called from', obj
class A:
  pass
a=A()
a.func=func
a.func()
```

This fails with a `TypeError`: `func() takes exactly 1 argument (0 given)`, whereas this code works as expected:

```python
import types
a.func = types.MethodType(func, a) # or types.MethodType(func, a, A) for PY2
a.func()
```

shows `I am called from <__main__.A instance at xxx>`.


## Dynamically Delete Instance Methods

-   By using the `del` operator
-   By using `delattr()` method

```python
class Student:
    # constructor
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def show(self):
        print('Name:', self.name, 'Age:', self.age)

    # instance method
    def percentage(self, sub1, sub2):
        print('Percentage:', (sub1 + sub2) / 2)

emma = Student('Emma', 14)
emma.show()
emma.percentage(67, 62)

# Delete the method from class using del operator
del emma.percentage

[[delete]] instance method show() using delattr()
delattr(emma, 'show') 

```

## What is Class Method in Python

Class methods are methods that are called on the *class* itself, not on a specific object instance. Therefore, it belongs to a class level, and all class instances share a class method.

-   **A class method is bound to the class** and not the object of the class. It can access only class variables.
-   It can modify the class state by changing the value of a *class variable* that would apply across all the class objects.

![define class method](https://pynative.com/wp-content/uploads/2021/08/class_method.png)

### Example 1: Create Class Method Using @classmethod Decorator

```python
from datetime import date

class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def calculate_age(cls, name, birth_year):
        # calculate age an set it as a age
        # return new object
        return cls(name, date.today().year - birth_year)

    def show(self):
        print(self.name + "'s age is: " + str(self.age))

jessa = Student('Jessa', 20)
jessa.show()

# create new object using the factory method
joy = Student.calculate_age("Joy", 1995)
print(joy.__dict__)
joy.show()
```

> Jessa's age is: 20
> {'name': 'Joy', 'age': 27}
> Joy's age is: 26

### Example 2: Create Class Method Using classmethod() function

```python
class School:
    # class variable
    name = 'ABC School'

    def school_name(cls):
        print('School Name is :', cls.name)

# create class method
School.school_name = classmethod(School.school_name)

# call class method
School.school_name()
```

> School Name is : ABC School

### Example 3: Access Class Variables in Class Methods
```python
class Student:
    school_name = 'ABC School'

    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def change_school(cls, school_name):
        # class_name.class_variable
        cls.school_name = school_name

    # instance method
    def show(self):
        print(self.name, self.age, 'School:', Student.school_name)

jessa = Student('Jessa', 20)
jessa.show()

# change school_name
Student.change_school('XYZ School')
jessa.show()
```

> Jessa 20 School: ABC School  
> Jessa 20 School: XYZ School

## Dynamically Add Class Method to a Class

```python
class Student:
    school_name = 'ABC School'

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show(self):
        print(self.name, self.age)

# class ended

# method outside class
def exercises(cls):
    # access class variables
    print("Below exercises for", cls.school_name)

# Adding class method at runtime to class
Student.exercises = classmethod(exercises)

jessa = Student("Jessa", 14)
jessa.show()
# call the new method
Student.exercises()
```

> Jessa 14
> Below exercises for ABC School

## Dynamically Delete Class Methods

```python
class Student:
    school_name = 'ABC School'

    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def change_school(cls, school_name):
        cls.school_name = school_name

jessa = Student('Jessa', 20)


# delete class method
del Student.change_school

# delete class method
delattr(Student, 'change_school')
```

## What is Static Methods in Python

A static method is a general utility method that performs a task in isolation. Inside this method, we don’t use instance or class variable because this static method doesn’t take any parameters like `self` and `cls`.

```python
class Employee:
    @staticmethod
    def sample(x):
        print('Inside static method', x)

# call static method
Employee.sample(10)

# can be called using object
emp = Employee()
emp.sample(10)
```

>Inside static method 10
>Inside static method 10

**Advantages : **  
- Consume Less memory
- To Write Utility functions

## The `staticmethod()` function

```python
class Employee:
    def sample(x):
        print('Inside static method', x)

# convert to static method
Employee.sample = staticmethod(Employee.sample)
# call static method
Employee.sample(10)
```

