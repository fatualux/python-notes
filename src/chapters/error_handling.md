# Error Handling

![Error Handling](../../static/images/error_handling.png)

Error handling in Python is the process of responding to the occurrence of exceptions—errors that arise during the execution of a program. Proper error handling ensures that your program can manage unexpected situations gracefully without crashing.

### Types of Errors

1. **Syntax Errors**:
   - Occur when the Python parser detects incorrect syntax.
   - Example:
     ```
     if True
         print("Syntax Error")
     # Missing colon (:) causes a SyntaxError
     ```

2. **Runtime Errors**:
   - Occur during execution and are also known as exceptions.
   - Example:
     ```
     x = 1 / 0
     # Raises a ZeroDivisionError at runtime
     ```

3. **Logical Errors**:
   - Occur when the code doesn't do what the programmer intended, but it doesn't cause an error or exception.
   - Example:
     ```
     result = 2 + 2
     print(result)
     # Incorrectly assuming result will be 5, but it outputs 4
     ```

### The `try-except` Block

The `try-except` block is the primary way to handle exceptions in Python. It allows you to "try" a block of code and "except" (catch) any exceptions that occur, preventing the program from crashing.

- **Basic Syntax**:
  ```
  try:
      # Code that may raise an exception
  except ExceptionType:
      # Code to execute if an exception occurs
  ```

- **Example**:
  ```
  try:
      x = 1 / 0
  except ZeroDivisionError:
      print("Cannot divide by zero.")
  # Output: Cannot divide by zero.
  ```

### Catching Multiple Exceptions

You can handle multiple exceptions by specifying them in a tuple within the `except` clause.

- **Example**:
  ```
  try:
      value = int(input("Enter a number: "))
      result = 10 / value
  except (ValueError, ZeroDivisionError) as e:
      print(f"An error occurred: {e}")
  # Handles both ValueError (if input is not a number) and ZeroDivisionError
  ```

### The `else` Clause

The `else` clause can be used with the `try-except` block to define code that should run if no exceptions are raised.

- **Example**:
  ```
  try:
      result = 10 / 2
  except ZeroDivisionError:
      print("Cannot divide by zero.")
  else:
      print(f"Result is {result}")
  # Output: Result is 5.0
  ```

### The `finally` Clause

The `finally` clause allows you to execute code regardless of whether an exception was raised or not. It's often used for cleanup actions.

- **Example**:
  ```
  try:
      file = open("example.txt", "r")
      content = file.read()
  except FileNotFoundError:
      print("File not found.")
  finally:
      file.close()
      print("File closed.")
  # Output: "File closed." is printed whether or not an exception occurs.
  ```

### Raising Exceptions

You can raise exceptions manually using the `raise` keyword if you want to enforce certain conditions in your code.

- **Example**:
  ```
  def divide(a, b):
      if b == 0:
          raise ValueError("b cannot be zero.")
      return a / b

  try:
      divide(10, 0)
  except ValueError as e:
      print(e)
  # Output: b cannot be zero.
  ```

### Custom Exceptions

You can define custom exceptions by creating a new class that inherits from the `Exception` class. This is useful when you need to handle specific types of errors in your application.

- **Example**:
  ```
  class NegativeNumberError(Exception):
      pass

  def check_positive(number):
      if number < 0:
          raise NegativeNumberError("Number cannot be negative.")

  try:
      check_positive(-5)
  except NegativeNumberError as e:
      print(e)
  # Output: Number cannot be negative.
  ```

### Conclusion

Error handling is an essential part of writing robust and reliable Python code. By understanding how to use `try-except` blocks, handle multiple exceptions, and create custom exceptions, you can ensure that your programs are resilient and user-friendly, even when unexpected situations arise.

