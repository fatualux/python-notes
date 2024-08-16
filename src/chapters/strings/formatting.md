# String Formatting

String formatting in Python allows you to create well-structured and readable strings by embedding variables or expressions into them. It is a powerful tool for generating dynamic content and making your code more maintainable.

### Types of String Formatting

Python offers several ways to format strings:

1. **Old-Style Formatting (`%`)**:
   - This method uses the `%` operator to format strings.
   - Example:
     ```python
     name = "Alice"
     age = 30
     formatted_string = "Name: %s, Age: %d" % (name, age)
     # formatted_string is "Name: Alice, Age: 30"
     ```

2. **`str.format()` Method**:
   - The `str.format()` method allows you to insert values into placeholders `{}` in a string.
   - Example:
     ```python
     name = "Bob"
     age = 25
     formatted_string = "Name: {}, Age: {}".format(name, age)
     # formatted_string is "Name: Bob, Age: 25"
     ```
   - You can also specify the order of insertion or use named placeholders:
     ```python
     formatted_string = "Name: {0}, Age: {1}".format(name, age)
     formatted_string_named = "Name: {name}, Age: {age}".format(name="Charlie", age=28)
     # formatted_string_named is "Name: Charlie, Age: 28"
     ```

3. **F-Strings (Formatted String Literals)**:
   - Introduced in Python 3.6, f-strings provide a concise and readable way to format strings.
   - Example:
     ```python
     name = "Diana"
     age = 22
     formatted_string = f"Name: {name}, Age: {age}"
     # formatted_string is "Name: Diana, Age: 22"
     ```
   - F-strings also support expressions:
     ```python
     formatted_string = f"Next year, {name} will be {age + 1} years old."
     # formatted_string is "Next year, Diana will be 23 years old."
     ```

### Formatting Options

You can control the format of numbers, strings, and other data types with specific options:

- **Width and Alignment**:
  - Control the width and alignment of text within a formatted string.
  - Example:
    ```python
    formatted_string = f"{name:<10} | {age:^5} | {'Student':>10}"
    # formatted_string is "Diana      |  22  |    Student"
    ```

- **Number Formatting**:
  - Format numbers with specific precision, as decimals, or in scientific notation.
  - Example:
    ```python
    pi = 3.14159
    formatted_string = f"Pi to 2 decimal places: {pi:.2f}"
    # formatted_string is "Pi to 2 decimal places: 3.14"
    ```

- **Thousands Separator**:
  - Add commas or other separators to large numbers.
  - Example:
    ```python
    large_number = 1000000
    formatted_string = f"{large_number:,}"
    # formatted_string is "1,000,000"
    ```

- **String Formatting with Dictionaries**:
  - You can use dictionaries to pass multiple values to format strings.
  - Example:
    ```python
    data = {"name": "Eve", "age": 27}
    formatted_string = "Name: {name}, Age: {age}".format(**data)
    # formatted_string is "Name: Eve, Age: 27"
    ```

### Escaping Braces

If you need to include braces `{}` in your string without them being interpreted as placeholders, you can escape them by doubling:

  ```python
  formatted_string = f"{{Escaped braces}} and {{name}}"
  # formatted_string is "{Escaped braces} and {name}"
  ```

