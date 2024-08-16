# Objects

An **object** is an abstraction for a data structure; everything in Python is an object.

In Object Oriented Programming, we are trying to model *real life objects*, and these objects have things (*attributes*, usually modeled by *variables*) and they also can do things (*methods*, usually modeled by functions).

![Objects](../static/images/objects.png)

For example, a function can be an object, but a class, a list, a variable can be objects too, and so on. Everything in Python can be defined as an object.

We can also affirm that <ins>an object is an **instance** of a class</ins>. In this case, the word *instance* means an *example*, an *occurrence* of a class.

Objects encapsulate data and functions (methods) which operate on that data. An object could be seen as a container of data, characterized by these three essential peculiarities:

1. An **identifier** (ID): A unique name or reference that distinguishes one object from another.
2. A **type**: The class or data type of the object which defines the object's behavior and properties.
3. A **value**: The data or state contained within the object.

## Key Concepts of Objects in Python

- **Creating Objects**:
  Objects are created by instantiating a class. Each object can have its own state and behavior based on the class it is an instance of.

  ```python
  class Car:
      def __init__(self, make, model):
          self.make = make
          self.model = model

  my_car = Car("Toyota", "Corolla")
  ```

- **Accessing Object Attributes**:
  You can access and modify the attributes of an object using dot notation.

  ```python
  print(my_car.make)  # Output: Toyota
  my_car.model = "Camry"
  print(my_car.model)  # Output: Camry
  ```

- **Calling Object Methods**:
  Methods are functions defined within a class that operate on the object’s data. You call a method using dot notation.

  ```python
  class Dog:
      def bark(self):
          print("Woof!")

  my_dog = Dog()
  my_dog.bark()  # Output: Woof!
  ```

- **Object Identity**:
  Every object has a unique identity, which can be obtained using the `id()` function. This identity remains constant during the object’s lifetime.

  ```python
  print(id(my_car))  # Outputs a unique identifier for the object
  ```

- **Object Type**:
  The type of an object can be determined using the `type()` function. This returns the class to which the object belongs.

  ```python
  print(type(my_car))  # Output: <class '__main__.Car'>
  ```

- **Object Value**:
  The value of an object is the actual data stored in the object’s attributes. This value can be manipulated and queried through methods and attributes.

  ```python
  print(my_car.make)  # Output: Toyota
  ```

- **Mutability**:
  Objects can be mutable (e.g., lists, dictionaries) or immutable (e.g., integers, strings, tuples). Mutable objects can be changed after they are created, while immutable objects cannot.

  ```python
  mutable_list = [1, 2, 3]
  immutable_tuple = (1, 2, 3)

  mutable_list.append(4)  # The list can be modified
  # immutable_tuple.append(4)  # This would raise an AttributeError
  ```

- **Object Lifespan**:
  The lifespan of an object begins when it is created and ends when it is no longer referenced and is garbage collected by Python.

  ```python
  del my_car  # Removes the reference to the object; it may be garbage collected
  ```

- **Instance Methods vs. Class Methods**:
  - **Instance Methods**: Operate on an instance of the class and can access or modify the instance's attributes.
  - **Class Methods**: Operate on the class itself rather than instances and can be defined using the `@classmethod` decorator.

  ```python
  class MyClass:
      @classmethod
      def class_method(cls):
          print("This is a class method.")

      def instance_method(self):
          print("This is an instance method.")

  MyClass.class_method()  # Output: This is a class method.
  obj = MyClass()
  obj.instance_method()  # Output: This is an instance method.
  ```

- **Static Methods**:
  Static methods do not access or modify class or instance attributes and can be defined using the `@staticmethod` decorator.

  ```python
  class Math:
      @staticmethod
      def add(x, y):
          return x + y

  print(Math.add(5, 3))  # Output: 8
  ```

