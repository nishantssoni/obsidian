# Chapter 2: Python for Data Science — Introduction

## 1. Environment Setup

To establish a robust data science environment, the Anaconda distribution is recommended due to its comprehensive package management system.

> [!TIP]
> 
> Resource Recommendation: For in-depth tutorials on environment management, Corey Schafer’s YouTube series is highly regarded in the community.

### Virtual Environment Management

Managing environments prevents dependency conflicts. Below are the essential commands for configuring `conda` and managing environments.

Bash

```
# Disable the default activation of the base environment on startup
conda config --set auto_activate_base False

# Activate the root environment manually (Linux/macOS)
source ~/anaconda3/bin/activate root

# Alternatively, use the standard conda command
conda activate base

# Install packages (e.g., TensorFlow)
pip3 install --upgrade tensorflow
```

## 2. Why Python?

Python is the industry standard for data science and machine learning for several reasons:

- **Ease of Adoption:** Simple syntax reduces the learning curve.
- **Ecosystem:** Extensive libraries for Machine Learning (ML) and Artificial Intelligence (AI).
- **Interactivity:** Jupyter Notebooks allow for iterative coding and data visualization.
- **General Purpose:** Beyond data science, Python is robust for web development, automation, and scripting.
    
C:\Users\nish\Downloads\obsidian-main\obsidian-main\ease\4 - Index\applied ai course.md
## 3. Keywords and Identifiers

### Keywords

Keywords are reserved words used by the Python compiler to understand the program structure. They cannot be used as variable names.
- **Case Sensitivity:** Keywords are case-sensitive (e.g., `True`, `False`, `None` are capitalized).
- **Total Count:** There are approximately 35 keywords in modern Python.
    

**Programmatic check for keywords:**

Python

```
import keyword

# Print all keywords
print(keyword.kwlist)

# Print total count
print(f"Total number of keywords: {len(keyword.kwlist)}")
```

### Identifiers

Identifiers are names given to entities such as variables, functions, and classes.

- **Rules:** Must consist of letters, digits, or underscores (`_`). Cannot start with a digit. No special characters allowed.
    

## 4. Syntax: Comments and Indentation

- **Comments:** Use `#` for single-line comments. Use triple quotes (`"""` or `'''`) for multi-line documentation.
    
- **Indentation:** Python uses whitespace (standard convention is 4 spaces) to define code blocks, replacing the braces `{}` found in languages like C++ or Java.
    
- **Line Continuation:** Use a backslash `\` to break long lines, or wrap the expression in parentheses `()`.
    
- **Multi-statement Lines:** Semicolons `;` can separate multiple statements on a single line, though this is generally discouraged for readability.
    

## 5. Variables and Data Types

In Python, a variable is a reference to a memory location. Explicit declaration is not required.

> [!NOTE]
> 
> Object Model: Everything in Python is an object. You can use type(variable) to check the class and isinstance(object, class) to verify inheritance.

### Memory Optimization

Python optimizes memory by assigning the same memory address to immutable variables with identical short values (interning).

Python

```
a = 10
b = 10
# Both point to the same address
print(id(a) == id(b)) # Output: True
```

### Data Types Overview

|**Type**|**Mutable?**|**Description**|
|---|---|---|
|**Number**|No|Integers, Floats, and Complex numbers (e.g., `2+3j`).|
|**Boolean**|No|`True` and `False`.|
|**String**|No|Unicode character sequence. Indexable and slicable.|
|**Tuple**|No|Ordered sequence defined by `()`. Faster than lists.|
|**List**|Yes|Ordered sequence defined by `[]`.|
|**Set**|Yes|Unordered collection of unique items defined by `{}`. No indexing.|
|**Dictionary**|Yes|Key-Value pairs defined by `{k:v}`. Values accessed via keys.|

> [!QUESTION]
> 
> How does slicing work?
> 
> Slicing allows access to subsets of data. Str[5:] extracts characters from index 5 to the end of the string.

## 6. Standard Input and Output

Modern Python favors f-strings for string formatting due to improved readability and performance.

Python

```
name = "Alice"
roll_no = 101

# Legacy format method
print('Name: {a}, Roll: {b}'.format(a=name, b=roll_no))

# Modern f-string (Preferred)
print(f'Name: {name}, Roll: {roll_no}')

# User Input (always returns a string)
user_val = input("Enter value: ")
```

## 7. Operators

Operators facilitate arithmetic and logical computations.

- **Arithmetic:** `+`, `-`, `*`, `/`, `%` (modulo), `**` (exponent).
    
    - _Floor Division (`//`):_ Returns the largest integer less than or equal to the result (e.g., `-15 // 2` results in `-8`).
        
- **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=`.
    
- **Logical:** `and`, `or`, `not`.
    
- **Bitwise:** `&` (AND), `|` (OR), `~` (NOT), `^` (XOR), `>>` (Right Shift), `<<` (Left Shift).
    
- **Assignment:** `=`, `+=`, `-=`, etc.
    
- **Identity:** `is`, `is not`. Checks if two variables point to the same memory object (unlike `==` which checks value equality).
    
- **Membership:** `in`, `not in`. Checks for existence in sequences (lists, strings) or keys in dictionaries.
    

## 8. Control Flow

### Conditional Statements

Python treats `0`, `None`, and empty containers as `False`; all other values are `True`.

Python

```
if condition:
    # Execute if True
elif other_condition:
    # Execute if first condition is False and this is True
else:
    # Execute if all above are False
```

### Loops

- **While Loop:** Executes as long as the condition is true.
    
- **For Loop:** Iterates over a sequence (using `range(start, end, step)`).
    

> [!NOTE]
> 
> Loop else Blocks: Python allows an else clause in loops. The else block executes only if the loop completes normally (i.e., it was not terminated by a break statement).

- **Break:** Exits the nearest enclosing loop immediately.
    
- **Continue:** Skips the rest of the code inside the loop for the current iteration and jumps to the next iteration.
    

---

### Technical Addendum

1. **Small Integer Caching (Interning):** Python pre-allocates integers between -5 and 256. When you assign any variable to a number in this range, Python references the existing object in memory rather than creating a new one. This is why `a = 256; b = 256; a is b` returns `True`, but `a = 257; b = 257; a is b` may return `False` (depending on the compiler implementation).
    
2. **Short-Circuit Evaluation:** In logical operations, Python evaluates expressions from left to right and stops as soon as the result is determined. For `a or b`, if `a` is true, `b` is never evaluated. This is often used for safe execution, such as `if x is not None and x.some_method():`.
    
3. **The Global Interpreter Lock (GIL):** While Python is a general-purpose language, standard CPython implementations contain a GIL that prevents multiple native threads from executing Python bytecodes at once. This is why multi-threading in Python is often used for I/O-bound tasks, while multi-processing is preferred for CPU-bound data science tasks to bypass the GIL.