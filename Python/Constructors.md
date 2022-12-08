A constructor is a special method used to create and initialize an object of a class.

In Python, Object creation is divided into two parts in **Object Creation** and **Object initialization**
-   Internally, the `__new__` is the method that creates the object
-   And, using the `__init__()` method we can implement constructor to initialize the object.

```python
def __init__(self):
    # body of the constructor
```

Where,

-   `def`: The keyword is used to define function.
-   `__init__()` Method: It is a reserved method. This method gets called as soon as an object of a class is instantiated.
-   `self`: The first argument `self` refers to the current object. It binds the instance to the `__init__()` method. It’s usually named `self` to follow the naming convention.


```python
class Student:

    # constructor
    # initialize instance variable
    def __init__(self, name):
        print('Inside Constructor')
        self.name = name
        print('All variables initialized')

    # instance Method
    def show(self):
        print('Hello, my name is', self.name)
```

![](https://pynative.com/wp-content/uploads/2021/07/python_constructor_create_object.png)

## Types of Constructor
![](https://pynative.com/wp-content/uploads/2021/07/types_of_constructor.png)

### Default Constructor 
```python
class Employee:

    def display(self):
        print('Inside Display')

emp = Employee()
emp.display()
```


As you can see in the example, we do not have a constructor, but we can still create an object for the class because Python added the default constructor during a program compilation.

### Non-Parametrized Constructor

A constructor without any arguments is called a non-parameterized constructor. This type of constructor is used to initialize each object with default values.

```python
class Company:

    # no-argument constructor
    def __init__(self):
```


### Parameterized Constructor
A constructor with defined parameters or arguments is called a parameterized constructor. We can pass different values to each object at the time of creation using a parameterized constructor.

```python
class Employee:
    # parameterized constructor
    def __init__(self, name, age, salary):
```


## Constructor With Default Values

```python
class Student:
    # constructor with default values age and classroom
    def __init__(self, name, age=12, classroom=7):
```

## Self keyword 

`self` is a self-referencing pointer. It is **necessary** to pass `self` as a parameter if the method is inside a class. This is because when an object calls a method, Python automatically passes the object as the first argument to the method.

![](https://www.codesdope.com/pa-images-bucket/courses/python/co2.jpg)

> sq.description() is equivalent to Square.description(sq)

So, if we do not write `self` as a parameter, we will get an error. Try removing `self` and see the error.

![](https://www.codesdope.com/pa-images-bucket/courses/python/co3.jpg)


## Constructor Overloading

Constructor overloading is a concept of having more than one constructor with a different parameters list in such a way so that each constructor can perform different tasks.

**Python does not support constructor overloading**. If we define multiple constructors then, the interpreter will considers only the last constructor and throws an error if the sequence of the arguments doesn’t match as per the last constructor.

## Constructor Chaining

Constructor chaining is the process of calling one constructor from another constructor.
Using the `super()` method we can invoke the parent class constructor from a child class.

```python
class Vehicle:
    # Constructor of Vehicle
    def __init__(self, engine):
        print('Inside Vehicle Constructor')
        self.engine = engine

class Car(Vehicle):
    # Constructor of Car
    def __init__(self, engine, max_speed):
        super().__init__(engine) # < == > Employee.__init__(self, name, xp, salary)
        print('Inside Car Constructor')
        self.max_speed = max_speed

class Electric_Car(Car):
    # Constructor of Electric Car
    def __init__(self, engine, max_speed, km_range):
        super().__init__(engine, max_speed)
        print('Inside Electric Car Constructor')
        self.km_range = km_range

# Object of electric car
ev = Electric_Car('1500cc', 240, 750)
print(f'Engine={ev.engine}, Max Speed={ev.max_speed}, Km range={ev.km_range}')

```

>Inside Vehicle Constructor
>Inside Car Constructor
>Inside Electric Car Constructor
>
>Engine=1500cc, Max Speed=240, Km range=750

## Counting the Number of objects of a Class

```python
class Employee:
    count = 0
    def __init__(self):
        Employee.count = Employee.count + 1


# creating objects
e1 = Employee()
e2 = Employee()
e2 = Employee()
print("The number of Employee:", Employee.count)

```
>The number of employee: 3

## Constructor Return Value

In Python, the constructor does not return any value. Therefore, while declaring a constructor, we don’t have anything like return type. Instead, a constructor is implicitly called at the time of object instantiation. Thus, it has the sole purpose of initializing the instance variables.

The `__init__()` is required to return None. We can not return something else. If we try to return a non-None value from the `__init__()` method, it will raise TypeError.

**Example**

```python
class Test:

    def __init__(self, i):
        self.id = i
        return True

d = Test(10)
```

> TypeError: __init__() should return None, not 'bool'

## Destructor

**Destructor is a special method that is called when an object gets destroyed.** In Python, The special method `__del__()` is used to define a destructor. For example, when we execute `del object_name` destructor gets called automatically and the object gets garbage collected.

![](https://pynative.com/wp-content/uploads/2021/07/python_destructor_to_destroy_object.png)

**Syntax of destructor declaration**
```python
def __del__(self):
    # body of a destructor
```


```python
class Student:

    # constructor
    def __init__(self, name):
        print('Inside Constructor')
        self.name = name
        print('Object initialized')

    def show(self):
        print('Hello, my name is', self.name)

    # destructor
    def __del__(self):
        print('Inside destructor')
        print('Object destroyed')

# create object
s1 = Student('Emma')
s1.show()

# delete object
del s1

```

>Inside Constructor
>Object initialized
>Hello, my name is Emma
>Inside destructor
>Object destroyed



![](https://pynative.com/wp-content/uploads/2021/07/working_of_destructor.png)


---
# RECAP:
-   A constructor is a unique method used to initialize an object of the class.
-   Python will provide a default constructor if no constructor is defined.
-   Constructor is not a method and doesn’t return anything. it returns None
-   In Python, we have three types of constructor default, Non-parametrized, and parameterized constructor.
-   Using self, we can access the instance variable and instance method of the object. The first argument self refers to the current object.
-   Constructor overloading is not possible in Python.
-   If the parent class doesn’t have a default constructor, then the compiler would not insert a default constructor in the child class.
-   A child class constructor can also invoke the parent class constructor using the `super()` method.
-  In object-oriented programming, A destructor is called when an object is deleted or destroyed.
-   Destructor is used to perform the clean-up activity before destroying the object, such as closing database connections or file handle.
-   In Python we use `__del__()` method to perform clean-up task before deleting the object.
-   The destructor will not invoke when we delete object reference. It will only invoke when all references to the objects get deleted.