# Inheritance

Inheritance is an object-oriented programming concept that allows a class (child or subclass) to inherit attributes and methods from another class (parent or superclass). It promotes code reuse and establishes a hierarchical relationship between classes.

### Types of Inheritance

1. **Single Inheritance**: A class inherits from a single parent class.

   ```python
   class Animal:
       def speak(self):
           return "Animal sound"

   class Dog(Animal):
       def bark(self):
           return "Woof"

   dog = Dog()
   print(dog.speak())  # Output: Animal sound
   print(dog.bark())   # Output: Woof
   ```

2. **Multiple Inheritance**: A class inherits from more than one parent class. 

   ```python
   class A:
       def method_a(self):
           return "Method A"

   class B:
       def method_b(self):
           return "Method B"

   class C(A, B):
       pass

   c = C()
   print(c.method_a())  # Output: Method A
   print(c.method_b())  # Output: Method B
   ```

3. **Multilevel Inheritance**: A class inherits from a class that is itself inherited from another class.

   ```python
   class Animal:
       def eat(self):
           return "Eating"

   class Mammal(Animal):
       def walk(self):
           return "Walking"

   class Dog(Mammal):
       def bark(self):
           return "Woof"

   dog = Dog()
   print(dog.eat())    # Output: Eating
   print(dog.walk())   # Output: Walking
   print(dog.bark())   # Output: Woof
   ```

4. **Hierarchical Inheritance**: Multiple classes inherit from a single parent class.

   ```python
   class Vehicle:
       def start(self):
           return "Vehicle started"

   class Car(Vehicle):
       def drive(self):
           return "Driving car"

   class Bike(Vehicle):
       def ride(self):
           return "Riding bike"

   car = Car()
   bike = Bike()
   print(car.start())  # Output: Vehicle started
   print(car.drive())  # Output: Driving car
   print(bike.start()) # Output: Vehicle started
   print(bike.ride())  # Output: Riding bike
   ```

### The `super()` Function

The `super()` function is used to call methods from a parent class from within a child class. This is useful for extending the functionality of inherited methods.

```python
class Parent:
    def greet(self):
        return "Hello from Parent"

class Child(Parent):
    def greet(self):
        return super().greet() + " and Child"

child = Child()
print(child.greet())  # Output: Hello from Parent and Child
```

### Key Points

- **Code Reuse**: Inheritance promotes reuse by allowing a child class to use methods and attributes from a parent class.
- **Hierarchical Relationships**: It establishes a hierarchical relationship between classes.
- **Extensibility**: Child classes can extend or modify the behavior of parent classes.

### Best Practices

- **Favor Composition over Inheritance**: Use composition to combine functionalities where possible, and use inheritance for clear hierarchical relationships.
- **Keep Hierarchies Simple**: Avoid deep inheritance hierarchies that can make the codebase complex and difficult to manage.
- **Document Inheritance**: Clearly document the parent-child relationships and overridden methods to enhance code readability and maintainability.

