2025-01-18 23:11

Status:

Tags: [[python]] [[data_types]] [[data_structure]] [[string]]

# Python Strings


### **1. Definition and Basic Properties**

- **String**: A string is a sequence of characters, which can be represented as Unicode (default) or ASCII.
    
    - Example:
        
        ```python
        my_str = "kl"  # String of characters
        ```
        
- **Encoding**: The conversion of characters into numbers (e.g., converting 'a' to 97) is called **encoding**.
    
    - Example:
        
        ```python
        my_str = str(1)  # Converts integer 1 to string
        ```
        
- **Immutability**: Strings in Python are **immutable**, meaning once created, their content cannot be modified.
    

---

### **2. String Operations**

- **Accessing Characters**: You can access characters in a string using indexing (like a list).
    
    - Example:
        
        ```python
        my_str = "hello"
        print(my_str[0])  # Output: 'h'
        ```
        
- **Concatenation**: You can concatenate strings using the `+` operator.
    
    - Example:
        
        ```python
        str1 = "Hello"
        str2 = " World"
        print(str1 + str2)  # Output: "Hello World"
        ```
        
- **Iteration**: You can loop through each character in a string using a `for` loop.
    
    - Example:
        
        ```python
        for char in "hello":
            print(char)
        ```
        
- **Common String Methods**:
    
    - `lower()`: Converts the string to lowercase.
    - `upper()`: Converts the string to uppercase.
    - `join()`: Joins elements of a sequence into a string.
    - `split()`: Splits the string into a list of substrings.
    - `find()`: Returns the index of the first occurrence of a substring.
    - `replace()`: Replaces a substring with another.
    
    Example:
    
    ```python
    my_str = "Bad Morning"
    print(my_str.replace("Bad", "Good"))  # Output: "Good Morning"
    ```
    

---

### **3. Palindrome Check**

To check if a string is a palindrome:

1. Convert the string to lowercase.
2. Reverse the string.
3. Compare the original and reversed strings.

```python
my_str = 'mADam'
# Convert to lowercase
my_str = my_str.lower()

# Reverse the string
revStr = reversed(my_str)

# Check if the string is equal to its reversed version
if list(revStr) == list(my_str):
    print("Given string is palindrome")
else:
    print("Given string is not palindrome")
```

Output:

```plaintext
Given string is palindrome
```

---

### **4. Sorting Words Alphabetically**

To sort words in a string alphabetically:

1. Split the string into a list of words.
2. Sort the list.
3. Print each sorted word.

```python
my_str = "python program to sort word in alphabetical order"
# Split string into words
wrds = my_str.split()

# Sort the list of words
wrds.sort()

# Print sorted words
for word in wrds:
    print(word)
```

Output:

```plaintext
alphabetical
In
Order
Program
Python
Sort
to
```

---

### **Summary**

- Strings are sequences of characters that can be manipulated using various methods like `lower()`, `upper()`, `split()`, and `replace()`.
- Palindrome checks involve comparing a string with its reversed version.
- Sorting words in a string can be achieved by splitting the string, sorting the resulting list, and printing the sorted words.

# References