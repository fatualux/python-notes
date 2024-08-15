# Bitwise Operations

Bitwise operations perform operations on the binary representations of integers. These operations are useful for low-level programming and manipulating data at the bit level.

### Common Bitwise Operators

1. **AND (`&`)**: Performs a bitwise AND. Results in a bit being set if it is set in both operands.

   ```python
   a = 12  # 1100 in binary
   b = 7   # 0111 in binary
   result = a & b  # 0100 in binary, which is 4
   print(result)  # Output: 4
   ```

2. **OR (`|`)**: Performs a bitwise OR. Results in a bit being set if it is set in either operand.

   ```python
   a = 12  # 1100 in binary
   b = 7   # 0111 in binary
   result = a | b  # 1111 in binary, which is 15
   print(result)  # Output: 15
   ```

3. **XOR (`^`)**: Performs a bitwise XOR. Results in a bit being set if it is set in one operand but not both.

   ```python
   a = 12  # 1100 in binary
   b = 7   # 0111 in binary
   result = a ^ b  # 1011 in binary, which is 11
   print(result)  # Output: 11
   ```

4. **NOT (`~`)**: Performs a bitwise NOT. Inverts all bits of the operand (one's complement).

   ```python
   a = 12  # 1100 in binary
   result = ~a  # Inverts bits: 0011 in binary, which is -13 (in two's complement)
   print(result)  # Output: -13
   ```

5. **Left Shift (`<<`)**: Shifts bits to the left by a specified number of positions. Fills with zeros on the right.

   ```python
   a = 3  # 0011 in binary
   result = a << 2  # 1100 in binary, which is 12
   print(result)  # Output: 12
   ```

6. **Right Shift (`>>`)**: Shifts bits to the right by a specified number of positions. For positive numbers, fills with zeros on the left.

   ```python
   a = 12  # 1100 in binary
   result = a >> 2  # 0011 in binary, which is 3
   print(result)  # Output: 3
   ```

### Conclusion

Bitwise operations are used to manipulate individual bits of integers. Understanding these operations is essential for tasks that require direct control over binary data and performance optimization at the bit level.

