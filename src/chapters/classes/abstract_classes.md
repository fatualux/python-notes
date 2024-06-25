# Abstract Classes

An abstract class is a class that cannot be instantiated on its own and is intended to be subclassed. It provides a common interface for its subclasses and may include abstract methods that must be implemented by any subclass.

### Characteristics

1. **Abstract Methods**: Methods declared in an abstract class that do not have an implementation. Subclasses must override these methods to provide specific functionality.

   ```python
   from abc import ABC, abstractmethod

   class Shape(ABC):
       @abstractmethod
       def area(self):
           pass

       @abstractmethod
       def perimeter(self):
           pass

   class Circle(Shape):
       def __init__(self, radius):
           self.radius = radius

       def area(self):
           return 3.14 * self.radius ** 2

       def perimeter(self):
           return 2 * 3.14 * self.radius

   my_circle = Circle(5)
   print(my_circle.area())       # Output: 78.5
   print(my_circle.perimeter())  # Output: 31.400000000000002
   ```

2. **Concrete Methods**: Methods in an abstract class that have an implementation. Subclasses can use these methods directly or override them if needed.

   ```python
   class Shape(ABC):
       @abstractmethod
       def area(self):
           pass

       @abstractmethod
       def perimeter(self):
           pass

       def description(self):
           return "This is a geometric shape."

   class Rectangle(Shape):
       def __init__(self, width, height):
           self.width = width
           self.height = height

       def area(self):
           return self.width * self.height

       def perimeter(self):
           return 2 * (self.width + self.height)

   my_rectangle = Rectangle(4, 6)
   print(my_rectangle.description())  # Output: This is a geometric shape.
   ```

### Benefits of Abstract Classes

- **Design Blueprint**: Provides a template for other classes to follow, ensuring that a certain set of methods are implemented in subclasses.
- **Code Reusability**: Allows for the reuse of common code and functionality in concrete subclasses.
- **Enforces Structure**: Ensures that all subclasses adhere to a certain interface and implement necessary methods, promoting consistency.

