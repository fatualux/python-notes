# File Operations

Python provides several built-in functions to perform basic file operations, such as opening, reading, writing, and closing files.

1. **Opening a File**:
   - Use the `open()` function to open a file. The `open()` function returns a file object, which allows you to interact with the file.
   - Syntax:
     ```python
     file_object = open("filename", "mode")
     ```
   - Common modes include:
     - `'r'`: Read (default mode)
     - `'w'`: Write (creates a new file or truncates an existing file)
     - `'a'`: Append (writes to the end of the file without truncating)
     - `'b'`: Binary mode (used with other modes for binary files)

2. **Reading a File**:
   - **`read()`**: Reads the entire file content as a string.
   - **`readline()`**: Reads a single line from the file.
   - **`readlines()`**: Reads all lines and returns them as a list.
   - Example:
     ```python
     file = open("example.txt", "r")
     content = file.read()  # Reads entire file
     first_line = file.readline()  # Reads first line
     all_lines = file.readlines()  # Reads all lines as a list
     file.close()
     ```

3. **Writing to a File**:
   - **`write()`**: Writes a string to the file.
   - **`writelines()`**: Writes a list of strings to the file.
   - Example:
     ```python
     file = open("example.txt", "w")
     file.write("Hello, World!\n")
     lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
     file.writelines(lines)
     file.close()
     ```

4. **Appending to a File**:
   - Use `'a'` mode to append content to the end of the file without truncating it.
   - Example:
     ```python
     file = open("example.txt", "a")
     file.write("This line is appended.\n")
     file.close()
     ```

5. **Closing a File**:
   - Always close the file after performing operations to free system resources.
   - Example:
     ```python
     file = open("example.txt", "r")
     # Perform operations
     file.close()
     ```

### File Handling Using `with` Statement

Using the `with` statement is the preferred way to handle files in Python. It ensures that the file is properly closed after its suite finishes, even if an exception occurs.

- Example:
  ```python
  with open("example.txt", "r") as file:
      content = file.read()
  # The file is automatically closed after the block
  ```

### Working with Binary Files

To work with binary files, use the `'b'` mode along with the other modes. This is essential for non-text files like images, videos, and executables.

- Example:
  ```python
  with open("image.png", "rb") as binary_file:
      binary_data = binary_file.read()
  ```

### File Positioning

You can control the file's current position using `seek()` and check it with `tell()`.

- **`seek(offset, whence)`**: Moves the file pointer to a specific position.
  - `offset`: Number of bytes to move.
  - `whence`: Starting point (0 = start, 1 = current position, 2 = end).
  - Example:
    ```python
    file = open("example.txt", "r")
    file.seek(0)  # Move to the start of the file
    ```
- **`tell()`**: Returns the current file position.
  - Example:
    ```python
    position = file.tell()  # Get current file position
    ```

### Handling File Exceptions

File handling can raise exceptions, such as `FileNotFoundError` or `IOError`. It's important to handle these exceptions to prevent the program from crashing.

- Example:
  ```python
  try:
      file = open("nonexistent.txt", "r")
  except FileNotFoundError:
      print("File not found.")
  finally:
      file.close()
  ```

