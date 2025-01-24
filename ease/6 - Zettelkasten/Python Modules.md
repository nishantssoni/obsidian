2025-01-18 23:27

Status:

Tags: [[python]] [[modules]]

# Python Modules


A **module** is a file that contains Python definitions, such as functions, classes, and variables, along with runnable code. Modules allow you to structure and organize your Python programs.

---

### **1. Importing Modules**

You can import a module into your code to use its functions and classes. Here are some ways to import and use modules:

#### **Basic Import**

```python
import datetime
print(datetime.datetime.now())  # Prints the current date and time
```

Output:

```plaintext
datetime.datetime(2021, 5, 6, 5, 31, 30, 808483)
```

#### **Importing with Renaming (Alias)**

You can give a module an alias using `as`, which can make your code cleaner, especially for long module names.

```python
import math as m
print(m.sqrt(16))  # Outputs: 4.0
```

#### **Importing Specific Functions or Variables**

You can import specific functions or variables from a module, rather than the entire module.

```python
from math import sqrt, pi
print(sqrt(25))  # Outputs: 5.0
print(pi)        # Outputs: 3.141592653589793
```

#### **Importing All Functions (Wildcard Import)**

Using `*` allows you to import all functions and variables from the module. However, this is not recommended in larger programs because it can make it unclear where certain functions or variables are coming from.

```python
from math import *
print(sin(pi/2))  # Outputs: 1.0
```

---

### **2. `dir()` Function**

The `dir()` function is used to get a list of all the names defined inside a module, including functions, classes, and variables. It helps you discover the contents of a module.

Example:

```python
import math
print(dir(math))  # Outputs a list of all functions and constants in the math module
```

---

### **Summary of Import Statements**

- **`import module_name`**: Imports the entire module.
- **`import module_name as alias`**: Imports the module and gives it an alias for easier use.
- **`from module_name import specific_item`**: Imports specific items (functions, classes, variables) from the module.
- **`from module_name import *`**: Imports all items from the module (not recommended for large projects).
- **`dir(module_name)`**: Lists all defined names in the module.

# References