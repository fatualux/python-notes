# Open/Closed Principle

”Software artifacts (classes, modules, functions, etc.) should be open 
for extension, but closed for modification.” 
(Bertrand Meyer, Object-Oriented Software Construction)

The Open/Closed Principle (OCP) is another key principle of object-oriented design within the S. O. L. I. D framework.

It encourages developers to design systems that can be easily extended to accommodate new functionality without altering existing code.

This can be achieved through the use of interfaces, abstract classes, and polymorphism.

## Example

The wrong way:

```python
class AreaCalculator:
    def calculate_area(self, shape):
        if isinstance(shape, Rectangle):
            return shape.width * shape.height
        elif isinstance(shape, Circle):
            return 3.14* (shape.radius **2)
        # If we want to add a new shape, we have to modify this method
        # which violates the Open/Closed Principle

class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

class Circle:
    def __init__(self, radius):
        self.radius = radius
```



```python
from abc import ABC, abstractmethod

# The Shape class is open for extension as we can add new shapes (e.g., Triangle) 
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

# by implementing the area method, but it is closed for modification since 
# we don't have to change existing code (like the Rectangle or Circle classes) 
# to accommodate new shapes.

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * (self.radius**2)

def calculate_area(shapes):
    return sum(shape.area() for shape in shapes)

# Example usage
shapes = [Rectangle(2, 3), Circle(5)]
print(calculate_area(shapes))  # Output: 36.14

```
