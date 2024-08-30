# Magic Methods

### Definition

Magic methods, also known as dunder methods (double underscore methods), are special methods in Python that begin and end with double underscores. They allow you to define how your objects behave with built-in operations and functions.

### Common Magic Methods

1. **`__init__`**: Initializes a new instance of the class. Called when an object is created.

   ```python
   class Person:
       def __init__(self, name, age):
           self.name = name
           self.age = age

   person = Person("Alice", 30)
   ```

2. **`__str__`**: Defines the string representation of an object, used by the `str()` function and `print()`.

   ```python
   class Person:
       def __init__(self, name, age):
           self.name = name
           self.age = age

       def __str__(self):
           return f"{self.name}, {self.age} years old"

   person = Person("Alice", 30)
   print(person)  # Output: Alice, 30 years old
   ```

3. **`__repr__`**: Defines the official string representation of an object, used by the `repr()` function and typically for debugging.

   ```python
   class Person:
       def __init__(self, name, age):
           self.name = name
           self.age = age

       def __repr__(self):
           return f"Person(name={self.name!r}, age={self.age!r})"

   person = Person("Alice", 30)
   print(repr(person))  # Output: Person(name='Alice', age=30)
   ```

4. **`__add__`**: Defines behavior for the addition operator (`+`).

   ```python
   class Point:
       def __init__(self, x, y):
           self.x = x
           self.y = y

       def __add__(self, other):
           return Point(self.x + other.x, self.y + other.y)

       def __repr__(self):
           return f"Point({self.x}, {self.y})"

   p1 = Point(1, 2)
   p2 = Point(3, 4)
   p3 = p1 + p2
   print(p3)  # Output: Point(4, 6)
   ```

5. **`__eq__`**: Defines behavior for the equality operator (`==`).

   ```python
   class Person:
       def __init__(self, name, age):
           self.name = name
           self.age = age

       def __eq__(self, other):
           return (self.name == other.name) and (self.age == other.age)

   person1 = Person("Alice", 30)
   person2 = Person("Alice", 30)
   print(person1 == person2)  # Output: True
   ```

6. **`__len__`**: Defines behavior for the `len()` function.

   ```python
   class MyList:
       def __init__(self, items):
           self.items = items

       def __len__(self):
           return len(self.items)

   my_list = MyList([1, 2, 3, 4])
   print(len(my_list))  # Output: 4
   ```

### Benefits of Magic Methods

- **Enhanced Integration**: Allows custom objects to integrate seamlessly with Python's syntax and built-in functions.
- **Flexibility**: Provides the ability to define how objects respond to standard operations, making custom classes more intuitive to use.
- **Readability**: Helps in creating more readable and maintainable code by leveraging Python's built-in functionality in a natural way.

### Conclusion

Magic methods are a powerful feature in Python that enable you to define custom behavior for built-in operations and functions. By implementing these methods, you can make your objects work more naturally with Python's syntax and operations, enhancing both their usability and integration.

