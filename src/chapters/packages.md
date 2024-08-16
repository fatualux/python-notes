# Packages

Every Python file, which has the extension `.py`, is called a *module*. Python allows us to organize these modules into structures called **packages**, which are essentially directories that contain a special `__init__.py` file.

![Packages](../static/images/packages.png)

## Key Concepts of Packages in Python

- **Definition of Packages**:
 A package is a collection of modules organized in directories. A directory must contain an __init__.py file (which can be empty) to be recognized as a package.
  ```python
  my_package/
  ├── __init__.py
  ├── module1.py
  └── module2.py
  ```

- **Importing Modules from Packages**:
  You can import modules or functions from a package using the dot notation. For example, to import `module1` from `my_package`, you would use:

  ```python
  from my_package import module1
  ```

  To import a specific function or class from a module within a package:

  ```python
  from my_package.module1 import my_function
  ```

- **Sub-packages**:
  Packages can contain sub-packages, which are just packages within packages. Each sub-package must also contain its own `__init__.py` file.

  ```python
  my_package/
  ├── __init__.py
  ├── module1.py
  ├── sub_package/
  │   ├── __init__.py
  │   └── sub_module.py
  ```

  Importing a module from a sub-package:

  ```python
  from my_package.sub_package import sub_module
  ```

- **Relative Imports**:
  Within a package, you can use relative imports to import modules or sub-packages using relative paths. This is useful for referring to modules in the same package or sub-packages.

  ```python
  # In my_package/module1.py
  from . import module2  # Import module2 from the same package
  from .sub_package import sub_module  # Import sub_module from sub_package
  ```

- **Namespace Packages**:
  Starting with Python 3.3, the `__init__.py` file is no longer required to create a package. This allows for namespace packages, which can span multiple directories. However, the traditional method with `__init__.py` is still widely used.

  ```python
  # Namespace package
  my_namespace/
  └── my_package/
      └── module1.py
  ```

- **Installing External Packages**:
  Python has a robust ecosystem of external packages that can be installed using package managers like `pip`. These packages are typically hosted on repositories like PyPI (Python Package Index).

  ```shell
  pip install requests
  ```

  After installation, you can use the installed package in your code:

  ```python
  import requests
  response = requests.get("https://example.com")
  ```

- **Creating and Distributing Packages**:
  To create your own package, you can include a `setup.py` file with metadata and dependencies. This file is used for packaging and distributing your code.

  ```python
  # setup.py example
  from setuptools import setup, find_packages

  setup(
      name='my_package',
      version='0.1',
      packages=find_packages(),
      install_requires=[
          'requests',
      ],
  )
  ```

  You can then build and distribute the package using:

  ```shell
  python setup.py sdist bdist_wheel
  pip install .
  ```

