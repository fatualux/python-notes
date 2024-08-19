# Scopes

A **scope** is the textual region of a Python program where a namespace is directly accessible. In other words, a scope defines the areas of a program where variables can be accessed or modified.

![Scopes](../static/images/scopes.png)

## Key Concepts of Scopes in Python

- **Local Scope**:
  Variables defined inside a function have a local scope. These variables are accessible only within that function.

  ```python
  def my_function():
      local_var = "I am local"  # Local scope
      print(local_var)  # Output: I am local
  ```

- **Global Scope**:
  Variables defined outside of any function or class have a global scope. These variables are accessible from anywhere in the module after their definition.

  ```python
  global_var = "I am global"  # Global scope

  def my_function():
      print(global_var)  # Output: I am global
  ```

- **Enclosing Scope**:
  Variables defined in a containing (enclosing) function's scope are accessible in nested functions but not vice versa.

  ```python
  def outer_function():
      enclosing_var = "I am enclosing"

      def inner_function():
          print(enclosing_var)  # Accesses the variable from the enclosing scope
      inner_function()
  ```

- **Built-in Scope**:
  This is the scope of Python's built-in functions and exceptions. It is the broadest scope and is accessible anywhere in the code.

  ```python
  print(len("example"))  # len() is a built-in function
  ```

- **Global Keyword**:
  The `global` keyword allows you to modify a global variable inside a function.

  ```python
  counter = 0

  def increment():
      global counter
      counter += 1
  ```

- **Nonlocal Keyword**:
  The `nonlocal` keyword allows you to modify a variable in an enclosing (non-global) scope.

  ```python
  def outer_function():
      count = 0

      def inner_function():
          nonlocal count
          count += 1
      inner_function()
      return count
  ```

- **Namespace**:
  A namespace is a mapping from names to objects. Different scopes correspond to different namespaces.

  ```python
  x = 10  # Global namespace

  def my_function():
      x = 5  # Local namespace
      print(x)  # Output: 5
  ```

- **Scope Resolution (LEGB Rule)**:
  Python uses the LEGB rule to resolve variable names:
  - **L**ocal: The innermost scope (local function scope).
  - **E**nclosing: The scope of any enclosing functions.
  - **G**lobal: The top-level scope of the module.
  - **B**uilt-in: The built-in scope.

  ```python
  x = 10  # Global scope

  def outer():
      x = 5  # Enclosing scope

      def inner():
          x = 2  # Local scope
          print(x)  # Output: 2
      inner()
      print(x)  # Output: 5
  outer()
  print(x)  # Output: 10
  ```

