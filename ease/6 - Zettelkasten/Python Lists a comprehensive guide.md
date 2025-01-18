2025-01-18 23:01

Status:

Tags:[[python]] [[data_types]] [[data_structure]]

# Python Lists a comprehensive guide


---

### **1. List Basics**

- **Definition**: A list is a sequence data structure in Python, defined by square brackets `[]`. It is **indexable** (can access elements using indices) and **mutable** (can modify elements).
- **Example**:
    
    ```python
    my_list = [1, 2, 3, 'apple', True]
    ```
    

---

### **2. List Operations**

- **Length**: `len(list)` returns the number of elements in the list.
    
    ```python
    len(my_list)  # Returns: 5
    ```
    
- **Adding Elements**:
    
    - `append(element)` adds an element to the end.
        
        ```python
        my_list.append(4)  # Adds 4 to the end
        ```
        
    - `insert(index, element)` adds an element at a specific index.
        
        ```python
        my_list.insert(2, 'banana')  # Inserts 'banana' at index 2
        ```
        
    - `extend(iterable)` extends the list by appending elements from another iterable (like another list).
        
        ```python
        my_list.extend([6, 7])  # Extends the list with elements 6 and 7
        ```
        
- **Removing Elements**:
    
    - `remove(element)` removes the first occurrence of an element.
        
        ```python
        my_list.remove('apple')  # Removes 'apple'
        ```
        
    - `pop(index)` removes an element at the given index and returns it.
        
        ```python
        my_list.pop(2)  # Removes and returns the element at index 2
        ```
        
    - `del list[index]` deletes the element at a specified index.
        
        ```python
        del my_list[1]  # Deletes element at index 1
        ```
        

---

### **3. List Manipulation**

- **Reversing**: `list.reverse()` reverses the original list.
    
    ```python
    my_list.reverse()
    ```
    
- **Sorting**:
    
    - `sorted(list)` returns a sorted copy without modifying the original.
    - `list.sort()` sorts the list in place.
    
    ```python
    sorted_list = sorted(my_list)  # Returns a sorted list
    my_list.sort()  # Sorts the list in place
    ```
    
- **Membership Test**:
    
    - `in` checks if an item is in the list.
    - `not in` checks if an item is not in the list.
    
    ```python
    3 in my_list  # Returns True if 3 is in the list
    10 not in my_list  # Returns True if 10 is not in the list
    ```
    

---

### **4. List Slicing**

- **Slicing** allows extracting a portion of the list.
    
    ```python
    my_list[1:4]  # Returns a new list from index 1 to 3
    my_list[::2]  # Every second element
    ```
    
- **List Concatenation**:
    
    ```python
    new_list = my_list + [7, 8]  # Merges two lists
    ```
    
- **Count Occurrences**:
    
    - `list.count(element)` returns how many times an element appears in the list.
    
    ```python
    my_list.count(2)  # Returns the count of 2 in the list
    ```
    

---

### **5. List Comprehensions**

List comprehensions provide a concise way to create lists based on existing lists or sequences.

- **Basic Syntax**:
    
    ```python
    [expression for item in iterable]
    ```
    
- **Examples**:
    
    - Squares of numbers:
        
        ```python
        square = [i**2 for i in range(10)]
        ```
        
    - Filter even numbers:
        
        ```python
        even_numbers = [i for i in range(10) if i % 2 == 0]
        ```
        
    - Apply a transformation:
        
        ```python
        doubled = [i * 2 for i in [1, 2, 3, 4, 5] if i > 3]
        ```
        
- **Complex Example** (Tuples in a list):
    
    ```python
    lst = [(i, i**2, i**3) for i in range(5)]
    ```
    

---

### **6. Additional List Techniques**

- **Splitting Strings into Lists**:
    
    ```python
    "hello world".split(' ')  # Returns ['hello', 'world']
    ```
    
- **Merging Lists**:
    
    ```python
    new_lst = lst1 + lst2  # Merges lst1 and lst2
    ```
    
- **Transposing a Matrix (Without and With List Comprehension)**:
    
    - Without list comprehension:
        
        ```python
        transposed = []
        for i in range(4):
            lst = [row[i] for row in matrix]
            transposed.append(lst)
        print(transposed)
        ```
        
    - With list comprehension:
        
        ```python
        transposed = [[row[i] for row in matrix] for i in range(len(matrix))]
        print(transposed)
        ```
        

---



# References