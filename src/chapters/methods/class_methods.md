# Class Methods

Class methods are methods that operate on the class itself rather than on instances of the class. They take the class as their first parameter, conventionally named `cls`. Class methods can be used to access or modify class-level attributes and are defined using the `@classmethod` decorator.

### Defining Class Methods

Class methods are defined using the `@classmethod` decorator and must have `cls` as their first parameter.

#### Example:

```python
class MyClass:
    class_variable = "I am a class variable"

    @classmethod
    def get_class_variable(cls):
        return cls.class_variable

# Access the class method
print(MyClass.get_class_variable())  # Output: I am a class variable
```

### Modifying Class State

Class methods can be used to modify class-level attributes or perform actions that affect the class as a whole.

#### Example:

```python
class Counter:
    count = 0

    @classmethod
    def increment(cls):
        cls.count += 1

    @classmethod
    def get_count(cls):
        return cls.count

# Increment the count using the class method
Counter.increment()
print(Counter.get_count())  # Output: 1
```

### Using Class Methods for Factory Methods

Class methods can be used as factory methods to create instances of the class in different ways. This can be useful for alternative constructors.

#### Example:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_string(cls, person_str):
        name, age = person_str.split('-')
        return cls(name, int(age))

# Create an instance using the class method
person = Person.from_string("John-30")
print(person.name)  # Output: John
print(person.age)   # Output: 30
```

### Key Differences from Instance Methods

- **First Parameter**: Class methods use `cls` to refer to the class, while instance methods use `self` to refer to the instance.
- **Access**: Class methods can access and modify class-level attributes, whereas instance methods operate on instance-specific attributes.

### Best Practices

- **Use for Class-Level Operations**: Use class methods for operations that pertain to the class itself rather than to individual instances.
- **Factory Methods**: Use class methods to provide alternative ways to instantiate objects, especially when the initialization logic is complex.
- **Keep Methods Focused**: Ensure class methods are clear in their purpose and only handle class-level operations.

