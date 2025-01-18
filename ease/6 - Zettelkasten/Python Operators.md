2025-01-18 22:14

Status: 

Tags:[[python]] [[operators]]

# Python Operators


Operators are special symbols in Python that allow performing arithmetic or logical computations. Here's a breakdown of the key types and their functionalities:

---

### 1. **Basic Explanation**

- **Example**: In `2 + 3`, `+` is the operator, while `2` and `3` are operands.

---

### 2. **Types of Operators**

#### **Arithmetic Operators**

- **Symbols**: `+`, `-`, `*`, `/`, `%`, `//`, `**`
- **Purpose**: Perform mathematical operations like addition, subtraction, etc.
- **Examples**:
    - `15 // 2 = 7` (Floor division: nearest integer ≤ value)
    - `-15 // 2 = -8` (Similar logic for negative numbers)

#### **Comparison Operators**

- **Symbols**: `<`, `>`, `!=`, `==`, `>=`, `<=`
- **Purpose**: Compare two values and return a boolean (`True`/`False`).

#### **Logical Operators**

- **Keywords**: `and`, `or`, `not`
- **Purpose**: Combine conditional statements.
- **Examples**:
    - `True and False → False`
    - `True or False → True`

#### **Bitwise Operators**

- **Symbols**: `&`, `|`, `^`, `~`, `>>`, `<<`
- **Purpose**: Perform bit-level operations on integers.
- **Examples**:
    - `a = 10 (1010 in binary), b = 4 (0100 in binary)`
        - `a & b → 0` (`1010 & 0100 = 0000`)
        - `a | b → 14` (`1010 | 0100 = 1110`)
    - **Right Shift**: `a >> b`
    - **Left Shift**: `a << b`

#### **Assignment Operators**

- **Symbols**: `=`, `+=`, `-=`, `*=`, `/=`, `%=` `//=` `**=`, `&=`, `|=`
- **Purpose**: Assign values to variables or modify them in place.
- **Example**: `a += 10` is equivalent to `a = a + 10`.

#### **Identity Operators**

- **Keywords**: `is`, `is not`
- **Purpose**: Check if two variables point to the same memory location.
- **Note**: Ineffective for complex data types (e.g., lists, tuples).

#### **Membership Operators**

- **Keywords**: `in`, `not in`
- **Purpose**: Check if a value exists in a sequence (e.g., list, tuple, string).
- **Dictionaries**: Work for keys, not values.

---



# References