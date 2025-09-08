## Singleton Pattern

Singleton ensures that a class has only one instance and provides an easy global access to that instance.
The pattern does not stipulate what to do with a Singleton. This is where you can be
creative.

The main tenets of this pattern are:
1. Ensure that the class has only a single instance.
2. Provide easy global access to this instance.
3. Control how it is instantiated.
4. Any critical region must be entered serially.

### When to use:

When you want to control access to a shared resource.

### When not to use:

Use the Singleton pattern with restraint and do not let it degenerate into
just a global access for everything. Global access hides dependencies and
might make it harder to read such code, so make sure that you have a good
reason to use this pattern.11548768

The main question you should ask is: do you violate the SRP (Single
Responsibility Principle?) If YES then reconsider using it.

If your singleton is doing too much, it might be a sign that you need to refactor your code.

Consider breaking it down into smaller, more focused classes that adhere to the Single Responsibility Principle.


When designing a Singleton, consider lazy construction which means that
the class instance should only be created when it is first needed. In some
cases we might consider eager loading if, for example, we need the
singleton to be always ready and loaded fast.

Thread-Safety needs to be considered in languages that allow
multi-threaded access to ensure that access is properly controlled and
locked, so that the state of the singleton (if it has one) is always
deterministic.
a. Because Python does support multi-threaded programming we will
need to take special care when creating multi-threaded singletons.
We will need to lock the Critical Section.


The Singleton Pattern can be implemented in a
number of different ways in
python.
Some possible methods include:
1. Base class.
2. Decorator.
3. Metaclass.
From those, the metaclass is best suited for this
purpose since with it we can manipulate and control
the task of class creation itself.

Quick note on some general Python function overrides:
1. __new__ : This is a static method that is responsible for creating and
returning a new instance of a class. It is the first step in the object
instantiation process. It is typically overridden when you need to control
the object creation process
2. __init__ : This is an instance method that is responsible for initializing an
object's attributes after it has been created by __new__. The __init__
method does not return a value and is called automatically after the object
is created. This method is typically overridden to define custom attribute
initialization for the class.
3. __call__ : This is an instance method that allows a class's instances to be
called as if they were functions.


**Example of Singleton**

### LAZY INSTANTIATION

```python
class Logger(Singleton):
    def __init__(self):
        if not hasattr(self, 'initialized'):  # prevent re-initialization
            self.initialized = True
            self.logs = []

    def log(self, message):
        self.logs.append(message)
        print(f"Log: {message}")

    def get_logs(self):
        return self.logs


# Usage
if __name__ == "__main__":
    logger1 = Logger()
    logger2 = Logger()

    logger1.log("First log entry.")
    logger2.log("Second log entry.")

    # Both logger1 and logger2 should be the same instance
    print(logger1 is logger2)  # Outputs: True
    print(logger1.get_logs())   # Outputs: ['First log entry.', 'Second log entry.']
```

```python
class Singleton:
# class-level variable to store the single instance of the class
_instance = None

# override the method to control how new objects are created
def __new__(cls, *args, **kwargs):
    # check if instance of the class has been created before.
    if not cls._instance:
        # create new instance of the class and store it in instance
        cls._instance = super().__new__(cls, *args, **kwargs)
    # return the single instance of the class
    # newly created one or existing one
    return cls._instance
if not cls._instance:
# create new instance of the class
# and store it in instance
cls._instance = super().__new__(cls)
# return the single instance of the class
# newly created one or existing one
return cls._instance
```

### Best Python Implementation:

Using the metaclass is probably the best way to create a Singleton in Python.
A metaclass in Python is a class that defines the behavior and rules for creating other classes.

In other words, metaclasses are the "classes of classes."
By default, all Python classes implicitly inherit from the type built-in class, which is itself a
metaclass.

Metaclasses allow us to customize the class creation process and modify class attributes,
methods, or other properties before the class is actually created.
They provide a way to apply certain behaviors consistently across multiple classes.

```python
class SingletonMeta (type) :
# Dictionary stores single instance of the class for
# each subclass of the SingletonMeta metaclass
instances = {}

def __call__(cls, *args, **kwargs):
    # Single instance of the class already been created?
    if cls not in cls.instances:
        # Create the instance by calling the method of the parent's class.
        instance = super().__call__(*args, **kwargs)
        cls.instances[cls] = instance
    return cls.instances[cls]

# our actual Singleton class
class Singleton (metaclass=SingletonMeta) :
    def some_business_logic(self):
        pass
```

## EAGER LOADING

- Allows for data preload and caching.
- Allows for connectivity pre-caching.
- Important when access is frequent and needs to be fast.
- We initialize and load the instance before we need it.

Python does not provide an out-of-the-box solution for eager loading, but we can use metaclasses to implement it.

```python
class EagerSingletonMeta(type):
    # Dictionary stores single instance of the class for
    # each subclass of the SingletonMeta metaclass
    _instances = {}

    # override: called during creation of sub-types
    def __init__(cls, name, bases, attrs):
        super().__init__(name, bases, attrs)
        # eager loading of the class instance
        cls._instances[cls] = super().__call__()
        # return the single instance of the class
        def __call__(cls, *args, **kwargs):
            return cls._instances[cls]

    # returns the single instance of the class
    def get_instance(cls):
        return cls._instances[cls]

# actual Singleton class
class EagerSingleton(metaclass=EagerSingletonMeta):
    def __init__(self):
        self.state = "Initial State"

    def some_logic(self):
        print(f"EagerSingleton: {self.state}")
```
