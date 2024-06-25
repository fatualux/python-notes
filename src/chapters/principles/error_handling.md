# Error Handling

Error handling is crucial for creating robust and reliable software. It involves anticipating potential issues and managing them gracefully to prevent the application from crashing and to provide useful feedback to users.

### Basic Concepts

- **Exceptions**: An exception is an event that disrupts the normal flow of a program. Python uses exceptions to signal errors.
- **Try-Except Block**: This block is used to catch and handle exceptions that occur during the execution of code.

### Syntax

```python
try:
    # Code that might raise an exception
except SomeException as e:
    # Code that runs if an exception occurs
finally:
    # Code that always runs, regardless of whether an exception occurred
```

### Types of Exceptions

- **Built-in Exceptions**: Python provides a range of built-in exceptions, such as `ValueError`, `TypeError`, and `FileNotFoundError`.
- **Custom Exceptions**: You can define your own exceptions by subclassing the `Exception` class.

### ValueError Example
```python
def square_root(x):
    if x < 0:
        raise ValueError("Cannot compute square root of a negative number.")
    return x ** 0.5

try:
    result = square_root(-9)
except ValueError as e:
    print(f"ValueError: {e}")
```

### TypeError Example
```python
def add(a, b):
    return a + b

try:
    result = add(5, "10")
except TypeError as e:
    print(f"TypeError: {e}")
```

### FileNotFoundError Example
```python
try:
    with open("non_existent_file.txt", "r") as file:
        content = file.read()
except FileNotFoundError as e:
    print(f"FileNotFoundError: {e}")
```

### Best Practices

1. **Catch Specific Exceptions**: Handle specific exceptions rather than using a generic `except` clause to avoid masking other issues.

   ```python
   try:
       # Code that might raise an exception
   except ValueError:
       # Handle ValueError specifically
   except TypeError:
       # Handle TypeError specifically
   ```

2. **Use Finally for Cleanup**: Use the `finally` block to ensure that cleanup actions, such as closing files or releasing resources, are executed.

   ```python
   try:
       file = open('file.txt', 'r')
       # Read from the file
   except IOError as e:
       print(f"An error occurred: {e}")
   finally:
       file.close()  # Ensure the file is closed
   ```

3. **Log Exceptions**: Use logging to record exceptions and provide detailed information for debugging.

   ```python
   import logging

   try:
       # Code that might raise an exception
   except Exception as e:
       logging.error(f"An error occurred: {e}")
   ```

4. **Avoid Bare Excepts**: Avoid using bare `except:` clauses, as they can catch unexpected exceptions and make debugging difficult.

   ```python
   try:
       # Code that might raise an exception
   except:
       # Avoid this; it catches all exceptions
   ```

5. **Reraise Exceptions if Necessary**: Sometimes, it's useful to catch an exception, perform some action, and then re-raise the exception to be handled further up the call stack.

   ```python
   try:
       # Code that might raise an exception
   except ValueError as e:
       # Handle the exception
       raise  # Reraise the exception
   ```

### Conclusion

Proper error handling ensures that your application can gracefully manage unexpected situations, providing a better user experience and making it easier to maintain and debug your code.

