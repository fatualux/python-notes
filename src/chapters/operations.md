# Operations with Numbers

![Operations](../static/images/operations.png)

In Python, various operators are used to perform mathematical operations on numbers. Here’s a breakdown of the common operators and their usage:

| Operator | Meaning                                | Example   | Output |
|----------|----------------------------------------|-----------|--------|
| `+`      | Addition                                | `1 + 1`   | 2      |
| `-`      | Subtraction                             | `1 - 1`   | 0      |
| `*`      | Multiplication                          | `1 * 1`   | 1      |
| `/`      | True Division (returns a float)         | `9 / 5`   | 1.8    |
| `//`     | Floor Division (integer division)       | `9 // 5`  | 1      |
| `**`     | Exponentiation (power)                  | `2 ** 3`  | 8      |
| `%`      | Modulo (remainder of division)          | `10 % 3`  | 1      |

## Key Concepts of Number Operations in Python

- **Addition (`+`)**:
  Adds two numbers together and returns the sum.

  ```python
  result = 5 + 3  # Output: 8
  ```

- **Subtraction (`-`)**:
  Subtracts the second number from the first and returns the difference.

  ```python
  result = 10 - 4  # Output: 6
  ```

- **Multiplication (`*`)**:
  Multiplies two numbers and returns the product.

  ```python
  result = 7 * 6  # Output: 42
  ```

- **True Division (`/`)**:
  Divides the first number by the second, always returning a float.

  ```python
  result = 9 / 4  # Output: 2.25
  ```

- **Floor Division (`//`)**:
  Divides the first number by the second and returns the largest integer less than or equal to the result.

  ```python
  result = 9 // 4  # Output: 2
  ```

- **Exponentiation (`**`)**:
  Raises the first number to the power of the second number and returns the result.

  ```python
  result = 3 ** 4  # Output: 81
  ```

- **Modulo (`%`)**:
  Returns the remainder of the division of the first number by the second number.

  ```python
  result = 10 % 3  # Output: 1
  ```

- **Combination of Operations**:
  Python supports combining multiple operations in a single expression, with standard precedence rules.

  ```python
  result = (2 + 3) * (5 ** 2) / 4  # Output: 31.25
  ```

- **Order of Operations**:
  Python follows the standard order of operations (PEMDAS/BODMAS) where Parentheses/Brackets, Exponents/Orders, Multiplication and Division, and Addition and Subtraction are performed in that order.

  ```python
  result = 3 + 2 * (8 / 4) ** 2  # Output: 11.0
  ```

- **Type Conversion**:
  Operations between different numeric types (e.g., integer and float) result in a float. Explicit type conversion can be performed using `int()`, `float()`, etc.

  ```python
  int_result = int(7 / 3)  # Output: 2
  float_result = float(7 // 3)  # Output: 2.0
  ```

