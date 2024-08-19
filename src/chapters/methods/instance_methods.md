# Instance Methods

Instance methods are functions defined within a class that operate on instances of the class. They take the instance itself as the first argument, conventionally named `self`. This allows the method to access and modify the instance's attributes and other methods.

### Defining Instance Methods

Instance methods are defined using the `def` keyword inside a class. The first parameter of an instance method is always `self`, which refers to the instance on which the method is called.

#### Example:

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def display_info(self):
        return f"{self.make} {self.model}"

# Create an instance of Car
my_car = Car("Opel", "Astra")
print(my_car.display_info())  # Output: Opel Astra
```

### Accessing and Modifying Attributes

Instance methods can access and modify instance attributes defined in the `__init__` method or elsewhere in the class.

#### Example:

```python
class BankAccount:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def get_balance(self):
        return self.balance

# Create an instance of BankAccount
account = BankAccount(100)
account.deposit(50)
print(account.get_balance())  # Output: 150
```

### Using `self`

The `self` parameter is used to access instance attributes and other methods from within an instance method. It is automatically passed by Python when the method is called on an instance.

#### Example:

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)

# Create an instance of Rectangle
rect = Rectangle(4, 5)
print(rect.area())       # Output: 20
print(rect.perimeter())  # Output: 18
```

### Best Practices

- **Use Descriptive Names**: Name methods clearly to reflect their functionality.
- **Keep Methods Focused**: Each instance method should have a single responsibility. Avoid making methods too complex or multi-functional.
- **Document Methods**: Use docstrings to describe the purpose and behavior of instance methods for better code readability and maintainability.
- **Avoid Modifying Global State**: Instance methods should generally operate on instance data rather than affecting global state or other unrelated instances.

