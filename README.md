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

## Some Puzzles on Bit Manipulation
**Problem-1**

bitAnd - x&y using only ~ and |
 *   Example: bitAnd(6, 5) = 4
 *   Legal ops: ~ |
 *   Max ops: 8
 *   Rating: 1
```C
int bitAnd(int x, int y)
{

    int temp = ~(~x | ~y);
    return temp;
}
```
**Problem-2**

bitOr - x|y using only ~ and &
 *   Example: bitOr(6, 5) = 7
 *   Legal ops: ~ &
 *   Max ops: 8
 *   Rating: 1
```C
int bitOr(int x, int y)
{
    int temp = ~(~x & ~y);
    return 2;

}
```
**Problem-3**

isZero - returns 1 if x == 0, and 0 otherwise
 *   Examples: isZero(5) = 0, isZero(0) = 1
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 2
 *   Rating: 1
```C
int isZero(int x)
{
    return !x;
}
```
**Problem-4**

minusOne - return a value of -1
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 2
 *   Rating: 1
```C
int minusOne(void)
{
    return ~(1 << 31);
}
```
**Problem-5**

TMax - return maximum two's complement integer
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 4
 *   Rating: 1
```C
int tmax(void)
{
    // Shift 1 to the left by 31 bits to set the sign bit to 0
    // All other bits will be set to 1
    return (1 << 31) ^ ~(1 << 31);
}
```
**Problem-6**

bitXor - x^y using only ~ and &
 *   Example: bitXor(4, 5) = 1
 *   Legal ops: ~ &
 *   Max ops: 14
 *   Rating: 2
```C
int bitXor(int x, int y) {
    int not_x = ~x;
    int not_y = ~y;
    int and_x_y = x & y;
    int and_not_x_not_y = not_x & not_y;
    int result = ~(and_x_y & and_not_x_not_y);
    return result;
}
```
**Problem-7**

getByte - Extract byte n from word x
 *   Bytes numbered from 0 (LSB) to 3 (MSB)
 *   Examples: getByte(0x12345678,1) = 0x56
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 6
 *   Rating: 2
```C
int getByte(int x, int n)
{
    // Shift x right by 8 * n bits to get the desired byte in the least significant position
    int shifted = x >> (n << 3);

    // Mask the result to keep only the least significant byte
    int result = shifted & 0xFF;

    return result;
}
```
**Problem-8**

isEqual - return 1 if x == y, and 0 otherwise
 *   Examples: isEqual(5,5) = 1, isEqual(4,5) = 0
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 5
 *   Rating: 2
```C
int isEqual(int x, int y)
{
    // XOR x and y, if they are equal, the result will be 0
    int result = !(x ^ y);

    return result;
}
```
**Problem-9**

negate - return -x
 *   Example: negate(1) = -1.
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 5
 *   Rating: 2
```C
int negate(int x)
{
    // Negate x by taking its two's complement
    return (~x) + 1;
}
```
**Problem-10**

isPositive - return 1 if x > 0, return 0 otherwise
 *   Example: isPositive(-1) = 0.
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 8
 *   Rating: 3

```C
int isPositive(int x)
{
    // Shift x 31 bits to the right to extract its sign bit
    int sign = (x >> 31) & 1;

    // If x is greater than 0, sign will be 0, and we negate it to get 1
    // If x is less than or equal to 0, sign will be 1, and we negate it to get 0
    return !sign;
}
```
