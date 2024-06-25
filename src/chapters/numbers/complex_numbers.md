# Complex Numbers

### Representation of Complex Numbers

- **Real Part**: The real part of a complex number is the component that does not involve the imaginary unit `j`.
- **Imaginary Part**: The imaginary part is the component that is multiplied by `j`, where `j` is the square root of -1.

Example:

  ```
  z = 3 + 4j  # 3 is the real part, 4 is the imaginary part
  ```

### Accessing Real and Imaginary Parts

You can access the real and imaginary parts of a complex number using the `.real` and `.imag` attributes.

  ```
  z = 3 + 4j
  real_part = z.real      # real_part is 3.0
  imaginary_part = z.imag # imaginary_part is 4.0
  ```

### Complex Number Operations

1. **Addition**:
   - Adds the real parts and the imaginary parts separately.
     ```
     z1 = 3 + 4j
     z2 = 1 + 2j
     result = z1 + z2  # result is 4 + 6j
     ```

2. **Subtraction**:
   - Subtracts the real parts and the imaginary parts separately.
     ```
     z1 = 3 + 4j
     z2 = 1 + 2j
     result = z1 - z2  # result is 2 + 2j
     ```

3. **Multiplication**:
   - Multiplies complex numbers using distributive property.
     ```
     z1 = 3 + 4j
     z2 = 1 + 2j
     result = z1 * z2  # result is -5 + 10j
     ```

4. **Division**:
   - Divides complex numbers using the formula for complex division.
     ```
     z1 = 3 + 4j
     z2 = 1 + 2j
     result = z1 / z2  # result is 2.2 - 0.4j
     ```

5. **Conjugate**:
   - The conjugate of a complex number is obtained by changing the sign of the imaginary part.
     ```
     z = 3 + 4j
     conjugate_z = z.conjugate()  # conjugate_z is 3 - 4j
     ```

### Magnitude and Phase

- **Magnitude**: The magnitude (or absolute value) of a complex number is the distance from the origin to the point represented by the number in the complex plane. It can be calculated using the `abs()` function.

  ```
  z = 3 + 4j
  magnitude = abs(z)  # magnitude is 5.0
  ```

- **Phase**: The phase (or argument) of a complex number is the angle between the positive real axis and the line representing the number in the complex plane. You can calculate it using the `cmath.phase()` function.

  ```
  import cmath

  z = 3 + 4j
  phase = cmath.phase(z)  # phase is approximately 0.93 radians
  ```

### Polar Coordinates

- **Conversion to Polar Coordinates**: A complex number can be represented in polar form as \(r \times e^{i\theta}\), where \(r\) is the magnitude and \(\theta\) is the phase.

  ```
  r, theta = cmath.polar(z)  # r is 5.0, theta is approximately 0.93 radians
  ```

- **Conversion from Polar to Rectangular Coordinates**: You can convert polar coordinates back to a complex number using `cmath.rect()`.

  ```
  z = cmath.rect(5.0, 0.93)  # z is approximately 3 + 4j
  ```

### Use Cases for Complex Numbers

- **Electrical Engineering**: Used in the analysis of AC circuits, where impedance is represented as a complex number.
- **Quantum Physics**: Complex numbers are used in quantum mechanics to describe wave functions.
- **Control Systems**: Complex numbers are used in the analysis of control systems, particularly in the context of transfer functions.

### Conclusion

Complex numbers are a powerful mathematical tool that extends the concept of one-dimensional numbers to two dimensions, incorporating both a real and an imaginary component. Understanding how to work with complex numbers in Python is crucial for fields that require advanced mathematical calculations.

