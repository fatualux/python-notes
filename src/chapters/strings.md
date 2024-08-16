# Strings

![Strings](../static/images/strings.png)

In Python, strings are sequences of characters enclosed in quotation marks. They can be defined using single quotes, double quotes, or triple quotes. Each type of quoting has its use cases and characteristics.

## Key Concepts of Strings in Python

- **String Definition**:
  Strings can be defined using single quotes (`'`), double quotes (`"`), or triple quotes (`'''` or `"""`). Triple quotes are used for multi-line strings.

  ```python
  single_quote = 'Wolf'  # Single quotes
  double_quote = "Wolf"  # Double quotes
  multi_line = '''A Wolf
  is howling'''  # Triple quotes for multi-line strings
  escaped_multi_line = 'this\nalso\nproduces\na multiline\nstring'  # Escape characters for new lines
  ```

- **String Operations**:
  Strings support various operations such as concatenation, repetition, and slicing.

  ```python
  # Concatenation
  greeting = "Hello, " + "world!"  # Output: "Hello, world!"

  # Repetition
  repeat = "Ha" * 3  # Output: "HaHaHa"

  # Slicing
  word = "Python"
  first_two = word[:2]  # Output: "Py"
  last_three = word[-3:]  # Output: "hon"
  ```

- **String Methods**:
  Python provides numerous methods to manipulate strings, such as `lower()`, `upper()`, `strip()`, `replace()`, and `split()`.

  ```python
  text = "  Hello, World!  "
  lower_text = text.lower()  # Output: "  hello, world!  "
  upper_text = text.upper()  # Output: "  HELLO, WORLD!  "
  stripped_text = text.strip()  # Output: "Hello, World!"
  replaced_text = text.replace("World", "Python")  # Output: "  Hello, Python!  "
  words = text.split()  # Output: ['Hello,', 'World!']
  ```

- **String Formatting**:
  Strings can be formatted using f-strings (Python 3.6+), `format()` method, or the `%` operator.

  ```python
  # f-strings (Python 3.6+)
  name = "Alice"
  age = 30
  formatted = f"Name: {name}, Age: {age}"  # Output: "Name: Alice, Age: 30"

  # format() method
  formatted = "Name: {}, Age: {}".format(name, age)  # Output: "Name: Alice, Age: 30"

  # % operator
  formatted = "Name: %s, Age: %d" % (name, age)  # Output: "Name: Alice, Age: 30"
  ```

- **Escape Characters**:
  To include special characters in strings, use escape sequences. Common escape characters include `\n` (new line), `\t` (tab), `\\` (backslash), and `\"` (double quote).

  ```python
  escaped_string = "This is a line.\nThis is another line.\n\tThis is indented."  # Output: "This is a line.\nThis is another line.\n\tThis is indented."
  ```

- **Raw Strings**:
  Raw strings treat backslashes as literal characters and do not interpret them as escape characters. Use `r` or `R` prefix for raw strings.

  ```python
  raw_string = r"C:\Users\Name\Path"  # Output: "C:\Users\Name\Path"
  ```

- **String Indexing**:
  Strings are indexed sequences, and each character in the string can be accessed using its index. Indexing starts at 0 for the first character.

  ```python
  word = "Python"
  first_char = word[0]  # Output: "P"
  last_char = word[-1]  # Output: "n"
  ```

- **Multiline Strings**:
  Triple quotes are used to define strings that span multiple lines. They preserve line breaks and formatting.

  ```python
  multiline = """This is a string
  that spans multiple lines
  and preserves line breaks."""
  ```

- **String Immutability**:
  Strings in Python are immutable, meaning once created, they cannot be modified. Any operation that alters a string will create a new string.

  ```python
  original = "Hello"
  modified = original.replace("H", "J")  # Output: "Jello"
  ```
