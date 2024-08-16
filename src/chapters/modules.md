# Modules

![Modules](../static/images/modules.png)

In Python, a **module** is a file containing Python definitions and statements. Modules allow you to organize your Python code into manageable sections and reuse code across different parts of your application. Each module has a `.py` extension.

## Key Concepts of Modules in Python

- **Creating a Module**:
  To create a module, simply save your Python code in a file with a `.py` extension. For example, `mymodule.py` is a module file.

  ```python
  # mymodule.py
  def greet(name):
      """Return a greeting message."""
      return f"Hello, {name}!"

  pi = 3.14159
  ```

- **Importing Modules**:
  You can import modules using the `import` keyword. This allows you to access the functions, classes, and variables defined in the module.

  ```python
  import mymodule

  message = mymodule.greet("Alice")
  print(message)  # Output: Hello, Alice!
  ```

- **Importing Specific Items**:
  You can import specific functions or variables from a module to avoid importing the entire module.

  ```python
  from mymodule import greet, pi

  message = greet("Bob")
  print(message)  # Output: Hello, Bob!
  print(pi)       # Output: 3.14159
  ```

- **Importing with Aliases**:
  You can use the `as` keyword to give a module or function an alias, which can make your code shorter and more readable.

  ```python
  import mymodule as mm

  message = mm.greet("Charlie")
  print(message)  # Output: Hello, Charlie!
  ```

- **Module Search Path**:
  Python searches for modules in a specific order: the current directory, then directories listed in the `PYTHONPATH` environment variable, and finally in the default installation directories.

  You can view the module search path using the following code:

  ```python
  import sys
  print(sys.path)
  ```

- **Standard Library Modules**:
  Python includes a standard library of modules that provide useful functionalities. Some common standard library modules include:
  - `math`: Mathematical functions.
  - `datetime`: Date and time functions.
  - `os`: Operating system interfaces.
  - `sys`: System-specific parameters and functions.

  ```python
  import math
  import datetime

  print(math.sqrt(16))  # Output: 4.0
  print(datetime.date.today())  # Output: Current date
  ```

- **Module Initialization**:
  When a module is imported, Python executes its code. If you have initialization code that should only run when the module is executed directly (not when imported), use the `if __name__ == "__main__":` construct.

  ```python
  # mymodule.py
  def greet(name):
      """Return a greeting message."""
      return f"Hello, {name}!"

  if __name__ == "__main__":
      print(greet("Main"))
  ```

  If you run `mymodule.py` directly, it will print "Hello, Main!". If imported into another module, it will not print this message.

- **Reloading Modules**:
  To reload a module that has been modified since it was first imported, use the `reload()` function from the `importlib` module.

  ```python
  import importlib
  import mymodule

  importlib.reload(mymodule)
  ```

