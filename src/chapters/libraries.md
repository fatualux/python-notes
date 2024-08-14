# Libraries

Python has an extensive standard library, but its functionality can be significantly extended by using third-party libraries. These libraries provide additional tools and functionalities, ranging from data manipulation to web development, machine learning, and more.

![Library](../static/images/library_02.png)

>You can access the list of available libraries in the [Python Package Index (PyPI)](https://pypi.org/).

## Key Concepts of Libraries in Python

- **Importing Libraries**:
  To use a library in your Python code, you first need to import it. Python provides the `import` statement for this purpose.

  ```python
  import math  # Importing the standard math library
  import os    # Importing the standard os library
  ```

- **Installing Third-Party Libraries**:
  Third-party libraries are not included in Python’s standard library and must be installed using a package manager like `pip`. Once installed, they can be imported and used just like standard libraries.

  ```python
  # Install a third-party library using pip
  pip install requests
  ```

- **Using Imported Libraries**:
  After importing a library, you can access its functions, classes, and variables using dot notation.

  ```python
  import math

  result = math.sqrt(16)  # Output: 4.0
  ```

- **Commonly Used Third-Party Libraries**:
  - **NumPy**: Provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on them.
  
    ```python
    import numpy as np

    array = np.array([1, 2, 3, 4])
    ```
  
  - **Pandas**: Used for data manipulation and analysis, providing data structures like DataFrame and Series.
  
    ```python
    import pandas as pd

    data = {'name': ['Alice', 'Bob'], 'age': [25, 30]}
    df = pd.DataFrame(data)
    ```

  - **Requests**: Allows you to send HTTP requests, making it easy to interact with web services.
  
    ```python
    import requests

    response = requests.get('https://api.github.com')
    ```

  - **Matplotlib**: A plotting library for creating static, animated, and interactive visualizations in Python.
  
    ```python
    import matplotlib.pyplot as plt

    plt.plot([1, 2, 3, 4], [10, 20, 25, 30])
    plt.show()
    ```

  - **Scikit-learn**: A machine learning library that provides simple and efficient tools for data mining and data analysis.
  
    ```python
    from sklearn.linear_model import LinearRegression

    model = LinearRegression()
    ```

  - **Flask**: A lightweight WSGI web application framework designed to make it easy to get started with web development.
  
    ```python
    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Hello, World!'
    ```

- **Creating Your Own Libraries**:
  You can create your own libraries by organizing your Python code into modules (files) and packages (directories with an `__init__.py` file). These libraries can then be imported and reused in other projects.

  ```python
  # Example of a simple custom module
  # File: my_module.py
  def greet(name):
      return f"Hello, {name}!"
  ```

  ```python
  # Using the custom module in another script
  import my_module

  print(my_module.greet("Alice"))  # Output: Hello, Alice!
  ```

- **Virtual Environments**:
  Virtual environments are isolated environments that allow you to manage dependencies for different projects separately, avoiding conflicts between library versions.

  ```bash
  # Creating a virtual environment
  python -m venv myenv

  # Activating the virtual environment
  # On Windows:
  myenv\Scripts\activate
  # On macOS/Linux:
  source myenv/bin/activate

  # Deactivating the virtual environment
  deactivate
  ```

