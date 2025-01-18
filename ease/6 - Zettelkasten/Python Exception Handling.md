2025-01-18 23:45

Status: #code 

Tags: [[python]] [[exception_handling]]

# Python Exception Handling

### Exception Handling in Python

#### Types of Errors

- **Syntax Errors**: These occur when the structure of the code doesn't follow Python's grammar rules. Example:
    
    ```python
    if a < 3
    # SyntaxError: invalid syntax
    ```
    
- **Runtime Errors (Exceptions)**: These occur when the program is running. Example:
    
    ```python
    1 / 0
    # ZeroDivisionError: integer division or modulo by zero
    ```
    

#### Built-in Exceptions

Python provides many built-in exceptions, such as:

- `ArithmeticError`
- `AttributeError`
- `IOError`
- `ZeroDivisionError`
- And many more.

You can check the available exceptions using `dir(__builtins__)`.

#### Exception Handling with `try`, `except`, and `finally`

- **Try-Except**: The `try` block contains code that may raise an exception, and the `except` block contains code to handle that exception.
    
    ```python
    try:
        # risky code
    except:
        # exception handling code
    ```
    
- **Example with `try` and `except`**:
    
    ```python
    import sys
    lst = ['b', 0, 2]
    for entry in lst:
        try:
            print("The entry is", entry)
            r = 1 / int(entry)
        except:
            print("Oops!", sys.exc_info()[0],"occured.")
            print("Next entry.")
    ```
    
- **Catching Specific Exceptions**: Instead of catching all exceptions, it is better to catch specific ones.
    
    ```python
    try:
        # code
    except ValueError:
        # handle ValueError
    except ZeroDivisionError:
        # handle ZeroDivisionError
    ```
    
- **Raising Exceptions**: You can raise exceptions intentionally using `raise`.
    
    ```python
    raise ValueError("Error:Entered negative number")
    ```
    
- **`try`...`finally`**: The `finally` block is always executed, regardless of whether an exception occurred or not. This is useful for resource cleanup.
    
    ```python
    try:
        f = open('sample.txt')
        # perform file operations
    except:
        # handle exceptions
    finally:
        f.close()  # always executed
    ```
    

#### Example: Handling Different Exceptions

```python
import sys
lst = ['b', 0, 2]

for entry in lst:
    try:
        print("****************************")
        print("The entry is", entry)
        r = 1 / int(entry)
    except ValueError:
        print("This is a ValueError.")
    except ZeroDivisionError:
        print("This is a ZeroError.")
    except:
        print("Some other error")
```

#### Raising an Exception

```python
try:
    num = int(input("Enter a positive integer:"))
    if num <= 0:
        raise ValueError("Error: Entered negative number")
except ValueError as e:
    print(e)
```

# References