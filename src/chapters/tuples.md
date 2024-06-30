# Tuples

![Tuples](../static/images/tuples.png)

**Tuples** are similar to lists, but they are **immutable**.

Tuples are used to store multiple items in a single variable, or in a function, to return multiple objects.

```python
my_tuple = (1, 2, 3)
my_tuple = tuple((1, 2, 3)) # same as above
my-single-item-tuple = (5,) # remember the comma

a, b, c = my_tuple
print(a, b, c) # it prints 1, 2, 3
1 in my_tuple # it prints True, because 1 is in my_tuple
```
