# Creating Packages

1. **Create a Directory**: Create a directory for your package. This directory will serve as the namespace for your package.

2. **Add `__init__.py`**: Inside this directory, add a file named `__init__.py`. This file can be empty or contain initialization code for the package.

3. **Add Modules**: Place your Python files (modules) inside the package directory. Each file should contain related functions, classes, or variables.

4. **Subpackages**: If you need to organize modules further, create subdirectories (subpackages) within your package. Each subdirectory must also contain an `__init__.py` file.

### Importing from Packages

You can import modules from packages using the dot notation:

```python
from my_package import module1
from my_package.subpackage import submodule1
```

### Example

Consider a package named `my_tools` with the following structure:

```python
my_tools/
    __init__.py
    math_utils.py
    string_utils.py
```

In `math_utils.py`:

```python
def add(a, b):
    return a + b
```

In `string_utils.py`:

```python
def capitalize(text):
    return text.capitalize()
```

You can use the functions in another script like this:

```python
from my_tools.math_utils import add
from my_tools.string_utils import capitalize

result = add(2, 3)
text = capitalize("hello")
```

### Best Practices

- **Organize logically**: Group related modules together to keep the package structure logical and intuitive.
- **Avoid large packages**: Split large packages into smaller subpackages to keep them manageable.
- **Document**: Provide clear documentation for your package and modules to help users understand their purpose and usage.

