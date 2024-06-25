# Names

In Python, **names** are *identifiers* used to refer to objects, such as variables, functions, classes, and modules. Names allow you to retrieve and manipulate data in your code.

![Names](../static/images/name.png)

## Key Concepts of Names in Python

- **Naming Rules**:
  Names must follow certain rules:
  - Names can consist of letters (a-z, A-Z), digits (0-9), and underscores (_).
  - Names must start with a letter or an underscore, not a digit.
  - Names are case-sensitive (`myvariable` is different from `MyVariable`).
  - Names cannot be the same as Python keywords (e.g., `if`, `for`, `class`).

  ```python
  valid_name = "This is valid"
  _private_name = "Also valid"
  name123 = "Valid with numbers"
  # 123name = "Invalid, starts with a number"  # SyntaxError
  ```

- **Reserved Keywords**:
  Python has reserved keywords that cannot be used as names. These keywords have special meanings and are used to define the syntax of the language.

  ```python
  import keyword
  print(keyword.kwlist)  # Prints a list of reserved keywords
  ```

- **Naming Conventions**:
  Naming conventions help improve code readability and maintainability:
  - **Variables and functions**: Use lowercase letters with words separated by underscores (`snake_case`).
  - **Classes**: Use CamelCase (e.g., `MyClass`).
  - **Constants**: Use uppercase letters with words separated by underscores (`UPPER_CASE`).

  ```python
  # Variable and function names
  user_age = 25
  def calculate_area(radius):
      return 3.14 * radius * radius

  # Class names
  class StudentProfile:
      pass

  # Constant names
  MAX_LIMIT = 100
  ```

- **Global vs. Local Names**:
  Names defined outside any function or class are global and can be accessed from anywhere in the module. Names defined inside a function or class are local to that function or class.

  ```python
  global_name = "I'm global"

  def my_function():
      local_name = "I'm local"
      print(global_name)  # Accesses the global name
      print(local_name)   # Accesses the local name

  my_function()
  print(local_name)  # Raises NameError because local_name is not accessible here
  ```

- **Built-in Names**:
  Python provides a set of built-in names that represent standard functions, types, and objects. These names are part of the built-in namespace and are available in every module.

  ```python
  print(len([1, 2, 3]))  # len is a built-in function
  print(type(42))        # type is a built-in function
  ```

- **Name Resolution**:
  Python uses a system called LEGB (Local, Enclosing, Global, Built-in) to resolve names:
  - **Local**: Names assigned within the current function.
  - **Enclosing**: Names in the outer function’s scope (if nested functions).
  - **Global**: Names assigned at the top level of the module.
  - **Built-in**: Names in the built-in namespace.

  ```python
  x = "global x"

  def outer_function():
      x = "enclosing x"

      def inner_function():
          x = "local x"
          print(x)  # Prints "local x"

      inner_function()
      print(x)  # Prints "enclosing x"

  outer_function()
  print(x)  # Prints "global x"
  ```

