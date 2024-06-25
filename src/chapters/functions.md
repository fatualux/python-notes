# Functions

In Python, a **function** is a block of organized code that is used to perform an action. 

![Functions](../static/images/functions.png)

Functions provide better modularity for applications and a high degree of code reusing, in compliance with the DRY (Don't Repeat Yourself) principle.

Functions names, if made up of several words (compound names), are separated by underscores (e.g. `my_function()`)

They can take parameters (inputs), perform some operations, and optionally return a value.

## Key Concepts of Functions in Python

- **Function Definition**:
  A function is defined using the `def` keyword, followed by the function name, parameters (if any) enclosed in parentheses, and a colon. The function body is indented and contains the code to execute.

  ```python
  def function_name(parameters):
      # function body
      pass
  ```

- **Function Example**:
  Here’s a simple example of a function that adds two numbers:

  ```python
  def add_numbers(a, b):
      """Add two numbers and return the result."""
      return a + b

  result = add_numbers(1, 2)  # Output: 3
  ```

- **Parameters and Arguments**:
  Functions can take parameters, which are inputs that the function can use to perform its task.
  When calling the function, the actual values passed are called arguments.

  ```python
  def greet(name):
      """Greet a person by their name."""
      print(f"Hello, {name}!")

  greet("Isabel")  # Output: Hello, Isabel!
  ```

- **Return Statement**:
  The `return` statement is used to exit a function and optionally pass an expression back to the caller. If no `return` statement is present, the function returns `None` by default.

  ```python
  def square(number):
      """Return the square of a number."""
      return number * number

  result = square(4)  # Output: 16
  ```

- **Default Parameters**:
  Functions can have default parameter values, which are used if no argument is provided for that parameter when the function is called.

  ```python
  def greet(name="Guest"):
      """Greet a person with a default name."""
      print(f"Hello, {name}!")

  greet()        # Output: Hello, Guest!
  greet("Bob")   # Output: Hello, Bob!
  ```

- **Keyword Arguments**:
  Functions can be called using keyword arguments, where the name of the parameter is explicitly stated.
  This allows arguments to be passed in any order.

  ```python
  def describe_pet(animal_type, pet_name):
      """Display information about a pet."""
      print(f"\nI have a {animal_type}.")
      print(f"My {animal_type}'s name is {pet_name}.")

  describe_pet(animal_type="dog", pet_name="Buddy")
  describe_pet(pet_name="Whiskers", animal_type="cat")
  ```

- **Variable-Length Arguments**:
  Python functions can accept an arbitrary number of arguments using `*args` (for non-keyword arguments) and `**kwargs` (for keyword arguments).

  ```python
  def make_pizza(size, *toppings):
      """Print the list of toppings that have been requested."""
      print(f"\nMaking a {size}-inch pizza with the following toppings:")
      for topping in toppings:
          print(f"- {topping}")

  make_pizza(16, "pepperoni", "mushrooms", "green peppers", "extra cheese")
  # Output: Making a 16-inch pizza with the following toppings:
  #         - pepperoni
  #         - mushrooms
  #         - green peppers
  #         - extra cheese
  ```

- **Docstrings**:
  Functions can include documentation strings (docstrings) to describe their purpose. These strings are written inside triple quotes `"""` and can be accessed using the function’s `__doc__` attribute.

  ```python
  def multiply(a, b):
      """Multiply two numbers and return the result."""
      return a * b

  print(multiply.__doc__)  # Output: Multiply two numbers and return the result.
  ```

- **Function Scope**:
  Variables defined inside a function are local to that function and cannot be accessed outside of it. This is known as the function's scope.

  ```python
  def my_function():
      x = 10  # x is local to my_function
      print(x)

  my_function()  # Output: 10
  # print(x)  # Raises a NameError because x is not accessible here
  ```

