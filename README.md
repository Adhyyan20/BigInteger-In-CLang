
## BigInt Library - README

### Introduction
This C library provides an implementation of `BigInt`, a data structure designed to handle arbitrarily large integers using a doubly linked list. Each node stores a group of four digits to optimize space usage and efficiency. The library supports fundamental arithmetic operations like addition, subtraction, multiplication, division, modulus, GCD, LCM, and exponentiation, along with useful comparison and utility functions.

### Features
- **Initialize from string**: Create a `BigInt` from a numerical string representation.
- **Arithmetic Operations**: Perform addition, subtraction, multiplication, division, modulus, GCD, LCM, and exponentiation.
- **Comparison Functions**: Compare two `BigInt` numbers, considering both magnitude and sign.
- **Memory Management**: Includes functions to handle memory allocation and deallocation.
- **Printing Support**: Functions available to display `BigInt` values easily.

### Compilation Guide
To compile and use this library in your C project:

1. Run this on Terminal
    ```sh
    gcc -c bigint.c -o bigint
    ar rcs lib_bigint.a bigint
    gcc -o test main.c -L. lib_bigint.a
    ./test
    ```

### Function List

#### 1. `BigInt* createI(char* str)`
   - **Purpose**: Initializes a `BigInt` from a string.
   - **Time Complexity**: O(n), where n is the number of digits.
   - **Example**:
     ```c
     BigInt* num = createI("123456789");
     ```

#### 2. `void printI(BigInt* num)`
   - **Purpose**: Prints the `BigInt` value.
   - **Time Complexity**: O(k), where k is the number of nodes (digits/4).
   - **Example**:
     ```c
     printI(num);
     ```

#### 3. `BigInt* addI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Adds two `BigInt` numbers.
   - **Time Complexity**: O(max(m, n)), where m and n are the node counts of `num1` and `num2`.
   - **Example**:
     ```c
     BigInt* sum = addI(num1, num2);
     ```

#### 4. `BigInt* subI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Computes `num1 - num2`.
   - **Time Complexity**: O(max(m, n)).
   - **Example**:
     ```c
     BigInt* result = subI(num1, num2);
     ```

#### 5. `BigInt* mulI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Multiplies two `BigInt` numbers.
   - **Time Complexity**: O(m * n).
   - **Example**:
     ```c
     BigInt* product = mulI(num1, num2);
     ```

#### 6. `BigInt* divI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Performs integer division.
   - **Time Complexity**: O(m * log n).
   - **Example**:
     ```c
     BigInt* quotient = divI(num1, num2);
     ```

#### 7. `BigInt* modI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Computes `num1 % num2`.
   - **Time Complexity**: O(m * log n).
   - **Example**:
     ```c
     BigInt* remainder = modI(num1, num2);
     ```

#### 8. `BigInt* powI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Raises `num1` to the power of `num2`.
   - **Time Complexity**: O(log n * m).
   - **Example**:
     ```c
     BigInt* power = powI(num1, num2);
     ```

#### 9. `BigInt* gcdI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Computes the greatest common divisor.
   - **Time Complexity**: O(m * log n).
   - **Example**:
     ```c
     BigInt* gcd = gcdI(num1, num2);
     ```

#### 10. `BigInt* lcmI(BigInt* num1, BigInt* num2)`
   - **Purpose**: Computes the least common multiple.
   - **Time Complexity**: O(m * log n).
   - **Example**:
     ```c
     BigInt* lcm = lcmI(num1, num2);
     ```

#### 11. `void freeI(BigInt* num)`
   - **Purpose**: Releases memory occupied by a `BigInt`.
   - **Time Complexity**: O(n).
   - **Example**:
     ```c
     freeI(num);
     ```

### Time Complexity Breakdown
- **Addition/Subtraction**: O(max(m, n))
- **Multiplication**: O(m * n)
- **Division/Modulus**: O(m * log n)
- **Exponentiation**: O(log n * m)
- **GCD**: O(m * log n)
- **LCM**: O(m * log n)

---

