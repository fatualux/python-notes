# Classes

In Python, a **class** is <ins>a template, a prototype</ins> that defines the structure and <ins>behavior (attributes and methods)</ins> of objects.

![Classes](../../static/images/class.png)

So, we can say that classes are used to create objects.

## Key Concepts of Classes in Python

- **Class Definition**:
A class is defined <ins>using the class keyword</ins> followed by the class name and a colon.
Class names are typically written in CamelCase[^1].


```
class MyClass: # this is how a class is defined
```

- **Attributes and Methods**:
Attributes are variables that belong to the class.
Methods are functions that belong to the class.

```
class MyClass:
    def my_method(self):
        message = "Hello, World!" # this is an attribute
        print(message) # this is a method
```

- **The __init__ Method**:
It is a special method called **constructor** that is automatically called when a new instance of the class is created; it is used to <ins>initialize the attributes</ins> of the class.

- **Self Parameter**:
The <ins>first parameter</ins> of every method in a class, usually named <ins>self</ins>, which refers to the instance calling the method.

```
class MyClass:
    def __init__(self): # this is the constructor
        self.my_attribute = "Hello, World!"
        print(self.my_attribute)
```
- **Creating an Instance**:
An instance is created by calling the class using its name and passing any required arguments.

```
my_instance = MyClass()
```

- **Inheritance**:
A mechanism to create a new class using details of an existing class without modifying it. The new class (child class) inherits attributes and methods from the existing class (parent class).
