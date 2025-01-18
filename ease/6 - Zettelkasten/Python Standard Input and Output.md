2025-01-18 22:03

Status: #code

Tags:[[python]] [[fileio]]

# Python Standard Input and Output

### Python Standard Input and Output

Python provides simple ways to handle input and output operations. Here's a concise explanation:

---

### **Standard Output**

- **Using `print()` Function**: Displays information to the user.

#### **Examples**:

1. **Using `str.format()`**:
    
    ```python
    print('{a} {b}'.format(a=1, b=2))
    ```
    
    - Output: `1 2`
    - `{a}` and `{b}` are placeholders replaced with values of `a` and `b`.
2. **Using f-Strings (Python 3.6+)**:
    
    ```python
    name = 'John'
    roll = 42
    print(f'Hi, my name is {name} and my roll no is {roll}')
    ```
    
    - Output: `Hi, my name is John and my roll no is 42`
    - Variables are directly embedded in the string using curly braces `{}`.

---

### **Standard Input**

- **Using `input()`**: Reads data entered by the user as a string.

#### **Example**:

```python
user_input = input("Enter something: ")
print(f'You entered: {user_input}')
```

- **Input**: `Hello`
- **Output**: `You entered: Hello`

---

# References