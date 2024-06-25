# Booleans

**Booleans** are used to represent true or false values (boolean algebra is the subset of algebra which variables are either true or false).

Booleans are often used in conditional statements to control the flow of a program. They are essential in decision-making constructs such as `if`, `while`, and `for` loops.

![booleans](../static/images/booleans.png)

Booleans are subclasses of integers, and are represented as **1** (*true*) and **0** (*false*); their type is `bool`. and they can be combined in Boolean expressions using the logical operators *and*, *or*, and *not*.

- **Boolean Values**:
  Python uses `True` and `False` to represent boolean values. These are the only two possible values for a boolean.

- **Boolean Operations**:
  Booleans support logical operations like `and`, `or`, and `not`, which are used to combine or invert boolean expressions.

- and: Returns True if both operands are True.
- or: Returns True if at least one operand is True.
- not: Returns True if the operand is False, and False if the operand is True.


  ```python
  is_true = True
  is_false = False

  result_and = is_true and is_false  # False
  result_or = is_true or is_false    # True
  result_not = not is_true           # False
  ```

- **Boolean Expressions**:
  A boolean expression is an expression that evaluates to a boolean value (`True` or `False`). These expressions are commonly used in conditions and loops.

  ```python
  age = 18
  is_adult = age >= 18  # True
  ```

- **Truthiness**:
  In Python, objects can be evaluated in a boolean context to determine their "truthiness". Non-zero numbers, non-empty sequences, and non-empty objects are considered `True`, while `0`, `None`, and empty sequences or objects are considered `False`.

  ```python
  if []:
      print("This won't print because an empty list is False")
  if [1, 2, 3]:
      print("This will print because a non-empty list is True")
  ```
