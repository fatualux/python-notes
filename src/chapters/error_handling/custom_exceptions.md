# Custom Exceptions

Custom exceptions allow you to define your own error types to represent specific error conditions in your program. They help make error handling more precise and meaningful.

### Creating Custom Exceptions

1. **Define a Custom Exception Class**: Inherit from the built-in `Exception` class or one of its subclasses.

   ```python
   class MyCustomError(Exception):
       def __init__(self, message):
           super().__init__(message)
           self.message = message
   ```

2. **Raise a Custom Exception**: Use the `raise` keyword to trigger the custom exception in your code.

   ```python
   def divide(x, y):
       if y == 0:
           raise MyCustomError("Cannot divide by zero.")
       return x / y

   try:
       result = divide(10, 0)
   except MyCustomError as e:
       print(f"Error: {e.message}")
   ```

### Adding Additional Functionality

You can extend custom exceptions with additional attributes or methods to provide more context.

   ```python
   class DetailedError(Exception):
       def __init__(self, message, error_code):
           super().__init__(message)
           self.message = message
           self.error_code = error_code

   def process_data(data):
       if not data:
           raise DetailedError("No data provided.", 404)

   try:
       process_data(None)
   except DetailedError as e:
       print(f"Error: {e.message}, Code: {e.error_code}")
   ```

### Best Practices

- **Inherit from `Exception`**: Ensure your custom exception inherits from `Exception` or a more specific built-in exception.
- **Provide Meaningful Messages**: Use descriptive messages to make the exception informative.
- **Document Custom Exceptions**: Clearly document when and why to use each custom exception.

### Conclusion

Custom exceptions enhance error handling by allowing you to define and manage specific error conditions in a more controlled and descriptive manner. They provide better context for errors and make your codebase more maintainable.

