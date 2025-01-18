2025-01-18 23:05

Status:

Tags:[[python]] [[data_types]] [[data_structure]]

# Python Tuples

---

### **1. Tuple Basics**

- **Definition**: A tuple is similar to a list but **immutable**, meaning its elements cannot be modified after creation. Tuples are defined by parentheses `()`.
    
    - Example:
        
        ```python
        my_tuple = (1, 2, 3)
        ```
        
- **Single Element Tuple**: To create a tuple with one element, a trailing comma is required.
    
    ```python
    a = ('satish',)  # Valid tuple with one element
    type(a)  # Returns <class 'tuple'>
    ```
    
    Without the comma, it is treated as a regular element:
    
    ```python
    a = ('satish')  # This is a string, not a tuple
    type(a)  # Returns <class 'str'>
    ```
    

---

### **2. Tuple Operations**

- **Immutability**: Once a tuple is created, its elements cannot be changed.
    
    ```python
    my_tuple = (1, 2, 3)
    my_tuple[1] = 4  # This will raise a TypeError
    ```
    
- **Slicing**: You can slice a tuple similarly to a list.
    
    ```python
    tup = (1, 2, 3, 4, 5)
    sliced = tup[1:4:2]  # Returns (2, 4)
    ```
    
- **Mutable Elements in a Tuple**: If an element inside a tuple is a mutable object (e.g., a list), you can modify that mutable object.
    
    ```python
    t = (1, 2, 3, 4, ['nishant', 'sony'], 5)
    t[4][1] = 'soni'  # Valid, as the list inside the tuple is mutable
    print(t)  # (1, 2, 3, 4, ['nishant', 'soni'], 5)
    ```
    

---

### **3. Tuple Operations**

- **Concatenation**: You can concatenate (add) two tuples.
    
    ```python
    t = (1, 2, 3)
    t2 = (4, 5, 6)
    t += t2  # Concatenates t2 to t
    print(t)  # (1, 2, 3, 4, 5, 6)
    ```
    
- **Repetition**: Use the `*` operator to repeat the tuple elements.
    
    ```python
    t = ("nishant",) * 4  # Repeats the tuple four times
    print(t)  # ('nishant', 'nishant', 'nishant', 'nishant')
    ```
    
- **Deletion**: You can delete the entire tuple using `del`.
    
    ```python
    del t  # Deletes the whole tuple
    ```
    

---

### **4. Tuple Methods**

- **`tuple.count(element)`**: Returns the number of occurrences of an element in the tuple.
    
    ```python
    tup = (1, 2, 2, 3)
    tup.count(2)  # Returns 2
    ```
    
- **`tuple.index(element)`**: Returns the index of the first occurrence of the element.
    
    ```python
    tup.index(2)  # Returns 1 (first occurrence of 2)
    ```
    
- **Membership Test**:
    
    - `element in tuple` checks if the element is in the tuple.
    
    ```python
    2 in tup  # Returns True
    ```
    
    - `element not in tuple` checks if the element is not in the tuple.
    
    ```python
    5 not in tup  # Returns True
    ```
    
- **Other Operations**:
    
    - **`len(tuple)`**: Returns the length of the tuple.
        
        ```python
        len(tup)  # Returns 4
        ```
        
    - **`sorted(tuple)`**: Returns a sorted copy of the tuple (as a list).
        
        ```python
        sorted(tup)  # Returns [1, 2, 2, 3]
        ```
        
    - **`min(tuple)`**: Returns the smallest element.
        
        ```python
        min(tup)  # Returns 1
        ```
        
    - **`max(tuple)`**: Returns the largest element.
        
        ```python
        max(tup)  # Returns 3
        ```
        
    - **`sum(tuple)`**: Returns the sum of the elements.
        
        ```python
        sum(tup)  # Returns 8 (1 + 2 + 2 + 3)
        ```
        

---



# References