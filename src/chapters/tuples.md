# Tuples

![Tuples](../static/images/tuples.png)

**Tuples** are collections similar to lists, but with the key difference that they are **immutable**, meaning their contents cannot be changed once they are created. Tuples are used to group multiple items into a single variable and can be particularly useful when you need to return multiple values from a function.

## Key Concepts of Tuples in Python

- **Tuple Definition**:
  Tuples are defined using parentheses `()` and can contain multiple items separated by commas. You can also create a tuple using the `tuple()` constructor.

  ```python
  my_tuple = (1, 2, 3)  # Tuple with multiple items
  another_tuple = tuple((1, 2, 3))  # Tuple created with tuple() constructor
  single_item_tuple = (5,)  # Tuple with a single item (comma is necessary)
  ```

- **Accessing Tuple Elements**:
  Elements in a tuple can be accessed using indexing. Indexing starts at 0 for the first element.

  ```python
  my_tuple = (1, 2, 3)
  first_item = my_tuple[0]  # Output: 1
  last_item = my_tuple[-1]  # Output: 3
  ```

- **Unpacking Tuples**:
  Tuples can be unpacked into individual variables. The number of variables must match the number of elements in the tuple.

  ```python
  my_tuple = (1, 2, 3)
  a, b, c = my_tuple
  print(a, b, c)  # Output: 1 2 3
  ```

- **Tuple Operations**:
  Tuples support various operations such as concatenation, repetition, and membership testing.

  ```python
  tuple1 = (1, 2)
  tuple2 = (3, 4)
  concatenated = tuple1 + tuple2  # Output: (1, 2, 3, 4)
  repeated = tuple1 * 3  # Output: (1, 2, 1, 2, 1, 2)
  is_in = 2 in tuple1  # Output: True
  ```

- **Immutable Nature**:
  Tuples are immutable, which means once created, you cannot modify, add, or remove elements. Any attempt to do so will result in a `TypeError`.

  ```python
  my_tuple = (1, 2, 3)
  # my_tuple[1] = 4  # Raises TypeError: 'tuple' object does not support item assignment
  ```

- **Nested Tuples**:
  Tuples can contain other tuples or mutable objects like lists. This allows for complex data structures.

  ```python
  nested_tuple = ((1, 2), (3, 4))
  first_pair = nested_tuple[0]  # Output: (1, 2)
  second_item_of_first_pair = nested_tuple[0][1]  # Output: 2
  ```

- **Tuple Methods**:
  Tuples have two built-in methods: `count()` and `index()`. These methods are used to count occurrences of an element and find the index of the first occurrence of an element, respectively.

  ```python
  my_tuple = (1, 2, 2, 3)
  count_of_twos = my_tuple.count(2)  # Output: 2
  index_of_two = my_tuple.index(2)  # Output: 1 (index of the first occurrence)
  ```

- **Immutability and Hashing**:
  Because tuples are immutable, they can be used as keys in dictionaries or as elements of sets, unlike lists.

  ```python
  my_dict = { (1, 2): "value" }
  my_set = set([(1, 2), (3, 4)])  # Tuples can be elements of a set
  ```

