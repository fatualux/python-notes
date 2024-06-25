# Namespaces

A **namespace** is a system that ensures the unique identification of names within a program. It acts as a container that holds a set of identifiers (names) and their associated objects, avoiding name conflicts and allowing for the organization of code.

![Namespaces](../static/images/namespaces.png)

## Types of Namespaces in Python

- **Local Namespace**:
  The local namespace is created within a function when it is called. It contains names defined in that function, including parameters and variables. These names are accessible only within that function.

  ```python
  def my_function():
      local_var = 5  # local_var is in the local namespace
      print(local_var)

  my_function()  # Output: 5
  # print(local_var)  # Raises a NameError because local_var is not accessible outside the function
  ```

- **Global Namespace**:
  The global namespace refers to the scope of the module or script. Names defined at the top level of a module or script are part of the global namespace. These names are accessible throughout the module.

  ```python
  global_var = "Hello, World!"  # global_var is in the global namespace

  def print_global():
      print(global_var)  # Accessing a global variable from within a function

  print_global()  # Output: Hello, World!
  ```

- **Built-in Namespace**:
  The built-in namespace contains names that are predefined in Python and available in any module. This includes built-in functions and exceptions, such as `len()`, `range()`, and `Exception`.

  ```python
  print(len("Python"))  # Output: 6
  print(range(5))       # Output: range(0, 5)
  ```

## Namespace Lookup Order

When accessing a name, Python follows the LEGB rule to look it up:
- **Local**: Searches the local namespace (current function or scope).
- **Enclosing**: Searches any enclosing functions or scopes.
- **Global**: Searches the global namespace (module-level).
- **Built-in**: Searches the built-in namespace.

  ```python
  def outer_function():
      outer_var = "outer"

      def inner_function():
          inner_var = "inner"
          print(inner_var)  # Local to inner_function
          print(outer_var)  # Enclosing scope

      inner_function()

  outer_function()
  # Output:
  # inner
  # outer
  ```

## Modifying Namespaces

You can modify the global namespace using the `global` keyword inside a function, which allows you to assign values to global variables.

  ```python
  global_var = "Original"

  def modify_global():
      global global_var
      global_var = "Modified"  # Modifying the global variable

  modify_global()
  print(global_var)  # Output: Modified
  ```

