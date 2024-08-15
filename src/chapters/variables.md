# Variables

In Python, a **variable** is a named storage location that holds data, which can be modified during the execution of the program. Variables are used to store values for later use and are created when a value is assigned to them using the assignment operator (`=`).

![Variables](../static/images/variables.png)

## Key Concepts of Variables in Python

- **Variable Assignment**:
  Variables are assigned using the `=` operator. The variable name is on the left side and the value on the right side of the operator.

  ```python
  x = 5  # Assigns the value 5 to the variable x
  name = "Francesco"  # Assigns the string "Francesco" to the variable name
  ```

- **Dynamic Typing**:
  Python is dynamically typed, meaning that variables do not need an explicit type declaration. The type of the variable is inferred from the value assigned to it.

  ```python
  x = 5  # Integer
  x = "Hello"  # Now x is a string
  ```

- **Variable Naming**:
  Variable names must follow these rules:
  - Begin with a letter or an underscore (`_`).
  - Followed by letters, digits, or underscores.
  - Case-sensitive (e.g., `variable`, `Variable`, and `VARIABLE` are different).

  ```python
  my_var = 10
  _private_var = 20
  variable1 = 30
  ```

- **Variable Scope**:
  Variables have different scopes:
  - **Local Scope**: Variables defined within a function.
  - **Global Scope**: Variables defined outside any function or class.

  ```python
  global_var = "I am global"

  def my_function():
      local_var = "I am local"
      print(global_var)  # Access global variable
      print(local_var)   # Access local variable
  ```

- **Reassignment**:
  Variables can be reassigned to new values of any type.

  ```python
  my_var = 10
  my_var = "Now I am a string"  # Reassignment to a string
  ```

- **Multiple Assignments**:
  You can assign a single value to multiple variables or multiple values to multiple variables in a single line.

  ```python
  a = b = c = 5  # Assigns 5 to a, b, and c
  x, y, z = 1, 2, 3  # Assigns 1 to x, 2 to y, and 3 to z
  ```

- **Data Types**:
  Variables can hold different types of data, including but not limited to integers, floats, strings, lists, tuples, and dictionaries.

  ```python
  my_list = [1, 2, 3]  # List
  my_tuple = (4, 5, 6)  # Tuple
  my_dict = {"key1": "value1", "key2": "value2"}  # Dictionary
  ```

- **Variable Deletion**:
  Variables can be deleted using the `del` statement, which removes the variable and its value from memory.

  ```python
  x = 10
  del x  # x is deleted and accessing it will raise an error
  ```

- **Type Conversion**:
  You can convert variables from one type to another using type conversion functions like `int()`, `float()`, `str()`, etc.

  ```python
  x = "123"
  y = int(x)  # Converts the string "123" to the integer 123
  z = float(y)  # Converts the integer 123 to the float 123.0
  ```

- **Constants**:
  Python does not have built-in constant types, but by convention, variables intended to be constants are written in uppercase.

  ```python
  PI = 3.14159  # Conventionally a constant
  ```

