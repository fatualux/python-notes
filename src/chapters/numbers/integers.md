# Integers

Integers are a fundamental data type in Python, representing whole numbers (both positive and negative) without any fractional component. They are widely used in programming for counting, indexing, and performing various arithmetic operations.

### Integer Operations

1. **Arithmetic Operations**:
   - **Addition**: Adds two integers.
     ```
     result = 5 + 3  # result is 8
     ```
   - **Subtraction**: Subtracts one integer from another.
     ```
     result = 5 - 3  # result is 2
     ```
   - **Multiplication**: Multiplies two integers.
     ```
     result = 5 * 3  # result is 15
     ```
   - **Division**: Divides one integer by another (results in a float).
     ```
     result = 5 / 2  # result is 2.5
     ```
   - **Floor Division**: Divides and returns the integer part of the quotient.
     ```
     result = 5 // 2  # result is 2
     ```
   - **Modulus**: Returns the remainder of the division.
     ```
     result = 5 % 2  # result is 1
     ```
   - **Exponentiation**: Raises one integer to the power of another.
     ```
     result = 5 ** 3  # result is 125
     ```

2. **Comparison Operations**:
   - **Equal**: Checks if two integers are equal.
     ```
     result = (5 == 3)  # result is False
     ```
   - **Not Equal**: Checks if two integers are not equal.
     ```
     result = (5 != 3)  # result is True
     ```
   - **Greater Than**: Checks if one integer is greater than another.
     ```
     result = (5 > 3)  # result is True
     ```
   - **Less Than**: Checks if one integer is less than another.
     ```
     result = (5 < 3)  # result is False
     ```
   - **Greater Than or Equal To**: Checks if one integer is greater than or equal to another.
     ```
     result = (5 >= 3)  # result is True
     ```
   - **Less Than or Equal To**: Checks if one integer is less than or equal to another.
     ```
     result = (5 <= 3)  # result is False
     ```

### Type Conversion

- **Converting to Integer**: Use the `int()` function to convert a float or a string to an integer. If converting a float, it truncates the decimal part.

  ```
  result = int(3.7)   # result is 3
  result = int("5")   # result is 5
  ```

- **Converting to String**: Use the `str()` function to convert an integer to a string.

  ```
  result = str(5)  # result is "5"
  ```

### Working with Large Integers

Python's integers can handle arbitrarily large values, limited only by the available memory.

  ```
  large_int = 123456789012345678901234567890

