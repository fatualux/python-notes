# Polymorphism

Polymorphism is a core concept in object-oriented programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. It is derived from Greek, meaning "many shapes."

### Types of Polymorphism

1. **Method Overriding**: This occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. The method in the subclass overrides the method in the superclass.

   ```python
   class Animal:
       def speak(self):
           return "Animal speaks"

   class Dog(Animal):
       def speak(self):
           return "Dog barks"

   def make_animal_speak(animal):
       print(animal.speak())

   my_dog = Dog()
   make_animal_speak(my_dog)  # Output: Dog barks
   ```

2. **Method Overloading**: Python does not support method overloading by default as some other languages do. Instead, you can use default arguments or variable-length arguments to achieve similar results.

   ```python
   class Example:
       def greet(self, name=None):
           if name:
               return f"Hello, {name}!"
           return "Hello!"

   obj = Example()
   print(obj.greet())        # Output: Hello!
   print(obj.greet("Alice")) # Output: Hello, Alice!
   ```

3. **Operator Overloading**: Python allows operators to be overloaded to provide custom behavior for user-defined classes.

   ```python
   class Vector:
       def __init__(self, x, y):
           self.x = x
           self.y = y

       def __add__(self, other):
           return Vector(self.x + other.x, self.y + other.y)

       def __repr__(self):
           return f"Vector({self.x}, {self.y})"

   v1 = Vector(2, 3)
   v2 = Vector(4, 5)
   v3 = v1 + v2
   print(v3)  # Output: Vector(6, 8)
   ```

### Benefits of Polymorphism

- **Flexibility**: Allows for the use of a single interface to represent different underlying forms (data types).
- **Reusability**: Enhances code reusability by allowing the same function or method to operate on different types of data.
- **Maintainability**: Simplifies code maintenance and modification by reducing the need for multiple function names and promoting code uniformity.

