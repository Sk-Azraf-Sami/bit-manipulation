# Bit Manipulation in 'C' Programming

## Basic 
Bitwise operators are fundamental operators in computer programming that work on individual bits (0s and 1s) within binary representations of numbers. These operators are commonly used in low-level programming, hardware manipulation, and various other applications. There are several bitwise operators:

1. **Bitwise AND (`&`):** This operator compares each bit position of two integers. If both bits are 1, the result is 1; otherwise, it's 0.

   Example:
   ```
   5 (binary: 0101)
   & 3 (binary: 0011)
   = 1 (binary: 0001)
   ```

2. **Bitwise OR (`|`):** This operator compares each bit position of two integers. If either of the bits is 1, the result is 1; otherwise, it's 0.

   Example:
   ```
   5 (binary: 0101)
   | 3 (binary: 0011)
   = 7 (binary: 0111)
   ```

3. **Bitwise XOR (`^`):** This operator compares each bit position of two integers. If the bits are different (one is 0, the other is 1), the result is 1; otherwise, it's 0.

   Example:
   ```
   5 (binary: 0101)
   ^ 3 (binary: 0011)
   = 6 (binary: 0110)
   ```

4. **Bitwise NOT (`~`):** This operator negates each bit. It flips 0s to 1s and 1s to 0s.

   Example:
   ```
   ~5 (binary: 0101)
   = -6 (binary: 1010)
   ```

5. **Left Shift (`<<`):** This operator shifts the bits of a number to the left by a specified number of positions. It effectively multiplies the number by 2 for each position shifted.

   Example:
   ```
   5 << 2
   = 20
   ```

6. **Right Shift (`>>`):** This operator shifts the bits of a number to the right by a specified number of positions. It effectively divides the number by 2 for each position shifted.

   Example:
   ```
   20 >> 2
   = 5
   ```

Bitwise operators are often used in scenarios such as:

- Manipulating individual bits within a number.
- Efficiently implementing data structures like bitsets and flags.
- Performing optimizations in low-level code.
- Interacting with hardware registers.
- Encoding and decoding data in specific formats.

Understanding bitwise operators is crucial when working on embedded systems, system-level programming, and tasks requiring precise control over data at the bit level.

**Difference between ~ and ! of bitwise operation**

The `~` and `!` operators are both used in bitwise operations, but they serve different purposes and have different behaviors:

1. `~` (Bitwise NOT Operator):
   - `~` is the bitwise NOT operator, also known as the bitwise complement operator.
   - It inverts each bit in its operand. If a bit is 0, it becomes 1, and if it's 1, it becomes 0.
   - Example: If you apply `~` to the binary representation of 5 (which is `0101` in 4 bits), you get `-6` (which is `1010` in 4 bits in two's complement representation).
   - It's used for bitwise negation.

2. `!` (Logical NOT Operator):
   - `!` is the logical NOT operator.
   - It's used in boolean logic, not bitwise operations.
   - It takes a boolean value (true or false) as an operand and returns the opposite boolean value.
   - Example: `!true` returns `false`, and `!false` returns `true`.
   - It's used for boolean negation, such as in conditional statements and logical expressions.

In summary, `~` is a bitwise operator used for inverting individual bits in a binary representation, while `!` is a logical operator used for boolean negation in conditional logic. They have different purposes and applications.
