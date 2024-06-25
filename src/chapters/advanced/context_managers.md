# Context Managers

![Context Managers](../../static/images/context_managers.png)

Context managers in Python are used to manage resources such as files, network connections, or locks. They ensure that resources are properly acquired and released, even if errors occur during their use. The `with` statement is commonly used to work with context managers, automatically handling setup and teardown tasks.

### The `with` Statement

The `with` statement simplifies resource management by ensuring that the resource is automatically cleaned up after use. This is particularly useful for managing file I/O, database connections, and more.

- **Basic Syntax**:
  ```python
  with context_manager as resource:
      # Use the resource
  # Resource is automatically cleaned up here
  ```

- **Example**:
  ```python
  with open("example.txt", "r") as file:
      content = file.read()
  # File is automatically closed after this block
  ```

### Creating Custom Context Managers

You can create custom context managers by defining a class with `__enter__()` and `__exit__()` methods or by using the `contextlib` module.

1. **Using a Class**:
   - Define `__enter__()` to acquire the resource and `__exit__()` to release it.
   - Example:
     ```python
     class MyContextManager:
         def __enter__(self):
             print("Entering context")
             return self

         def __exit__(self, exc_type, exc_value, traceback):
             print("Exiting context")

     with MyContextManager() as manager:
         print("Inside the context")
     # Output:
     # Entering context
     # Inside the context
     # Exiting context
     ```

2. **Using the `contextlib` Module**:
   - The `contextlib` module provides a decorator to create context managers using generator functions.
   - Example:
     ```python
     from contextlib import contextmanager

     @contextmanager
     def my_context():
         print("Entering context")
         yield
         print("Exiting context")

     with my_context():
         print("Inside the context")
     # Output:
     # Entering context
     # Inside the context
     # Exiting context
     ```

### Practical Examples

1. **File Handling with Context Manager**:
   - Automatically handles file closing.
   - Example:
     ```python
     with open("example.txt", "w") as file:
         file.write("Hello, World!")
     # No need to explicitly close the file
     ```

2. **Managing Database Connections**:
   - Ensures that the database connection is closed after use.
   - Example:
     ```python
     import sqlite3

     with sqlite3.connect("database.db") as conn:
         cursor = conn.cursor()
         cursor.execute("SELECT * FROM table_name")
         results = cursor.fetchall()
     # Connection is automatically closed
     ```

3. **Thread Locks**:
   - Simplifies lock management in multithreading.
   - Example:
     ```python
     from threading import Lock

     lock = Lock()

     with lock:
         # Critical section of code
         print("Lock is acquired")
     # Lock is released here
     ```

### Handling Exceptions in Context Managers

Context managers can handle exceptions that occur within the `with` block using the `__exit__()` method.

- **Example**:
  ```python
  class MyContextManager:
      def __enter__(self):
          print("Entering context")
          return self

      def __exit__(self, exc_type, exc_value, traceback):
          if exc_type:
              print(f"An exception occurred: {exc_value}")
          print("Exiting context")

  with MyContextManager():
      raise ValueError("Something went wrong")
  # Output:
  # Entering context
  # An exception occurred: Something went wrong
  # Exiting context
  ```

### Conclusion

Context managers are a powerful feature in Python that help manage resources efficiently and safely. By using the `with` statement or creating custom context managers, you can ensure that resources are properly handled, reducing the risk of resource leaks and improving the reliability of your code.

