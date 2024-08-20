# Error Types

These are the most common built in exceptions in Python.

| ERROR                    | EXPLANATION                                                                                  |
|--------------------------|----------------------------------------------------------------------------------------------|
| `ValueError`             | Raised when a function receives an argument of the right type but an inappropriate value.    |
| `TypeError`              | Raised when an operation or function is applied to an object of inappropriate type.          |
| `FileNotFoundError`      | Raised when trying to open a file that does not exist.                                       |
| `IndexError`             | Raised when trying to access an element from a list or tuple with an invalid index.          |
| `KeyError`               | Raised when trying to access a dictionary with a key that does not exist.                    |
| `AttributeError`         | Raised when an attribute reference or assignment fails.                                      |
| `ImportError`            | Raised when an import statement fails to find the module definition or when a `from ... import` fails. |
| `ModuleNotFoundError`    | Raised when a module could not be found.                                                     |
| `ZeroDivisionError`      | Raised when attempting to divide by zero.                                                    |
| `NameError`              | Raised when a local or global name is not found.                                             |
| `UnboundLocalError`      | Raised when trying to access a local variable before it has been assigned.                   |
| `SyntaxError`            | Raised when the parser encounters a syntax error.                                            |
| `IndentationError`       | Raised when there is an incorrect indentation.                                               |
| `TabError`               | Raised when mixing tabs and spaces in indentation.                                           |
| `IOError`                | Raised when an I/O operation (such as a print statement or the `open()` function) fails.     |
| `OSError`                | Raised when a system-related operation causes an error.                                      |
| `StopIteration`          | Raised to signal the end of an iterator.                                                     |
| `RuntimeError`           | Raised when an error is detected that doesn't fall in any of the other categories.           |
| `RecursionError`         | Raised when the maximum recursion depth is exceeded.                                         |
| `NotImplementedError`    | Raised by abstract methods that need to be implemented by subclasses.                        |
| `AssertionError`         | Raised when an `assert` statement fails.                                                     |
| `FloatingPointError`     | Raised when a floating point operation fails.                                                |
| `OverflowError`          | Raised when the result of an arithmetic operation is too large to be expressed.              |
| `MemoryError`            | Raised when an operation runs out of memory.                                                 |
| `EOFError`               | Raised when the `input()` function hits an end-of-file condition.                            |
| `KeyboardInterrupt`      | Raised when the user hits the interrupt key (usually `Ctrl+C` or `Delete`).                  |
| `ConnectionError`        | Base class for network-related errors.                                                       |
| `TimeoutError`           | Raised when a system function times out.                                                     |
| `BrokenPipeError`        | Raised when a pipe is broken during a write operation.                                       |
| `IsADirectoryError`      | Raised when a file operation (such as `open()`) is attempted on a directory.                 |
| `PermissionError`        | Raised when trying to perform an operation without the necessary permissions.                |
| `ChildProcessError`      | Raised when a child process operation fails.                                                 |
| `BlockingIOError`        | Raised when an operation would block on an object (like a socket) set for non-blocking mode. |
| `SystemExit`             | Raised by the `sys.exit()` function.                                                         |
| `GeneratorExit`          | Raised when a generator’s `close()` method is called.                                        |

