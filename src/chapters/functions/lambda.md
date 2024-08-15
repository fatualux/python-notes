# Lambda Functions

Lambda functions, also known as anonymous functions, are small, one-line functions defined using the `lambda` keyword. They are used for creating small, throwaway functions that are not necessarily required to be named.

### Syntax

```python
lambda arguments: expression
```

- **Arguments**: The inputs to the lambda function, similar to parameters in regular functions.
- **Expression**: A single expression that is evaluated and returned by the lambda function.

### Example

Define a lambda function that adds two numbers:

```python
add = lambda x, y: x + y
print(add(5, 3))  # Output: 8
```

### Common Uses

1. **Short-lived Functions**: Lambda functions are often used for short operations where defining a full function is unnecessary.

2. **Higher-order Functions**: Useful in functions like `map()`, `filter()`, and `sorted()` where a simple function is required.

#### Example with `map()`:

```python
numbers = [1, 2, 3, 4]
squared = map(lambda x: x**2, numbers)
print(list(squared))  # Output: [1, 4, 9, 16]
```

#### Example with `filter()`:

```python
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = filter(lambda x: x % 2 == 0, numbers)
print(list(even_numbers))  # Output: [2, 4, 6]
```

#### Example with `sorted()`:

```python
points = [(2, 3), (1, 2), (4, 1)]
sorted_points = sorted(points, key=lambda point: point[1])
print(sorted_points)  # Output: [(4, 1), (1, 2), (2, 3)]
```

### Limitations

- **Single Expression**: Lambda functions can only contain a single expression, not multiple statements or complex logic.
- **Readability**: Overusing lambda functions for complex operations can reduce code readability. For complex functions, prefer regular function definitions.

### Best Practices

- **Use for Simple Operations**: Lambda functions are ideal for simple, short operations.
- **Prefer Named Functions for Complex Logic**: For more complex logic, define a named function using `def` to improve readability and maintainability.
- **Keep it Readable**: Ensure lambda functions are used in contexts where their brevity enhances code clarity, not detracts from it.

