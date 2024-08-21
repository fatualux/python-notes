# Dictionaries

![Dictionaries](../static/images/dictionaries.png)

A **dictionary** in Python is an **unordered collection** of items, where each item is a **key-value pair**. Dictionaries are **mutable**, meaning that they can be changed after their creation.

## Key Concepts of Dictionaries in Python

**Dictionary Definition**:
  A dictionary is defined by enclosing a comma-separated list of key-value pairs within **curly braces** `{}`.

```python
  my_dict = {
      "key1": "value1",
      "key2": "value2",
      "key3": "value3"
  }
```

**Keys and Values**:
- Keys: The unique identifiers that act as the index to access the corresponding values. Keys must be immutable types (e.g., strings, numbers, tuples).
- Values: The data associated with the keys. Values can be of any data type and can be duplicated.

```python

my_dict = {
    "name": "Alice",  # 'name' is the key, "Alice" is the value
    "age": 30,        # 'age' is the key, 30 is the value
    "city": "New York"
}
```

**Accessing Values**:
Values in a dictionary can be accessed by using the key in square brackets [] or with the .get() method.

```python

name = my_dict["name"]  # Accessing via key
age = my_dict.get("age")  # Accessing via .get() method
```

**Adding and Modifying Entries**:
You can add new key-value pairs or modify existing ones by assigning a value to a key.

```python
my_dict["email"] = "alice@example.com"  # Adding a new entry
my_dict["age"] = 31  # Modifying an existing entry
```
**Removing Entries**:
Entries can be removed using the del keyword, the .pop() method, or the .popitem() method (which removes the last inserted item).

```python
del my_dict["city"]  # Remove 'city' key-value pair
email = my_dict.pop("email")  # Remove and return the value of 'email'
last_item = my_dict.popitem()  # Remove and return the last inserted key-value pair
```

**Looping through dictionaries**
```python
student_dict = {
    "student": ["Michele", "Eleonora", "Isabel", "Simone"],
    "age": [8, 6, 7, 5]
}
print(student_dict)
# output: {'student': ['Michele', 'Eleonora', 'Isabel', 'Simone'], 'age': [8, 6, 7, 5]}

for (key, value) in student_dict.items():
    print(key)
    # output: student
    #         age
    print(value)
    # output: ['Michele', 'Eleonora', 'Isabel', 'Simone']
    #         [8, 6, 7, 5]
```

**Dictionary Methods**:

- **keys()**: Returns a view object of all keys.
- **values()**: Returns a view object of all values.
- **items()**: Returns a view object of all key-value pairs as tuples.
- **update()**: Merges another dictionary or an iterable of key-value pairs into the dictionary.

```python
keys = my_dict.keys()  # Get all keys
values = my_dict.values()  # Get all values
items = my_dict.items()  # Get all key-value pairs
my_dict.update({"name": "Bob", "city": "Los Angeles"})  # Update dictionary
```
