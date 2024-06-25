# Numbers

![Numbers](../static/images/numbers.png)

In Python, **numbers** are divided into two main types: **integers** and **floats** (real numbers). These types are used for performing arithmetic operations and representing numerical values.

## Key Concepts of Numbers in Python

- **Integers**:
  Integers are whole numbers without a fractional component. They can be positive, negative, or zero.

  ```python
  num1 = 10
  num2 = -5
  num3 = 0

  print(type(num1))  # Output: <class 'int'>
  ```

- **Floats**:
  Floats represent real numbers and include a decimal point. They can be used to represent fractions or floating-point arithmetic.

  ```python
  num1 = 3.14
  num2 = -0.001
  num3 = 2.0

  print(type(num1))  # Output: <class 'float'>
  ```

- **Type Conversion**:
  You can convert between integers and floats using type conversion functions like `int()` and `float()`.

  ```python
  int_value = 7
  float_value = 3.14

  converted_float = float(int_value)  # 7.0
  converted_int = int(float_value)    # 3
  ```

- **Precision and Rounding**:
  Floating-point numbers may have precision issues. Python provides the `round()` function to round floats to a specified number of decimal places.

  ```python
  pi = 3.14159
  rounded_pi = round(pi, 2)  # 3.14
  ```

- **Complex Numbers**:
  Python also supports complex numbers, which have a real and an imaginary part. They are defined with a `j` suffix for the imaginary part.

  ```python
  complex_num = 4 + 5j
  real_part = complex_num.real   # 4.0
  imag_part = complex_num.imag   # 5.0
  ```

- **Mathematical Functions**:
  Python's `math` module provides functions for more advanced mathematical operations.

  ```python
  import math

  square_root = math.sqrt(16)   # 4.0
  power = math.pow(2, 3)        # 8.0
  log_value = math.log(100)     # 4.605170185988092
  ```

- **Special Numeric Values**:
  Python has special constants such as `inf` (infinity) and `NaN` (not a number) for handling exceptional numeric cases.

  ```python
  infinity = float('inf')
  nan_value = float('nan')

  print(infinity)  # inf
  print(nan_value) # nan
  ```

