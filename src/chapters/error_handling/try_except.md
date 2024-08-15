# Try-Except Blocks

Try-except blocks handle exceptions and errors that occur during program execution, allowing you to manage unexpected situations and ensure that your program can recover gracefully.

### Basic Structure

1. **Try Block**: Contains code that might raise an exception.

   ```python
   try:
       # Code that may raise an exception
       result = 10 / 0
   ```

2. **Except Block**: Contains code that executes if an exception occurs in the try block.

   ```python
   except ZeroDivisionError:
       # Code to handle the exception
       print("Cannot divide by zero.")
   ```

### Example

   ```python
   try:
       number = int(input("Enter a number: "))
       result = 10 / number
   except ValueError:
       print("Invalid input; please enter an integer.")
   except ZeroDivisionError:
       print("Cannot divide by zero.")
   except Exception as e:
       print(f"An unexpected error occurred: {e}")
   ```

### Multiple Except Blocks

Handle different types of exceptions with multiple except blocks.

   ```python
   try:
       # Code that may raise multiple exceptions
       value = int("not a number")
   except ValueError:
       print("ValueError: Invalid input.")
   except TypeError:
       print("TypeError: Incorrect type.")
   ```

### Finally Block

(Optional) Executes code regardless of whether an exception occurred or not, often used for cleanup.

   ```python
   try:
       file = open("file.txt", "r")
       # Code to read file
   except FileNotFoundError:
       print("File not found.")
   finally:
       file.close()  # Ensure file is closed
   ```

### Else Block

(Optional) Executes code if no exception occurs in the try block.

   ```python
   try:
       result = 10 / 2
   except ZeroDivisionError:
       print("Cannot divide by zero.")
   else:
       print(f"Division successful, result is {result}.")
   ```

### Conclusion

Try-except blocks are crucial for robust error handling in Python. They help manage exceptions gracefully, ensuring that your program can handle errors without crashing and perform necessary cleanup or alternative actions.

