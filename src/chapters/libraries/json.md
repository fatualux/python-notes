# JSON Library

The JSON library in Python provides methods for parsing JSON strings and converting Python objects to JSON strings. This is useful for data interchange between a server and a web application or between different parts of a software system.

## Key Concepts

### 1. **Loading JSON Data**

- **Overview**: Convert JSON strings into Python objects.
- **Features**:
  - Supports parsing from a string or file.
  - Converts JSON arrays to Python lists and JSON objects to Python dictionaries.
- **Example**:
  ```python
  import json

  json_data = '{"name": "John", "age": 30, "city": "New York"}'
  data = json.loads(json_data)

  print(data["name"])  # Output: John
  ```

### 2. **Dumping JSON Data**

- **Overview**: Convert Python objects into JSON strings.
- **Features**:
  - Supports serialization of Python lists, dictionaries, and more.
  - Can write JSON data to a file.
- **Example**:
  ```python
  import json

  data = {
      "name": "John",
      "age": 30,
      "city": "New York"
  }

  json_data = json.dumps(data)
  print(json_data)  # Output: {"name": "John", "age": 30, "city": "New York"}
  ```

### 3. **Working with Files**

- **Overview**: Reading from and writing to JSON files.
- **Features**:
  - Use `json.load()` to read from a file.
  - Use `json.dump()` to write to a file.
- **Example**:
  ```python
  import json

  # Writing to a JSON file
  data = {
      "name": "John",
      "age": 30,
      "city": "New York"
  }

  with open("data.json", "w") as file:
      json.dump(data, file)

  # Reading from a JSON file
  with open("data.json", "r") as file:
      data = json.load(file)

  print(data["name"])  # Output: John
  ```

### 4. **Handling Complex Data Types**

- **Overview**: Serializing and deserializing custom objects.
- **Features**:
  - Implement custom encoding and decoding functions.
  - Handle non-standard data types like datetime.
- **Example**:
  ```python
  import json
  from datetime import datetime

  class CustomEncoder(json.JSONEncoder):
      def default(self, obj):
          if isinstance(obj, datetime):
              return obj.isoformat()
          return json.JSONEncoder.default(self, obj)

  data = {
      "name": "John",
      "birthdate": datetime(1990, 5, 17)
  }

  json_data = json.dumps(data, cls=CustomEncoder)
  print(json_data)  # Output: {"name": "John", "birthdate": "1990-05-17T00:00:00"}
  ```

### 5. **Pretty Printing JSON**

- **Overview**: Producing human-readable JSON strings.
- **Features**:
  - Use the `indent` parameter in `json.dumps()` for formatting.
  - Improve readability of JSON data.
- **Example**:
  ```python
  import json

  data = {
      "name": "John",
      "age": 30,
      "city": "New York"
  }

  json_data = json.dumps(data, indent=4)
  print(json_data)
  # Output:
  # {
  #     "name": "John",
  #     "age": 30,
  #     "city": "New York"
  # }
  ```

### 6. **Error Handling**

- **Overview**: Managing exceptions during JSON operations.
- **Features**:
  - Catch and handle `JSONDecodeError` for invalid JSON data.
  - Ensure robust data processing.
- **Example**:
  ```python
  import json

  invalid_json_data = '{"name": "John", "age": 30, "city": "New York"'

  try:
      data = json.loads(invalid_json_data)
  except json.JSONDecodeError as e:
      print(f"Error decoding JSON: {e}")
  ```
