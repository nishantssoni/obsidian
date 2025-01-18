2025-01-18 22:53

Status:

Tags: [[python]]

# Python Control Flow

### Python Control Flow: `If...else`

---

### **1. Basic `if...else` Statement**

```python
if test_expression:
    # Execute statement(s) if condition is true
```

- The test expression is evaluated, and if it's **True**, the indented statement(s) will execute.

---

### **2. Truthy and Falsy Values**

- In Python, most values are considered **True** in a boolean context, except for:
    
    - `0`
    - `None`
    - `False`
    
    Example:
    
    ```python
    if 1:
        print("True")  # This will execute because 1 is considered True.
    ```
    

---

### **3. `if...elif...else` (Multiple Conditions)**

For checking multiple conditions, use `elif` to add more test expressions and `else` for the default block when none of the conditions are true.

```python
if condition1:
    # Execute if condition1 is true
elif condition2:
    # Execute if condition2 is true
else:
    # Execute if neither condition1 nor condition2 is true
```

---

### **4. Nested `if...else` Statements**

You can nest `if...else` statements within each other to handle more complex logic.

```python
if condition1:
    if condition2:
        # Execute if both condition1 and condition2 are true
    else:
        # Execute if condition1 is true, but condition2 is false
else:
    # Execute if condition1 is false
```

---

### Python Control Flow: Loops

---

### **1. `while` Loop**

The `while` loop runs a block of code as long as a test expression is **True**.

```python
while test_expression:
    # Body of the while loop
```

- The loop continues executing until the condition evaluates to `False`.

#### **`else` in a `while` Loop**

- If the loop terminates **naturally** (i.e., the condition becomes `False`), the `else` block runs.

```python
while test_expression:
    # Body of the while loop
else:
    # Else part of the loop
```

---

### **2. `for` Loop**

The `for` loop is typically used to iterate over a sequence (like a range or list). You can define a starting point, an endpoint, and an optional step size.

```python
for i in range(starting, end, step):
    # Body of the for loop
```

- **`i`** is the loop variable, which takes values from `starting` to `end` with the given step size.

#### **`else` in a `for` Loop**

- Like the `while` loop, you can add an `else` block after a `for` loop. The `else` block runs if the loop terminates without hitting a `break` statement.

```python
for i in range(5):
    # Body of the for loop
else:
    # Else part of the loop (executed if no break occurs)
```

---

### **3. `break` and `continue`**

#### **`break`**

- The `break` statement is used to **exit** the loop prematurely, skipping any further iterations.

```python
for i in range(5):
    if i == 3:
        break  # Exits the loop when i equals 3
```

#### **`continue`**

- The `continue` statement skips the current iteration and moves to the next one in the loop.

```python
for i in range(5):
    if i == 3:
        continue  # Skips the iteration when i equals 3
```

---


# References