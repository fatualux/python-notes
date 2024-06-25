# Decorators

![Decorators](../../static/images/decorators.png)

Decorators in Python are a powerful and flexible tool that allow you to modify the behavior of functions or methods without changing their actual code. They are often used to add functionality such as logging, access control, memoization, or instrumentation to existing functions in a clean, readable, and reusable way.

### Basic Syntax

A decorator is a function that wraps another function. The basic syntax is:

```python
def decorator_function(original_function):
    def wrapper_function(*args, **kwargs):
        # Code before the function call
        result = original_function(*args, **kwargs)
        # Code after the function call
        return result
    return wrapper_function
```

- **`original_function`**: The function being decorated.
- **`wrapper_function`**: The function that wraps around the original function, adding additional behavior before and after it.

### Applying a Decorator

You can apply a decorator to a function using the `@` symbol before the function definition.

- Example:
  ```python
  def my_decorator(func):
      def wrapper():
          print("Something before the function.")
          func()
          print("Something after the function.")
      return wrapper

  @my_decorator
  def say_hello():
      print("Hello!")

  say_hello()
  # Output:
  # Something before the function.
  # Hello!
  # Something after the function.
  ```

### Decorators with Arguments

Decorators can also accept arguments, allowing you to customize their behavior.

- Example:
  ```python
  def repeat(num_times):
      def decorator_repeat(func):
          def wrapper(*args, **kwargs):
              for _ in range(num_times):
                  result = func(*args, **kwargs)
              return result
          return wrapper
      return decorator_repeat

  @repeat(num_times=3)
  def greet(name):
      print(f"Hello, {name}!")

  greet("Alice")
  # Output:
  # Hello, Alice!
  # Hello, Alice!
  # Hello, Alice!
  ```

### Common Use Cases

1. **Logging**:
   - Automatically log information about function calls.
   ```python
   def log_function_call(func):
       def wrapper(*args, **kwargs):
           print(f"Calling {func.__name__} with {args} and {kwargs}")
           return func(*args, **kwargs)
       return wrapper

   @log_function_call
   def add(x, y):
       return x + y

   result = add(3, 5)
   # Output: Calling add with (3, 5) and {}
   ```

2. **Access Control/Authentication**:
   - Control access to certain functions based on user permissions.
   ```python
   def require_permission(permission):
       def decorator(func):
           def wrapper(*args, **kwargs):
               if not user_has_permission(permission):
                   raise PermissionError(f"User lacks {permission} permission")
               return func(*args, **kwargs)
           return wrapper
       return decorator

   @require_permission("admin")
   def delete_user(user_id):
       print(f"User {user_id} deleted.")
   ```

3. **Memoization**:
   - Cache the results of expensive function calls to improve performance.
   ```python
   def memoize(func):
       cache = {}
       def wrapper(*args):
           if args not in cache:
               cache[args] = func(*args)
           return cache[args]
       return wrapper

   @memoize
   def fibonacci(n):
       if n in [0, 1

