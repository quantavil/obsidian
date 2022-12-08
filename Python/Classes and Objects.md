-   **Class**: The class is a user-defined data structure that binds the data members and methods into a single unit. Class is a **blueprint or code template for object creation**. Using a class, you can create as many objects as you want.
-   **Object**: An **object is an instance of a class**. It is a collection of attributes (variables) and methods. We use the object of a class to perform actions.
Objects have three characteristics: -   *Identity* Every object must be uniquely identified. *Attributes* represent its state, and *methods* represent its behavior. Using its methods, we can modify its state.

![](https://pynative.com/wp-content/uploads/2021/08/class_and_objects.jpg)

A real-life example of class and objects.

**Class**: Person

-   **State**: Name, Sex, Profession
-   **Behavior**: Working, Study

Using the above class, we can create multiple objects that depict different states and behavior.

**Object 1**: Jessa

-   **State**:
    -   Name: Jessa
    -   Sex: Female
    -   Profession: Software Engineer
-   **Behavior**:
    
    -   Working: She is working as a software developer at ABC Company
    
    -   Study: She studies 2 hours a day

**Object 2**: Jon

-   **State**:
    -   Name: Jon
    -   Sex: Male
    -   Profession: Doctor
-   **Behavior**:
    
    -   Working: He is working as a doctor
    
    -   Study: He studies 5 hours a day

### Syntax
```python
class class_name:
    '''This is a docstring. I have created a new class'''
    <statement 1>
    <statement 2>
    .
    .
    <statement N> # Attributes and methods
```

In Python, Object creation is divided into two parts in **Object Creation** and **Object initialization**

-   Internally, the `__new__` is the method that creates the object
-   And, using the `__init__()` method we can implement constructor to initialize the object.

### syntax
`<object-name> = <class-name>(<arguments>)`

example : `jessa = Person('Jessa', 'Female', 'Software Engineer')`

```python
class Person:
    def __init__(self, name, sex, profession):
        # data members (instance variables)
        self.name = name
        self.sex = sex
        self.profession = profession

    # Behavior (instance methods)
    def show(self):
        print('Name:', self.name, 'Sex:', self.sex, 'Profession:', self.profession)

    # Behavior (instance methods)
    def work(self):
        print(self.name, 'working as a', self.profession)

# create object of a class
jessa = Person('Jessa', 'Female', 'Software Engineer')

# call methods
jessa.show()
jessa.work()

```

>Name: Jessa Sex: Female Profession: Software Engineer
>Jessa working as a Software Engineer

## Attributes

![](https://pynative.com/wp-content/uploads/2021/08/class_attributes_in_python.jpg)

```python
class Student:
    [[class]] variable
    school_name = "Springfield Elementary"

    [[constructor]]
    def __init__(self, name, age):
        [[instance]] variable
        self.name = name
        self.age = age

s1 = Student("John", 12)  # Creating an object named s1

[[accessing]] instance variable
print('Student: ',s1.name, s1.age)

[[accessing]] class variable
print('School name: ',Student.school_name, s1.school_name) # shared by all instances

# Modifying instance variable 
s1.age = 13
s1.name = "Marie Doe"
print('Student: ',s1.name, s1.age)

# Modifying class variable
Student.school_name = "Springfield High School"
print('School name: ',Student.school_name, s1.school_name)

print(s1.__dict__)
# deleting instance variable / object property
del s1.name
print(s1.__dict__)

# deleting the object
del s1
print(s1.__dict__)
```

>Student:  John 12
>School name:  Springfield Elementary Springfield Elementary
>Student:  Marie Doe 13
>School name:  Springfield High School Springfield High School
>{'name': 'Marie Doe', 'age': 13}
>{'age': 13}
>NameError: name 's1' is not defined


## Methods

-   **Instance method**: Used to access or modify the object state. If we use *instance variables* inside a method, such methods are called instance methods.
-   **Class method**: Used to access or modify the class state. In method implementation, if we use only *class variables*, then such type of methods we should declare as a class method.
-   **Static method**: It is a general utility method that performs a task in isolation. Inside this method, we don’t use instance or class variable because this static method doesn’t have access to the class attributes.

![](https://pynative.com/wp-content/uploads/2021/08/python_class_method_vs_static_method_vs_instance_method.png)


In Python, the `pass` is a null statement. Therefore, nothing happens when the pass statement is executed.