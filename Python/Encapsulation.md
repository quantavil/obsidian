**Encapsulation** in Python describes the concept of **bundling data and methods within a single unit.** So, for example, when you create a *class*, it means you are implementing encapsulation. A class is an example of encapsulation as it binds all the data members *(instance variables)* and methods into a single unit.

![](https://pynative.com/wp-content/uploads/2021/08/encapsulation_python_class.jpg)

## Access Modifiers in Python

Access modifiers limit access to the variables and methods of a class. Python provides three types of access modifiers private, public, and protected.

-   **Public Member**: Accessible anywhere from outside class.
-   **Private Member**: Accessible within the class
-   **Protected Member**: Accessible within the class and its sub-classes

We can achieve this by using single **underscore** and **double** **underscores**.

![](https://pynative.com/wp-content/uploads/2021/08/python_data_hiding.jpg)


```python
class Student:
    [[constructor]] is defined
    def __init__(self, name, age, salary):
        self.age = age             # public Attribute
        self._name = name          # protected Attribute 
        self.__salary = salary     # private Attribute

    def _funName(self):            # protected method
        pass
 
    def __funName(self):           # private method
        pass
```

## Getters and Setters

Use the getter method to access data members and the setter methods to modify the data members.
In Python, private variables are not hidden fields like in other programming languages. The getters and setters methods are often used when:

-   When we want to avoid direct access to private variables
-   To add validation logic for setting a value

```python
class Student:
    def __init__(self, name, age):
        # private member
        self.name = name
        self.__age = age

    # getter method
    def get_age(self):
        return self.__age

    # setter method
    def set_age(self, age):
        self.__age = age

stud = Student('Jessa', 14)

# retrieving age using getter
print('Name:', stud.name, stud.get_age())

stud.name = 'Jessica'
stud.__age = 151 # will nor change the age because it is private

print('Name:', stud.name, stud.get_age())

# changing age using setter
stud.set_age(1612)

# retrieving age using getter
print('Name:', stud.name, stud.get_age())
```

>Name: Jessa 14
>Name: Jessica 14
>Name: Jessica 1612

## Advantages of Encapsulation

-   **Security**: The main advantage of using encapsulation is the security of the data. Encapsulation protects an object from unauthorized access. It allows private and protected access levels to prevent accidental data modification.
-   **Data Hiding**: The user would not be knowing what is going on behind the scene. They would only be knowing that to modify a data member, call the setter method. To read a data member, call the getter method. What these setter and getter methods are doing is hidden from them.
-   **Simplicity**: It simplifies the maintenance of the application by keeping classes separated and preventing them from tightly coupling with each other.
-   **Aesthetics**: Bundling data and methods within a class makes code more readable and maintainable