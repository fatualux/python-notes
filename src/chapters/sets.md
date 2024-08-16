# Sets

![Sets](../static/images/sets.png)

Sets in Python are unordered collections of unique elements. They are similar to lists or dictionaries, but with key differences, such as disallowing duplicate elements and not maintaining any order. Sets are particularly useful when you need to eliminate duplicates, perform membership tests, or apply mathematical set operations like union, intersection, and difference.

### Creating Sets

You can create a set by using curly braces `{}` or the `set()` function.

- **Using Curly Braces**:
  ```python
  my_set = {1, 2, 3, 4}
  # my_set is {1, 2, 3, 4}
  ```

- **Using the `set()` Function**:
  ```python
  my_set = set([1, 2, 3, 4])
  # my_set is {1, 2, 3, 4}
  ```

- **Creating an Empty Set**:
  - Use `set()` to create an empty set (curly braces `{}` would create an empty dictionary instead).
  ```python
  empty_set = set()
  # empty_set is set()
  ```

### Key Characteristics

1. **Unique Elements**:
   - Sets automatically eliminate duplicate values.
   ```python
   my_set = {1, 2, 2, 3}
   # my_set is {1, 2, 3}
   ```

2. **Unordered**:
   - The elements in a set are not stored in any particular order, and their order can change.
   ```python
   my_set = {3, 1, 2}
   # my_set could be displayed as {1, 2, 3} or any other order
   ```

3. **Immutable Elements**:
   - Sets can only contain immutable (hashable) elements like numbers, strings, and tuples, but not lists or other sets.
   ```python
   my_set = {1, "Hello", (2, 3)}
   # This is valid
   # my_set = {[1, 2], 3} would raise a TypeError
   ```

### Common Set Operations

1. **Adding Elements**:
   - Use `add()` to add a single element to a set.
   ```python
   my_set = {1, 2}
   my_set.add(3)
   # my_set is {1, 2, 3}
   ```

2. **Removing Elements**:
   - Use `remove()` to remove a specific element. Raises `KeyError` if the element is not found.
   - Use `discard()` to remove an element without raising an error if it’s not found.
   ```python
   my_set = {1, 2, 3}
   my_set.remove(2)
   # my_set is {1, 3}

   my_set.discard(4)  # No error raised
   ```

3. **Set Union**:
   - Combine two sets using the `|` operator or `union()` method.
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   union_set = set1 | set2
   # union_set is {1, 2, 3, 4, 5}
   ```

4. **Set Intersection**:
   - Find common elements between two sets using the `&` operator or `intersection()` method.
   ```python
   set1 = {1, 2, 3}
   set2 = {2, 3, 4}
   intersection_set = set1 & set2
   # intersection_set is {2, 3}
   ```

5. **Set Difference**:
   - Find elements in one set but not in the other using the `-` operator or `difference()` method.
   ```python
   set1 = {1, 2, 3}
   set2 = {2, 3, 4}
   difference_set = set1 - set2
   # difference_set is {1}
   ```

6. **Set Symmetric Difference**:
   - Find elements that are in either of the sets but not in both using the `^` operator or `symmetric_difference()` method.
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   symmetric_difference_set = set1 ^ set2
   # symmetric_difference_set is {1, 2, 4, 5}
   ```

### Membership Tests

Sets are highly efficient for membership tests, meaning you can quickly check if an element is in a set.

- **Checking Membership**:
  ```python
  my_set = {1, 2, 3}
  is_member = 2 in my_set  # True
  not_member = 4 not in my_set  # True
  ```

### Set Comprehensions

Similar to list comprehensions, you can use set comprehensions to create sets in a concise manner.

- **Example**:
  ```python
  squared_set = {x**2 for x in range(5)}
  # squared_set is {0, 1, 4, 9, 16}
  ```

