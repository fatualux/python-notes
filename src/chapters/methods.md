# Methods

In Python, a **method** is a function that is associated with an object, and defines the behavior of the objects of a class.

![Methods](../static/images/methods.png)

In other words, methods are defined inside a class and are accessed via instances of that class (objects).
They can take parameters (like regular functions) and operate on the object's internal state.

## Key Concepts of Methods in Python

- **Instance Methods**:
  These are the most common type of methods and are used to manipulate the state of an object or perform operations using its data. They take `self` as the first parameter, which represents the instance on which the method is called.

  ```python
  class Wolf:
      def howl(self):
          """Instance method that simulates the wolf howling."""
          print("Wooooooo!")

  wolf = Wolf()
  wolf.howl()  # Output: Wooooooo!
  ```

- **The `self` Parameter**:
  The `self` parameter is a reference to the current instance of the class and is used to access variables and methods that belong to the instance. It must be the first parameter in any instance method.

In other words, *self* refers to the actual object that's being created, *initialised*.

  ```python
  class Dog:
      def __init__(self, name):
          self.name = name  # Instance variable

      def bark(self):
          """Instance method that makes the dog bark."""
          print(f"{self.name} says Woof!")

  dog = Dog("Scooby-Doo")
  dog.bark()  # Output: Scooby-Doo says Woof!
  ```

- **Class Methods**:
  Class methods are methods that operate on the class itself rather than on instances of the class. They are defined using the `@classmethod` decorator and take `cls` as the first parameter, which represents the class.

  ```python
  class Cat:
      species = "Feline"

      @classmethod
      def set_species(cls, species_name):
          """Class method that sets the species for the class."""
          cls.species = species_name

      @classmethod
      def get_species(cls):
          """Class method that returns the species."""
          return cls.species

  Cat.set_species("Big Feline")
  print(Cat.get_species())  # Output: Big Feline
  ```

- **Static Methods**:
  Static methods do not operate on an instance or the class itself. They are defined using the `@staticmethod` decorator and do not take `self` or `cls` as a parameter. Static methods are typically utility functions that relate to the class but do not require access to class or instance variables.

  ```python
  class MathUtility:
      @staticmethod
      def add(a, b):
          """Static method that adds two numbers."""
          return a + b

  result = MathUtility.add(3, 4)  # Output: 7
  ```

- **Special Methods (Magic Methods)**:
  Python classes have special methods, often referred to as magic methods or dunder methods (double underscore methods), that allow you to define how objects of the class behave in certain situations. These methods are prefixed and suffixed with double underscores (`__`).

  - `__init__(self, ...)`: Called when an instance is created (constructor). It is used to initialise attributes.
  - `__str__(self)`: Defines the string representation of an object, used by `str()` and `print()`.
  - `__repr__(self)`: Defines a more detailed string representation, used by `repr()` and in debugging.
  - `__len__(self)`: Returns the length of the object, used by `len()`.
  - `__eq__(self, other)`: Defines behavior for the equality operator `==`.

```python
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages

    def __str__(self):
        """String representation of the object."""
        return f"'{self.title}' by {self.author}"

    def __repr__(self):
        """Detailed string representation, useful for debugging."""
        return f"Book(title='{self.title}', author='{self.author}', pages={self.pages})"

    def __len__(self):
        """Length of the book in pages."""
        return self.pages

    def __eq__(self, other):
        """Equality comparison between two books."""
        if isinstance(other, Book):
            return (self.title == other.title and
                    self.author == other.author and
                    self.pages == other.pages)
        return False

# Creating book instances
book1 = Book("1984", "George Orwell", 328)
book2 = Book("1984", "George Orwell", 328)
book3 = Book("Brave New World", "Aldous Huxley", 268)

# Using __str__ method
print(book1)        # Output: '1984' by George Orwell

# Using __repr__ method
print(repr(book1))  # Output: Book(title='1984', author='George Orwell', pages=328)

# Using __len__ method
print(len(book1))   # Output: 328

# Using __eq__ method
print(book1 == book2)  # Output: True
print(book1 == book3)  # Output: False
```

- **Method Overriding**:
  In a subclass, you can override a method defined in the parent class. This allows you to customize or extend the behavior of inherited methods.

  ```python
  class Animal:
      def speak(self):
          return "Some sound"

  class Dog(Animal):
      def speak(self):
          """Override the speak method to return a dog-specific sound."""
          return "Woof!"

  dog = Dog()
  print(dog.speak())  # Output: Woof!
  ```

- **Method Chaining**:
  Method chaining allows you to call multiple methods on the same object in a single line. To facilitate chaining, each method should return the object itself (`self`).

  ```python
  class Car:
      def __init__(self, brand):
          self.brand = brand
          self.speed = 0

      def accelerate(self, increase):
          """Increase the car's speed."""
          self.speed += increase
          return self

      def brake(self, decrease):
          """Decrease the car's speed."""
          self.speed -= decrease
          return self

      def display(self):
          """Display the car's brand and current speed."""
          print(f"{self.brand} is going at {self.speed} km/h")
          return self

  car = Car("Toyota")
  car.accelerate(30).brake(10).display()  # Output: Toyota is going at 20 km/h
  ```

Note that *method chaining* requires a return (`return self`), in order to call the next method.
Otherwise, the returned value is `None` by default, and chaining method is not possible (a *NoneType* error is raised).

