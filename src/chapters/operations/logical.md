# Logical Operations

Logical operations are used to combine or negate boolean values, facilitating complex conditional logic in programming.

### Common Logical Operators

1. **AND (`and`)**: Returns `True` if both operands are `True`; otherwise, returns `False`.

   ```python
   a = True
   b = False
   result = a and b  # False
   print(result)  # Output: False
   ```

2. **OR (`or`)**: Returns `True` if at least one operand is `True`; returns `False` if both are `False`.

   ```python
   a = True
   b = False
   result = a or b  # True
   print(result)  # Output: True
   ```

3. **NOT (`not`)**: Negates the boolean value of the operand. Returns `True` if the operand is `False`, and `False` if the operand is `True`.

   ```python
   a = True
   result = not a  # False
   print(result)  # Output: False
   ```

### Combining Logical Operators

Logical operators can be combined to form more complex conditions:

   ```python
   a = True
   b = False
   c = True

   result = (a and b) or c  # True
   print(result)  # Output: True
   ```

### Short-Circuit Evaluation

Logical operators use short-circuit evaluation to optimize performance:
- **AND (`and`)**: If the first operand is `False`, the second operand is not evaluated.
- **OR (`or`)**: If the first operand is `True`, the second operand is not evaluated.

   ```python
   def expensive_operation():
       print("Operation performed")
       return True

   result = False and expensive_operation()  # "Operation performed" is not printed
   print(result)  # Output: False
   ```

### Conclusion

Logical operations are fundamental for building conditions and control flow in programming. They enable complex decision-making and efficient code execution through short-circuit evaluation.

