2025-01-18 23:15

Status: #long

Tags: [[python]] [[functions]] [[recursive]]

# Python Functions

## part 1
---

### **1. Function Definition**

A function is a group of related statements that perform a specific task. Functions help break down a program into smaller, manageable chunks, making it easier to manage and debug.

```python
def fun(x):
    """This is a docstring to explain the function's purpose."""
    print("I am the body of the function")
    return x
```

- **Docstrings**: Docstrings are optional but highly recommended. They explain the function’s purpose and usage. You can access the docstring using `function_name.__doc__`.
    
- **Return Statement**: The return statement is optional. If no return value is specified, Python returns `None`.
    

---

### **2. Scope and Lifetime of Variables**

- **Scope** refers to where a variable is accessible in the code.
- **Lifetime** refers to the period during which a variable exists in memory.
    - Local variables inside a function are destroyed after the function finishes execution.
    - Global variables remain in memory until explicitly deleted.

---

### **3. Example: Computing HCF (Highest Common Factor)**

```python
def computeHCF(a, b):
    """Computing HCF of two numbers"""
    smaller = b if a > b else a  # concise if-else
    hcf = 1
    for i in range(1, smaller + 1):
        if (a % i == 0) and (b % i == 0):
            hcf = i
    return hcf

num1 = 98
num2 = 78
print('HCF of {0} and {1} is {2}'.format(num1, num2, computeHCF(num1, num2)))
```

Output:

```plaintext
HCF of 98 and 78 is 2
```

---

### **4. Types of Functions**

#### **Built-in Functions**

- **abs()**: Returns the absolute value of a number.
- **all()**: Returns `True` if all elements in an iterable are true, `False` if any element is false.

Example of `all()`:

```python
lst = [1, 2, 3, 4]
print(all(lst))  # Output: True

lst = [0, 1, 2, 3]
print(all(lst))  # Output: False
```

- **any()**: Returns `True` if any element in an iterable is true.
- **dir()**: Returns a list of valid attributes of the object.
- **divmod()**: Returns a tuple of the quotient and remainder of two numbers.
    
    ```python
    print(divmod(16, 3))  # Output: (5, 1)
    ```
    

#### **User-Defined Functions**

- **enumerate()**: Returns a pair of index and value for each element in an iterable.

Example:

```python
nums = [10, 20, 30, 40]
for index, value in enumerate(nums):
    print("Index {0} has value {1}".format(index, value))
```

Output:

```plaintext
Index 0 has value 10
Index 1 has value 20
Index 2 has value 30
Index 3 has value 40
```

---

### **5. Common Functional Programming Functions**

- **filter()**: Filters elements from an iterable based on a condition defined in a function.

Example:

```python
def find_positive_number(num):
    """Returns positive numbers"""
    if num > 0:
        return num

number_list = range(-10, 10)
positive_num_list = list(filter(find_positive_number, number_list))
print(positive_num_list)
```

Output:

```plaintext
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

- **map()**: Applies a function to each item in an iterable and returns a new iterable.

Example:

```python
numbers = [1, 2, 3, 4, 5]
def powerOfTwo(num):
    return num ** 2

squares = list(map(powerOfTwo, numbers))
print(squares)
```

Output:

```plaintext
[1, 4, 9, 16, 25]
```

- **reduce()**: Applies a rolling computation (like accumulation) to each pair of values in a list.

Example:

```python
from functools import reduce

lst = [1, 2, 3, 4, 5]
def multiply(x, y):
    return x * y

