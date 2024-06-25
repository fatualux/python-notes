# Floating Point Numbers

Floating point numbers, or floats, represent real numbers with decimal points. They are essential for calculations requiring precision, such as scientific computations, financial calculations, and more.

### Characteristics of Floating Point Numbers

- **Precision**: Floats have limited precision due to their binary representation. This can lead to small rounding errors in calculations.
- **Range**: Floats can represent very large and very small numbers, but their precision decreases as the numbers grow larger or smaller.

### Floating Point Operations

1. **Arithmetic Operations**:
   - **Addition**: Adds two floating point numbers.
     ```
     result = 5.5 + 3.2  # result is 8.7
     ```
   - **Subtraction**: Subtracts one float from another.
     ```
     result = 5.5 - 3.2  # result is 2.3
     ```
   - **Multiplication**: Multiplies two floating point numbers.
     ```
     result = 5.5 * 3.2  # result is 17.6
     ```
   - **Division**: Divides one float by another.
     ```
     result = 5.5 / 2.2  # result is 2.5
     ```
   - **Exponentiation**: Raises one float to the power of another.
     ```
     result = 5.5 ** 2  # result is 30.25
     ```

2. **Comparison Operations**:
   - **Equal**: Checks if two floats are equal.
     ```
     result = (5.5 == 5.5)  # result is True
     ```
   - **Not Equal**: Checks if two floats are not equal.
     ```
     result = (5.5 != 3.2)  # result is True
     ```
   - **Greater Than**: Checks if one float is greater than another.
     ```
     result = (5.5 > 3.2)  # result is True
     ```
   - **Less Than**: Checks if one float is less than another.
     ```
     result = (5.5 < 3.2)  # result is False
     ```
   - **Greater Than or Equal To**: Checks if one float is greater than or equal to another.
     ```
     result = (5.5 >= 5.5)  # result is True
     ```
   - **Less Than or Equal To**: Checks if one float is less than or equal to another.
     ```
     result = (5.5 <= 5.5)  # result is True
     ```

### Rounding Errors

Due to the way floating point numbers are represented in binary, some numbers cannot be represented exactly, leading to rounding errors.

  ```
  result = 0.1 + 0.2  # result might be 0.30000000000000004, not 0.3
  ```

### Formatting Floating Point Numbers

To control the number of decimal places displayed, you can format floats using string formatting.

  ```
  result = 5.6789
  formatted_result = "{:.2f}".format(result)  # formatted_result is "5.68"
  ```

### Type Conversion

- **Converting to Float**: Use the `float()` function to convert integers or strings to a float.
  
  ```
  result = float(5)       # result is 5.0
  result = float("5.7")   # result is 5.7
  ```

- **Converting to Integer**: Use the `int()` function to convert a float to an integer (truncates the decimal part).

  ```
  result = int(5.7)  # result is 5
  ```

