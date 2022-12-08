Polymorphism is the ability to exit in many forms. We can construct various classes to have methods with the same name while creating class methods.

### Polymorphism in Built-in function

- `len`

```python
students = ['Emma', 'Jessa', 'Kelly']
school = 'ABC School'

# calculate count
print(len(students))
print(len(school))
```

- `+`
```python
print(10+256)
print("Scaler"+"Academy")
```
- other examples `reversed` , `*`,
## Polymorphism With Inheritance

Polymorphism is mainly used with inheritance. In *inheritance*, child class inherits the attributes and methods of a parent class. The existing class is called a base class or parent class, and the new class is called a subclass or child class or derived class.

Using **method overriding** polymorphism allows us to defines methods in the child *class* that have the same name as the methods in the parent class. This **process of re-implementing the inherited method in the child class** is known as Method Overriding. It helps when we want to extend the functionality by altering the inherited method.

![](https://pynative.com/wp-content/uploads/2021/08/polymorphism_with_inheritance.jpg)

```python
class Vehicle:

    def __init__(self, name, color, price):
        self.name = name
        self.color = color
        self.price = price

    def show(self):
        print('Details:', self.name, self.color, self.price)

    def max_speed(self):
        print('Vehicle max speed is 150')

    def change_gear(self):
        print('Vehicle change 6 gear')


# inherit from vehicle class
class Car(Vehicle):
    def max_speed(self):
        print('Car max speed is 240')

    def change_gear(self):
        print('Car change 7 gear')


# Car Object
car = Car('Car x1', 'Red', 20000)
car.show()
# calls methods from Car class
car.max_speed()
car.change_gear()

# Vehicle Object
vehicle = Vehicle('Truck x1', 'white', 75000)
vehicle.show()
# calls method from a Vehicle class i.e. method overriding 
vehicle.max_speed()
vehicle.change_gear()
```

>Details: Car x1 Red 20000
>Car max speed is 240
>Car change 7 gear
>
>Details: Truck x1 white 75000
>Vehicle max speed is 150
>Vehicle change 6 gear

### Override Built-in Functions

Changing the default behavior of the built-in functions. For example, we can change or extend the built-in functions such as `len()`, `abs()`, or `divmod()` by redefining them in our class. Let’s see the example.

```python
class Shopping:
    def __init__(self, basket, buyer):
        self.basket = list(basket)
        self.buyer = buyer

    def __len__(self):
        print('Redefine length')
        count = len(self.basket)
        # count total items in a different way
        # pair of shoes and shir+pant
        return count * 2

shopping = Shopping(['Shoes', 'dress'], 'Jessa')
print(len(shopping))
```

>Redefine length
>4


## Polymorphism In Class methods

Polymorphism with class methods is useful when we group different objects having the same method. we can add them to a list or a tuple, and we don’t need to check the object type before calling their methods. Instead, Python will check object type at runtime and call the correct method.

```python
class Ferrari:
    def fuel_type(self):
        print("Petrol")

    def max_speed(self):
        print("Max speed 350")

class BMW:
    def fuel_type(self):
        print("Diesel")

    def max_speed(self):
        print("Max speed is 240")

ferrari = Ferrari()
bmw = BMW()

# iterate objects of same type
for car in (ferrari, bmw):
    # call methods without checking class of object
    car.fuel_type()
    car.max_speed()

print("######################################")
def car_details(obj): # creating  polymorphism with a function that can take any object as a parameter and execute its method without checking its class type
    obj.fuel_type()
    obj.max_speed()
    
car_details(ferrari)
car_details(bmw)
```

As you can see, we have created two classes Ferrari and BMW. They have the same instance method names `fuel_type()` and `max_speed()`. However, we have not linked both the classes nor have we used inheritance.

>Petrol
>Max speed 350
>Diesel
>Max speed is 240
>####################################
>Petrol
>Max speed 350
>Diesel
>Max speed is 240


## Method Overloading

The process of calling the same method with different parameters is known as method overloading. Python does not support method overloading. Python considers only the latest defined method even if you overload the method.

```python
def addition(a, b):
    c = a + b
    print(c)


def addition(a, b, c):
    d = a + b + c
    print(d)


# the below line shows an error
# addition(4, 5)

# This line will call the second product method
addition(3, 7, 5)

```

To Bypass method overloading we use Use-defined polymorphic method

```python
class Shape:
    # function with two default parameters
    def area(self, a, b=0):
        if b > 0:
            print('Area of Rectangle is:', a * b)
        else:
            print('Area of Square is:', a ** 2)

square = Shape()
square.area(5)

rectangle = Shape()
rectangle.area(5, 3)

```

>Area of Square is: 25
>Area of Rectangle is: 15

## Operator Overloading in Python

Operator overloading means changing the default behavior of an `operator` depending on the operands (values) that we use. In other words, we can use the same operator for multiple purposes.

```python
# add 2 numbers
print(100 + 200)

# concatenate two strings
print('Jess' + 'Roy')

# merger two list
print([10, 20, 30] + ['jessa', 'emma', 'kelly'])
```

### Overloading `+` operator for custom objects

 when we use the `+` operator, the magic method `__add__()` is automatically invoked. Internally `+` operator is implemented by using `__add__()` method. We have to override this method in our class if you want to add two custom objects.
```python
class Book:
    def __init__(self, pages):
        self.pages = pages

    # Overloading + operator with magic method
	    def __add__(self, other): # without this magic method it will throw Type Error
        return self.pages + other.pages

b1 = Book(400)
b2 = Book(300)
print("Total number of pages: ", b1 + b2)
	
```

> Total number of pages: 700

### Overloading the `*` Operator

```python
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary

    def __mul__(self, timesheet):
        print('Worked for', timesheet.days, 'days')
        # calculate salary
        return self.salary * timesheet.days


class TimeSheet:
    def __init__(self, name, days):
        self.name = name
        self.days = days


emp = Employee("Jessa", 800)
timesheet = TimeSheet("Jessa", 50)
print("salary is: ", emp * timesheet)
```


>Worked for 50 days
>salary is:  40000

### Magic Methods

In Python, there are different magic methods available to perform overloading operations. 

| Operator Name | Symbol | Magic method |
| --- | --- | --- |
| Addition | `+` | `__add__(self, other)` |
| Subtraction | `-` | `__sub__(self, other)` |
| Multiplication | `*` | `__mul**__**(self, other)` |
| Division | `/` | `__div__(self, other)` |
| Floor Division | `//` | `__floordiv__(self,other)` |
| Modulus | `%` | `__mod__(self, other)` |
| Power | `**` | `__pow__(self, other)` |
| Increment | `+=` | `__iadd__(self, other)` |
| Decrement | `-=` | `__isub__(self, other)` |
| Product | `*=` | `__imul__(self, other)` |
| Division | `/+` | `__idiv__(self, other)` |
| Modulus | `%=` | `__imod__(self, other)` |
| Power | `**=` | `__ipow__(self, other)` |
| Less than | `<` | `__lt__(self, other)` |
| Greater than | `>` | `__gt__(self, other)` |
| Less than or equal to | `<=` | `__le__(self, other)` |
| Greater than or equal to | `>=` | `__ge__(self, other)` |
| Equal to | `==` | `__eq__(self, other)` |
| Not equal | `!=` | `__ne__(self, other)` |
