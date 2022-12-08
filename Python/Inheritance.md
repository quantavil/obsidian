The **process of inheriting the properties of the parent class into a child class is called inheritance**.
The existing class is called a base class or parent class and the new class is called a subclass or child class or derived class.

**Syntax**

```python
class BaseClass:
  Body of base class
class DerivedClass(BaseClass):
  Body of derived class
```

## Types Of Inheritance

In Python, based upon the number of child and parent classes involved, there are five types of inheritance. The type of inheritance are listed below:

1.  Single inheritance
2.  Multiple Inheritance
3.  Multilevel inheritance
4.  Hierarchical Inheritance
5.  Hybrid Inheritance

## Single Inheritance

In single inheritance, a child class inherits from a single-parent class. Here is one child class and one parent class.

![](https://pynative.com/wp-content/uploads/2021/03/python_single_inheritance.png)

```python
# Base class
class Vehicle:
    def Vehicle_info(self):
        print('Inside Vehicle class')

# Child class
class Car(Vehicle):
    def car_info(self):
        print('Inside Car class')

# Create object of Car
car = Car()

# access Vehicle's info using car object
car.Vehicle_info()
car.car_info()
```

>Inside Vehicle class
>Inside Car class


## Multiple Inheritance

In multiple inheritance, one child class can inherit from multiple parent classes. So here is one child class and multiple parent classes.

![Python Multiple Inheritance](https://pynative.com/wp-content/uploads/2021/03/python_multiple_inheritance.png)

```python
# Parent class 1
class Person:
    def person_info(self, name, age):

# Parent class 2
class Company:
    def company_info(self, company_name, location):

# Child class
class Employee(Person, Company):
    def Employee_info(self, salary, skill):

```


## Multilevel inheritance

In multilevel inheritance, a class inherits from a child class or derived class. Suppose three classes A, B, C. A is the superclass, B is the child class of A, C is the child class of B. In other words, we can say a **chain of classes** is **called multilevel inheritance.**

![Python Multilevel Inheritance](https://pynative.com/wp-content/uploads/2021/03/python_multilevel_inheritance.png)


```python
# Base class
class Vehicle:
    def Vehicle_info(self):
        print('Inside Vehicle class')

# Child class
class Car(Vehicle):
    def car_info(self):
        print('Inside Car class')

# Child class
class SportsCar(Car):
    def sports_car_info(self):
        print('Inside SportsCar class')

# Create object of SportsCar
s_car = SportsCar()

# access Vehicle's and Car info using SportsCar object
s_car.Vehicle_info()
s_car.car_info()
s_car.sports_car_info()

```
**Output**

>Inside Vehicle class
>Inside Car class
>Inside SportsCar class


## Hierarchical Inheritance

In Hierarchical inheritance, more than one child class is derived from a single parent class. In other words, we can say one parent class and multiple child classes.

![Python hierarchical inheritance](https://pynative.com/wp-content/uploads/2021/03/python_hierarchical_inheritance.png)

```python
class Vehicle:
    def info(self):
        print("This is Vehicle")

class Car(Vehicle):
    def car_info(self, name):
        print("Car name is:", name)

class Truck(Vehicle):
    def truck_info(self, name):
        print("Truck name is:", name)

obj1 = Car()
obj1.info()
obj1.car_info('BMW')

obj2 = Truck()
obj2.info()
obj2.truck_info('Ford')
```

**Output**

```
This is Vehicle
Car name is: BMW

This is Vehicle
Truck name is: Ford
```

## Hybrid Inheritance

When inheritance is consists of multiple types or a combination of different inheritance is called hybrid inheritance.

![Python hybrid inheritance](https://pynative.com/wp-content/uploads/2021/03/python_hybrid_inheritance.png)


```python
class Vehicle:
    def vehicle_info(self):

class Car(Vehicle):
    def car_info(self):

class Truck(Vehicle):
    def truck_info(self):

# Sports Car can inherits properties of Vehicle and Car
class SportsCar(Car, Vehicle):
    def sports_car_info(self):
```

## Python `super()` function

In child class, we can refer to parent class by using the `super()` function. The super function returns a temporary object of the parent class that allows us to call a parent class method inside a child class method.

**Benefits of using the `super()` function.**

1.  We are not required to remember or specify the parent `class` name to access its methods.
2.  We can use the `super()` function in both **single** and **multiple inheritances**.
3.  The `super()` function support code **reusability** as there is no need to write the entire function

```python
class Company:
    def company_name(self):
        return 'Google'

class Employee(Company):
    def info(self):
        # Calling the superclass method using super()function
        c_name = super().company_name()
        print("Jessa works at", c_name)

# Creating object of child class
emp = Employee()
emp.info()
```

> Jessa works at Google

## issubclass() 

To verify whether a particular class is a subclass of another class. 

**Syntax**
`issubclass(class, classinfo)`
Where,

-   `class`: class to be checked.
-   `classinfo`: a `class`, type, or a `tuple` of classes or data types.

## Method Overriding

In inheritance, all members available in the parent class are by default available in the child class. If the child class does not satisfy with parent class implementation, then the child class is allowed to redefine that method by extending additional functions in the child class. This concept is called **method overriding**.

![Python method overriding](https://pynative.com/wp-content/uploads/2021/03/python_method_overriding.png)

```python
class Vehicle:
    def max_speed(self):
        print("max speed is 100 Km/Hour")

class Car(Vehicle):
    # overridden the implementation of Vehicle class
    def max_speed(self):
        print("max speed is 200 Km/Hour")

# Creating object of Car class
car = Car()
car.max_speed()
```

> max speed is 200 Km/Hour


## Method Resolution Order in Python

In Python, Method Resolution Order(MRO) is the order by which **Python looks for a method or attribute**. First, the method or attribute is searched within a class, and then it follows the order we specified while inheriting. 
```python
class A:
    def process(self):
        print(" In class A")

class B(A):
    def process(self):
        print(" In class B")

class C(B, A): # class C(A,B) is error # As B is already inherited A  therefore python is confuse between original A method and the A method inherited by the B
    def process(self): 
        print(" In class C")

# Creating object of C class
C1 = C()
C1.process()
print(C.mro())
# In class C
# [<class '__main__.C'>, <class '__main__.B'>, <class '__main__.A'>, <class 'object'>]
```

In the above example, we create three classes named `A`, `B` and `C`. Class `B` is inherited from `A`, class `C` inherits from `B` and `A`. When we create an object of the `C` class and calling the `process()` method, Python looks for the `process()` method in the current class in the `C` class itself.

Then search for parent classes, namely `B` and `A`, because `C` class inherit from `B` and `A`. that is, `C(B, A)` and always search in **left to right manner.**
[More Info](https://stackoverflow.com/questions/29214888/typeerror-cannot-create-a-consistent-method-resolution-order-mro)