product = reduce(multiply, lst)
print(product)
```

Output:

```plaintext
120
```

---

### **6. Functions Recap**

- **isinstance(value, datatype)**: Checks if a value is an instance of the given datatype.
- **enumerate()**: Provides index-value pairs from an iterable.
- **filter()**: Filters elements based on a condition.
- **map()**: Applies a function on all items in an iterable.
- **reduce()**: Applies a rolling computation to a sequence of elements.

These functions enhance the power of functional programming in Python, enabling efficient processing and transformations on data.



## part 2
---

### Function Arguments in Python

### **1. Default Arguments**

- Default arguments allow a function to have predefined values. These values are used if no value is passed for the argument.
- Default arguments should be placed at the end of the parameter list.

Example:

```python
def greet(message="Hello", name="Guest"):
    print(f"{message}, {name}!")

greet()  # Uses default values
greet("Good morning", "Nishant")  # Uses passed values
```

---

### **2. Keyword Arguments (`**kwargs`)**

- `**kwargs` allows a function to accept a variable number of keyword arguments (key-value pairs).
- This is useful when you don’t know in advance how many named arguments will be passed to the function.

Example:

```python
def greet(**kwargs):
    """This function greets the person with their name and message."""
    if kwargs:
        print(f"Hello {kwargs['name']}, {kwargs['msg']}")

greet(name="Nishant", msg="Good morning")
```

Output:

```plaintext
Hello Nishant, Good morning
```

---

### **3. Arbitrary Arguments (`*args`)**

- `*args` allows a function to accept an arbitrary number of positional arguments (like a tuple).
- This is useful when you don’t know how many arguments will be passed to the function.

Example:

```python
def greet(*names):
    """This function greets all the persons in the 'names' tuple."""
    print(names)
    for name in names:
        print(f"Hello, {name}")

greet('Nishant', 'Shekhar', 'Soni', 'Anurag', 'Durgesh')
```

Output:

```plaintext
('Nishant', 'Shekhar', 'Soni', 'Anurag', 'Durgesh')
Hello, Nishant
Hello, Shekhar
Hello, Soni
Hello, Anurag
Hello, Durgesh
```

---

### **4. Recursive Functions**

- Recursive functions call themselves in order to solve a problem.
- The recursion continues until a base condition is met.

Example:

```python
def factorial(num):
    """Return the factorial of a number."""
    return 1 if num == 1 else num * factorial(num - 1)

print(factorial(5))
```

Output:

```plaintext
120
```

---

### **5. Anonymous/Lambda Functions**

- Lambda functions are small, anonymous functions without a name.
- They are commonly used with functions like `filter()`, `map()`, and `reduce()`.

#### Lambda Function Example:

```python
square = lambda x: x**2  # Defining a lambda function
print(square(5))  # Output: 25
```

---

### **6. Lambda Functions with `filter()`, `map()`, and `reduce()`**

- **filter()**: Filters elements of an iterable based on a condition provided by a function.
- **map()**: Applies a function to all items in an iterable.
- **reduce()**: Applies a rolling computation to a list of values.

#### Example with `filter()`:

```python
lst = [1, 2, 3, 4, 5, 6, 7]
new_list = list(filter(lambda x: x % 2 == 0, lst))
print(new_list)
```

Output:

```plaintext
[2, 4, 6]
```

#### Example with `map()`:

```python
lst = [1, 2, 3, 4, 5, 6, 7]
new_list = list(map(lambda x: x**2, lst))
print(new_list)
```

Output:

```plaintext
[1, 4, 9, 16, 25, 36, 49]
```

#### Example with `reduce()`:

```python
from functools import reduce
lst = [1, 2, 3, 4, 5, 6, 7]
product_lst = reduce(lambda x, y: x * y, lst)
print(product_lst)
```

Output:

```plaintext
5040
```

---

### **Summary of Function Argument Types**

- **Default Arguments**: Provide a default value to function parameters.
- **Keyword Arguments (`**kwargs`)**: Allow the passing of a variable number of named arguments.
- **Arbitrary Arguments (`*args`)**: Allow the passing of a variable number of positional arguments.
- **Recursive Functions**: Functions that call themselves.
- **Lambda Functions**: Anonymous functions used in operations like `filter()`, `map()`, and `reduce()`.

# References