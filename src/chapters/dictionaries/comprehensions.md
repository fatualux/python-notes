# Dictionary Comprehensions

Dictionary comprehensions in Python provide a concise way to create dictionaries by applying an expression to each key-value pair in an iterable. They are similar to list comprehensions but generate dictionaries instead of lists, making your code more readable and efficient when working with key-value pairs.

### Basic Syntax

The basic syntax of a dictionary comprehension is:

```python
# {key_expression: value_expression for item in iterable}
# e.g.
 new_dict = {new_key:new_value for item in list}
```

- **key_expression**: The expression that defines the key in the dictionary.
- **value_expression**: The expression that defines the value corresponding to the key.
- **item**: The variable that takes each value from the iterable.
- **iterable**: The collection of items to iterate over.

### Examples

1. **Creating a Dictionary from a List**:
   - Example:
     ```python
     numbers = [1, 2, 3, 4]
     squares = {x: x**2 for x in numbers}
     # squares is {1: 1, 2: 4, 3: 9, 4: 16}
     ```

2. **Using a Condition in Dictionary Comprehension**:
   - You can filter items using an `if` condition.
   - Example:
     ```python
     numbers = range(10)
     even_squares = {x: x**2 for x in numbers if x % 2 == 0}
     # even_squares is {0: 0, 2: 4, 4: 16, 6: 36, 8: 64}
     ```

3. **Swapping Keys and Values**:
   - Example:
     ```python
     original_dict = {'a': 1, 'b': 2, 'c': 3}
     swapped_dict = {value: key for key, value in original_dict.items()}
     # swapped_dict is {1: 'a', 2: 'b', 3: 'c'}
     ```

4. **Combining Two Lists into a Dictionary**:
   - Example:
     ```python
     keys = ['name', 'age', 'city']
     values = ['Alice', 28, 'New York']
     combined_dict = {k: v for k, v in zip(keys, values)}
     # combined_dict is {'name': 'Alice', 'age': 28, 'city': 'New York'}
     ```

     Note: the ***zip function*** takes two or more iterables and returns an iterator of tuples, where the i-th tuple contains the i-th element from each of the input iterables.

     In this case, zip(keys, values) will produce an iterator of tuples: ('name', 'Alice'), ('age', 28), and ('city', 'New York').

5. **Nested Dictionary Comprehensions**:
   - Example:
     ```python
     nested_dict = {x: {y: y**2 for y in range(3)} for x in range(3)}
     # nested_dict is {0: {0: 0, 1: 1, 2: 4}, 1: {0: 0, 1: 1, 2: 4}, 2: {0: 0, 1: 1, 2: 4}}

     ```
6. **Converting values in a dictionary**:
   - Example:
     ```python
     weather_c = {"Monday": 12, "Tuesday": 14, "Wednesday": 15, "Thursday": 14, "Friday": 21, "Saturday": 22,"Sunday": 24}
     weather_f = {day: ((weather_c[day] * 9/5) + 32) for day in weather_c}
     # "weather_c[day]": section "Accessing values", in the previous chapter "Dictionaries"
     print(weather_f)
     ```

### Advanced Use Cases

1. **Handling Missing Keys with `get()`**:
   - You can handle cases where keys might not exist by using the `get()` method.
   Example:
     ```python
     data = {'a': 1, 'b': 2, 'c': 3}
     result = {k: data.get(k, 0) for k in ['a', 'b', 'd']}
     # result is {'a': 1, 'b': 2, 'd': 0}
     ```

2. **Creating Dictionaries with Complex Values**:
   - Example:
     ```python
     numbers = [1, 2, 3]
     complex_dict = {x: (x, x**2, x**3) for x in numbers}
     # complex_dict is {1: (1, 1, 1), 2: (2, 4, 8), 3: (3, 9, 27)}
     ```
  