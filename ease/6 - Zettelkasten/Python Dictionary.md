2025-01-18 23:09

Status:

Tags:[[python]] [[data_types]] [[data_structure]]

# Python Dictionary


### **1. Basics of Dictionaries**

- **Definition**: A dictionary is an unordered collection of **key-value pairs**, where each key is unique and used to access its corresponding value.
    
    - Example:
        
        ```python
        my_dict = {1: "nishant", 2: "soni"}
        ```
        
- **Creating Dictionaries**:
    
    - You can also create a dictionary using the `dict()` constructor, passing a list of tuples.
        
        ```python
        my_dict = dict([('a', 234), ('b', 97438), ('c', 4987)])
        ```
        
- **Time Complexity**: Searching for a key in a dictionary has **O(1)** time complexity, making it very efficient.
    

---

### **2. Dictionary Operations**

- **Accessing Values**:
    
    - You can access values by using their respective keys. If the key does not exist, using square brackets (`[]`) raises a `KeyError`. However, using `.get(key)` will return `None` if the key does not exist.
        
        ```python
        my_dict = {1: "nishant", 2: "soni"}
        print(my_dict[1])  # Output: "nishant"
        print(my_dict.get(3))  # Output: None
        ```
        
- **Adding or Updating Key-Value Pairs**:
    
    - You can add new key-value pairs by assigning a value to a new key:
        
        ```python
        my_dict["address"] = "ranchi"
        print(my_dict)  # Output: {1: "nishant", 2: "soni", "address": "ranchi"}
        ```
        
- **Removing Elements**:
    
    - **`dict.pop(key)`**: Removes the key-value pair with the specified key and returns the value.
        
        ```python
        my_dict.pop(2)  # Removes and returns the value "soni"
        ```
        
    - **`dict.popitem()`**: Removes and returns a random key-value pair.
        
        ```python
        my_dict.popitem()  # Removes and returns a random pair
        ```
        
    - **`del dict[key]`**: Deletes a specific key-value pair.
        
        ```python
        del my_dict[1]  # Removes the key-value pair with key 1
        ```
        
- **Clearing the Dictionary**:
    
    - **`dict.clear()`**: Removes all key-value pairs from the dictionary.
        
        ```python
        my_dict.clear()  # Clears the dictionary
        ```
        

---

### **3. Useful Dictionary Methods**

- **`dict.fromkeys(list, value)`**: Creates a new dictionary where the keys are taken from the given list, and the values are set to the specified value.
    
    - Example:
        
        ```python
        subject = {}.fromkeys(['maths', 'eng', 'bio'], 0)
        print(subject)  # Output: {'maths': 0, 'eng': 0, 'bio': 0}
        ```
        
- **`dict.items()`**: Returns the dictionary as a list of tuples, where each tuple is a key-value pair.
    
    - Example:
        
        ```python
        items = my_dict.items()
        print(items)  # Output: [(1, "nishant"), ("address", "ranchi")]
        ```
        
- **`dict.keys()`**: Returns a list of keys in the dictionary.
    
    - Example:
        
        ```python
        keys = my_dict.keys()
        print(keys)  # Output: [1, "address"]
        ```
        
- **`dict.values()`**: Returns a list of values in the dictionary.
    
    - Example:
        
        ```python
        values = my_dict.values()
        print(values)  # Output: ["nishant", "ranchi"]
        ```
        
- **`dict.copy()`**: Creates a shallow copy of the dictionary.
    
    - Example:
        
        ```python
        copied_dict = my_dict.copy()
        print(copied_dict)
        ```
        

---

### **4. Dictionary Comprehension**

- **Creating a Dictionary using Comprehension**:
    
    - Example:
        
        ```python
        my_dict = {k: (k**5) for k in range(10)}
        print(my_dict)
        # Output: {0: 0, 1: 1, 2: 32, 3: 243, 4: 1024, 5: 3125, 6: 7776, 7: 16807, 8: 32768, 9: 59049}
        ```
        
- **Filtering a Dictionary using Comprehension**:
    
    - Example:
        
        ```python
        new_dict = {k: v for k, v in my_dict.items() if v % 2 == 0}
        print(new_dict)
        # Output: {0: 0, 2: 32, 4: 1024, 6: 7776, 8: 32768}
        ```
        

---

### **Key Points**

- Dictionaries store key-value pairs, with unique keys and mutable values.
- Operations like adding, removing, and updating key-value pairs are easy and efficient.
- **Dictionary comprehension** provides a concise way to create or modify dictionaries based on conditions.

# References