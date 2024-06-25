# String Methods

String methods in Python are built-in functions that allow you to manipulate and analyze text data. These methods help you perform common operations such as searching, modifying, and formatting strings efficiently.

### Commonly Used String Methods

1. **`str.upper()` and `str.lower()`**:
   - Convert a string to uppercase or lowercase.
   - Example:
     ```python
     text = "Hello, World!"
     upper_text = text.upper()  # "HELLO, WORLD!"
     lower_text = text.lower()  # "hello, world!"
     ```

2. **`str.capitalize()` and `str.title()`**:
   - Capitalize the first letter of a string or capitalize the first letter of each word.
   - Example:
     ```python
     text = "hello, world!"
     capitalized_text = text.capitalize()  # "Hello, world!"
     title_text = text.title()  # "Hello, World!"
     ```

3. **`str.strip()`**, **`str.lstrip()`**, and **`str.rstrip()`**:
   - Remove leading and/or trailing whitespace (or other specified characters).
   - Example:
     ```python
     text = "   Hello, World!   "
     stripped_text = text.strip()  # "Hello, World!"
     left_stripped = text.lstrip()  # "Hello, World!   "
     right_stripped = text.rstrip()  # "   Hello, World!"
     ```

4. **`str.replace()`**:
   - Replace occurrences of a substring with another substring.
   - Example:
     ```python
     text = "Hello, World!"
     replaced_text = text.replace("World", "Python")  # "Hello, Python!"
     ```

5. **`str.split()` and `str.join()`**:
   - `split()`: Split a string into a list of substrings based on a delimiter.
   - `join()`: Join a list of strings into a single string with a specified delimiter.
   - Example:
     ```python
     text = "Hello, World!"
     words = text.split(", ")  # ["Hello", "World!"]
     joined_text = " - ".join(words)  # "Hello - World!"
     ```

6. **`str.find()` and `str.index()`**:
   - `find()`: Return the lowest index of the substring if found, otherwise return `-1`.
   - `index()`: Similar to `find()`, but raises a `ValueError` if the substring is not found.
   - Example:
     ```python
     text = "Hello, World!"
     index = text.find("World")  # 7
     # index_not_found = text.index("Python")  # Raises ValueError
     ```

7. **`str.startswith()` and `str.endswith()`**:
   - Check if a string starts or ends with a specified substring.
   - Example:
     ```python
     text = "Hello, World!"
     starts_with = text.startswith("Hello")  # True
     ends_with = text.endswith("World!")  # True
     ```

8. **`str.count()`**:
   - Count the number of occurrences of a substring in a string.
   - Example:
     ```python
     text = "Hello, World! Hello again!"
     count = text.count("Hello")  # 2
     ```

9. **`str.isalpha()`, `str.isdigit()`, and `str.isalnum()`**:
   - `isalpha()`: Check if the string consists only of alphabetic characters.
   - `isdigit()`: Check if the string consists only of digits.
   - `isalnum()`: Check if the string consists only of alphanumeric characters (letters and numbers).
   - Example:
     ```python
     text_alpha = "Hello"
     text_digit = "12345"
     text_alnum = "Hello123"
     is_alpha = text_alpha.isalpha()  # True
     is_digit = text_digit.isdigit()  # True
     is_alnum = text_alnum.isalnum()  # True
     ```

10. **`str.center()`, `str.ljust()`, and `str.rjust()`**:
    - Adjust the alignment of a string to be centered, left-justified, or right-justified within a given width.
    - Example:
      ```python
      text = "Hello"
      centered = text.center(10, "-")  # "--Hello---"
      left_justified = text.ljust(10, "-")  # "Hello-----"
      right_justified = text.rjust(10, "-")  # "-----Hello"
      ```

### Advanced String Methods

1. **`str.zfill()`**:
   - Pad a string on the left with zeros until it reaches the specified length.
   - Example:
     ```python
     text = "42"
     padded_text = text.zfill(5)  # "00042"
     ```

2. **`str.partition()` and `str.rpartition()`**:
   - Split the string into a tuple with three parts: the part before the separator, the separator itself, and the part after the separator.
   - Example:
     ```python
     text = "Hello, World!"
     parts = text.partition(", ")  # ("Hello", ", ", "World!")
     ```

3. **`str.casefold()`**:
   - Return a case-insensitive version of the string, useful for caseless matching.
   - Example:
     ```python
     text = "Hello, World!"
     casefolded_text = text.casefold()  # "hello, world!"
     ```

