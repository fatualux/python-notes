# Popular Libraries

![Popular Libraries](../../static/images/popular_libraries.png)

Python's ecosystem is vast, with a wealth of third-party libraries that extend its capabilities in various domains, from web development and data science to machine learning and automation. Understanding and utilizing these popular libraries can greatly enhance your productivity and broaden the scope of your Python projects.

### Web Development

#### 1. **Django**

- **Overview**: A high-level web framework that encourages rapid development and clean, pragmatic design.
- **Key Features**:
  - ORM (Object-Relational Mapping) for database interactions.
  - Built-in admin interface.
  - URL routing, authentication, and middleware support.
- **Installation**:
  ```python
  pip install django
  ```
- **Example**:
  ```python
  django-admin startproject myproject
  ```

#### 2. **Flask**

- **Overview**: A lightweight WSGI web application framework designed to make getting started quick and easy.
- **Key Features**:
  - Minimalistic and flexible.
  - Jinja2 templating.
  - Built-in development server and debugger.
- **Installation**:
  ```python
  pip install flask
  ```
- **Example**:
  ```python
  from flask import Flask

  app = Flask(__name__)

  @app.route("/")
  def hello():
      return "Hello, World!"

  if __name__ == "__main__":
      app.run()
  ```

### Data Science

#### 1. **NumPy**

- **Overview**: The fundamental package for numerical computing with Python.
- **Key Features**:
  - Support for large, multi-dimensional arrays and matrices.
  - Mathematical functions to operate on these arrays.
- **Installation**:
  ```python
  pip install numpy
  ```
- **Example**:
  ```python
  import numpy as np

  array = np.array([1, 2, 3, 4])
  print(array.mean())  # Outputs the mean of the array
  ```

#### 2. **Pandas**

- **Overview**: A powerful data analysis and manipulation library for Python.
- **Key Features**:
  - DataFrame object for data manipulation with integrated indexing.
  - Tools for reading and writing data between in-memory data structures and different formats.
- **Installation**:
  ```python
  pip install pandas
  ```
- **Example**:
  ```python
  import pandas as pd

  df = pd.DataFrame({
      "A": [1, 2, 3],
      "B": [4, 5, 6]
  })
  print(df.head())  # Displays the first few rows of the DataFrame
  ```

#### 3. **Matplotlib**

- **Overview**: A plotting library for creating static, animated, and interactive visualizations.
- **Key Features**:
  - Wide variety of plots: line, bar, scatter, histogram, etc.
  - Highly customizable.
- **Installation**:
  ```python
  pip install matplotlib
  ```
- **Example**:
  ```python
  import matplotlib.pyplot as plt

  plt.plot([1, 2, 3], [4, 5, 6])
  plt.show()
  ```

### Machine Learning

#### 1. **Scikit-learn**

- **Overview**: A library for machine learning, built on NumPy, SciPy, and Matplotlib.
- **Key Features**:
  - Simple and efficient tools for data mining and data analysis.
  - Accessible to both beginners and experts.
- **Installation**:
  ```python
  pip install scikit-learn
  ```
- **Example**:
  ```python
  from sklearn.linear_model import LinearRegression

  model = LinearRegression()
  model.fit([[1], [2], [3]], [1, 2, 3])
  print(model.predict([[4]]))  # Predicts the output for the input 4
  ```

#### 2. **TensorFlow**

- **Overview**: An open-source library for numerical computation and large-scale machine learning.
- **Key Features**:
  - Flexibility to build and train models.
  - Strong support for deep learning architectures.
- **Installation**:
  ```python
  pip install tensorflow
  ```
- **Example**:
  ```python
  import tensorflow as tf

  model = tf.keras.models.Sequential([
      tf.keras.layers.Dense(128, activation='relu'),
      tf.keras.layers.Dense(10, activation='softmax')
  ])
  ```

### Automation and Web Scraping

#### 1. **Selenium**

- **Overview**: A library for automating web browsers.
- **Key Features**:
  - Control browsers through programs and perform browser automation.
  - Support for different browsers.
- **Installation**:
  ```python
  pip install selenium
  ```
- **Example**:
  ```python
  from selenium import webdriver

  driver = webdriver.Chrome()
  driver.get("https://www.example.com")
  driver.quit()
  ```

#### 2. **Beautiful Soup**

- **Overview**: A library for parsing HTML and XML documents and extracting data from them.
- **Key Features**:
  - Handles different parsers and broken HTML.
  - Facilitates searching and navigating the parse tree.
- **Installation**:
  ```python
  pip install beautifulsoup4
  ```
- **Example**:
  ```python
  from bs4 import BeautifulSoup

  html_doc = "<html><body><p>Hello, World!</p></body></html>"
  soup = BeautifulSoup(html_doc, 'html.parser')
  print(soup.p.string)  # Outputs "Hello, World!"
  ```

### Networking

#### 1. **Requests**

- **Overview**: A simple and elegant HTTP library for Python, built for human beings.
- **Key Features**:
  - Easy to use for sending HTTP requests.
  - Supports methods like GET, POST, PUT, DELETE.
- **Installation**:
  ```python
  pip install requests
  ```
- **Example**:
  ```python
  import requests

  response = requests.get("https://www.example.com")
  print(response.text)  # Outputs the content of the response
  ```

#### 2. **Socket**

- **Overview**: Provides a low-level networking interface.
- **Key Features**:
  - Core module for network connections using sockets.
  - Supports TCP, UDP, and more.
- **Example**:
  ```python

  import socket

  # Create a socket object
  s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

  # Define the host and port
  host = "www.example.com"
  port = 80

  # Connect to the server
  s.connect((host, port))

  # Send an HTTP GET request
  request = "GET / HTTP/1.1\r\nHost: {}\r\nConnection: close\r\n\r\n".format(host)
  s.sendall(request.encode('utf-8'))

  # Receive the response from the server
  response = b""
  while True:
      data = s.recv(4096)
      if not data:
          break
      response += data

  # Close the socket
  s.close()

  # Print the response
  print(response.decode('utf-8'))
```
