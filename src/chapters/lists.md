# Lists

![Lists](../static/images/lists.png)

In Python, **lists** are used to store multiple items in a single variable. Lists are one of the most versatile data types available in Python.

## Key Concepts of Lists in Python

- **List Definition**:
  A list can be defined by placing all the items (elements) inside square brackets `[]`, separated by commas. Lists can contain items of different data types, including other lists.

  ```python
  my_empty_list = []
  my_empty_list = list()  # same as above
  my_list = [1, 2, 3]
  my_list = list([1, 2, 3])  # same as above
  mixed_list = [1, "hello", 3.14, True]
  nested_list = [1, [2, 3], [4, 5, 6]]
  ```

- **Ordered**:
  Lists are ordered, meaning that the elements have a defined order, and this order will not change unless you explicitly modify the list.

  ```python
  fruits = ["apple", "banana", "cherry"]
  print(fruits[0])  # Output: apple
  print(fruits[2])  # Output: cherry
  ```

- **Mutable**:
  Lists are mutable, meaning that you can change their content without changing their identity. You can add, remove, or modify elements in a list.

  ```python
  my_list = [1, 2, 3]
  my_list[0] = 10  # my_list is now [10, 2, 3]
  my_list.append(4)  # my_list is now [10, 2, 3, 4]
  my_list.remove(2)  # my_list is now [10, 3, 4]
  ```

- **Allow Duplicate Values**:
  Lists can have duplicate values, meaning the same value can appear multiple times in a list.

  ```python
  my_list = [1, 2, 2, 3, 3, 3]
  print(my_list)  # Output: [1, 2, 2, 3, 3, 3]
  ```

- **Accessing List Elements**:
  Elements in a list can be accessed by their index. Python uses zero-based indexing, so the first element has an index of 0. Negative indexing can be used to access elements from the end of the list.

  ```python
  my_list = ["a", "b", "c", "d"]
  first_item = my_list[0]  # Output: 'a'
  last_item = my_list[-1]  # Output: 'd'
  ```

- **Slicing**:
  You can access a range of elements in a list by using slicing. The syntax is `list[start:stop:step]`, where `start` is the index to begin slicing, `stop` is the index to end slicing (exclusive), and `step` is the interval between elements.

  ```python
  my_list = [0, 1, 2, 3, 4, 5]
  slice1 = my_list[1:4]  # Output: [1, 2, 3]
  slice2 = my_list[:3]   # Output: [0, 1, 2]
  slice3 = my_list[3:]   # Output: [3, 4, 5]
  slice4 = my_list[::2]  # Output: [0, 2, 4]
  ```

- **List Methods**:
  Lists come with several built-in methods that make them easy to work with:
  - `append(item)`: Adds an item to the end of the list.
  - `extend(iterable)`: Extends the list by appending elements from an iterable.
  - `insert(index, item)`: Inserts an item at a specified index.
  - `remove(item)`: Removes the first occurrence of an item.
  - `pop(index=-1)`: Removes and returns the item at the specified index (default is the last item).
  - `clear()`: Removes all items from the list.
  - `index(item, start=0, end=len(list))`: Returns the index of the first occurrence of an item.
  - `count(item)`: Returns the number of occurrences of an item.
  - `sort(key=None, reverse=False)`: Sorts the list in ascending order.
  - `reverse()`: Reverses the elements of the list.
  - `copy()`: Returns a shallow copy of the list.

  ```python
  my_list = [3, 1, 4, 1, 5, 9]
  my_list.append(2)  # [3, 1, 4, 1, 5, 9, 2]
  my_list.sort()     # [1, 1, 2, 3, 4, 5, 9]
  my_list.reverse()  # [9, 5, 4, 3, 2, 1, 1]
  my_list.pop()      # [9, 5, 4, 3, 2, 1]
  ```

- **Nested Lists**:
  Lists can contain other lists as elements, creating a nested list. This allows for the creation of more complex data structures like matrices or tables.

  ```python
  matrix = [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
  ]
  print(matrix[1][2])  # Output: 6 (second row, third column)
  ```

- **List Iteration**:
  You can iterate over the elements of a list using a `for` loop.

  ```python
  my_list = ["apple", "banana", "cherry"]
  for fruit in my_list:
      print(fruit)
  # Output:
  # apple
  # banana
  # cherry
  ```

- **List Length**:
  The `len()` function returns the number of elements in a list.

  ```python
  my_list = [1, 2, 3, 4]
  length = len(my_list)  # Output: 4
  ```

