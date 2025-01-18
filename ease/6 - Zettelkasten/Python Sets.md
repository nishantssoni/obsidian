2025-01-18 23:07

Status:

Tags:[[python]] [[data_types]] [[data_structure]]

# Python sets


### **1. Sets Basics**

- **Definition**: A set is an unordered collection of **unique** items (no duplicates), **mutable**, and **non-indexable**. They are defined using curly braces `{}`.
    
    - Example:
        
        ```python
        s = {1, 2, 3, 4, 2}
        print(s)  # Output: {1, 2, 3, 4}
        ```
        
        Sets automatically remove duplicates and store only one instance of each element.
- **Indexing Not Allowed**: Sets are unordered, so they do not support indexing.
    
    ```python
    s[2]  # TypeError: 'set' object is not subscriptable
    ```
    

---

### **2. Common Set Operations**

- **Adding Elements**:
    
    - **`set.add(element)`**: Adds a single element to the set.
        
        ```python
        s = {1, 2, 3}
        s.add(4)  # Adds 4 to the set
        print(s)  # Output: {1, 2, 3, 4}
        ```
        
- **Updating Sets**:
    
    - **`set.update(iterable)`**: Adds elements from a list, tuple, or another set.
        
        ```python
        s = {1, 2}
        s.update([3, 4])  # Adds multiple elements
        print(s)  # Output: {1, 2, 3, 4}
        ```
        
- **Removing Elements**:
    
    - **`set.discard(element)`**: Removes an element from the set. No error is raised if the element is not present.
        
        ```python
        s.discard(4)  # Removes 4 if present, does nothing if not present
        print(s)  # Output: {1, 2, 3}
        ```
        
    - **`set.remove(element)`**: Removes an element from the set. Raises a `KeyError` if the element is not found.
        
        ```python
        s.remove(3)  # Removes 3 from the set
        print(s)  # Output: {1, 2}
        ```
        
- **Random Element Removal**:
    
    - **`set.pop()`**: Removes and returns a random element from the set.
        
        ```python
        s = {1, 2, 3}
        removed_item = s.pop()  # Randomly removes one item
        print(s)  # Output: Set with one element removed
        ```
        
- **Clearing the Set**:
    
    - **`set.clear()`**: Removes all elements from the set.
        
        ```python
        s.clear()  # Removes all elements
        print(s)  # Output: set()
        ```
        

---

### **3. Set Operations**

- **Union**: Combines the elements from two sets.
    
    - **`Set1 | Set2`** or **`Set1.union(Set2)`**:
        
        ```python
        set1 = {1, 2}
        set2 = {2, 3}
        print(set1 | set2)  # Output: {1, 2, 3}
        ```
        
- **Intersection**: Returns elements that are common in both sets.
    
    - **`Set1 & Set2`** or **`Set1.intersection(Set2)`**:
        
        ```python
        print(set1 & set2)  # Output: {2}
        ```
        
- **Difference**: Returns elements in the first set but not in the second.
    
    - **`Set1 - Set2`** or **`Set1.difference(Set2)`**:
        
        ```python
        print(set1 - set2)  # Output: {1}
        ```
        
- **Symmetric Difference**: Returns elements in either set but not both.
    
    - **`Set1 ^ Set2`** or **`Set1.symmetric_difference(Set2)`**:
        
        ```python
        print(set1 ^ set2)  # Output: {1, 3}
        ```
        

---

### **4. Set Methods**

- **Subset**: Checks if one set is a subset of another.
    
    - **`set1.issubset(set2)`**: Returns `True` if `set1` is a subset of `set2`.
        
        ```python
        set1 = {1, 2}
        set2 = {1, 2, 3}
        print(set1.issubset(set2))  # Output: True
        ```
        
- **Frozenset**: A frozenset is an immutable version of a set. You cannot modify its elements once created.
    
    ```python
    frozenset_example = frozenset([1, 2, 3, 4])
    print(frozenset_example)  # Output: frozenset({1, 2, 3, 4})
    ```
    

---

### **Key Points**

- Sets are **unordered**, meaning no specific order of elements.
- They only store **unique elements**.
- Operations like **union, intersection, difference**, and **symmetric difference** provide powerful ways to manipulate sets.

# References