2025-01-18 21:50

Status: #basic 

Tags:[[python]] [[data_types]]

# Python Variables and Data Types

---

### **1. Variables**

- A variable is a memory location used to store data.
- **No Declaration Needed**: In Python, you don't need to declare a variable before assigning a value.
- **Examples**:
    - `a, b = 10, 'Hi'` → Assigns values to multiple variables in one line.
    - `a = b = c = 22` → Assigns the same value to multiple variables.

---

### **2. Memory Management**

- **`id()` Function**: Prints the memory address of the stored value.
    
    ```python
    a = 10
    print(id(a))
    ```
    
- **Shared Addresses**: Variables with the same value share the same memory location until one is modified. Python optimizes this to save space.

---

### **3. Object-Oriented Nature**

- **Everything in Python is an Object**: Even primitive data types like integers and strings are objects.
- **Type Identification**:
    - `type(variable)` → Returns the class/type of the variable.
    - `isinstance(object, class)` → Returns `True` if the object belongs to the specified class.

---

### **4. Data Types**

#### **Number**

- Includes `int`, `float`, and `complex` types.
- Example of a complex number: `2 + 3j`.

#### **Boolean**

- Represents `True` and `False`.

#### **String**

- A sequence of Unicode characters enclosed in quotes.
- Strings are **indexable** and **slicable**.
    - Example: `str[5:]` → Prints from the 5th index to the end.

#### **List**

- Ordered collection of items, defined with square brackets `[]`.
- Mutable (modifiable) and supports indexing.
    - Example: `list('Hello') → ['H', 'e', 'l', 'l', 'o']`.

#### **Tuple**

- Immutable, ordered collection of items, defined with parentheses `()`.
- Can store multiple data types and supports indexing.

#### **Set**

- Unordered collection of unique items, defined with curly braces `{}`.
- Does not support indexing.

#### **Dictionary**

- Unordered collection of key-value pairs, defined with curly braces `{}`.
- Values are accessed using keys.
    - Example: `my_dict = {'a': 1, 'b': 2}` → `my_dict['a']` returns `1`.

---

### **5. Data Conversion**

- Python supports data type conversion if the value is valid in both types.
- **Examples**:
    - `int('5') → 5`
    - `float('5.5') → 5.5`
    - `list('Hello') → ['H', 'e', 'l', 'l', 'o']`

---



# References