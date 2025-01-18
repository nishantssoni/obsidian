2025-01-18 21:47

Status: #basic

Tags:[[python]] [[identifiers]]

# Python Keywords and Identifiers
### Python Coding Practices and Syntax Guidelines

1. **Comments in Python**
    
    - Use `#` for single-line comments.
        
        ```python
        # This is a single-line comment
        ```
        
    - Use triple quotes (`"""` or `'''`) for multi-line comments or docstrings.
        
        ```python
        """
        This is a multi-line comment
        used to explain code in detail.
        """
        ```
        
2. **Indentation**
    
    - Python uses indentation (preferably 4 spaces per level) to define blocks of code, replacing traditional braces `{}`.
        
        ```python
        if True:
            print("This block is indented")
        ```
        
3. **Code Readability**
    
    - Write code across multiple lines to enhance readability.
        - Use a backslash `\` for line continuation.
            
            ```python
            total = 1 + 2 + 3 + \
                    4 + 5
            ```
            
        - Alternatively, enclose expressions in parentheses to avoid using `\`.
            
            ```python
            total = (1 + 2 + 3 +
                     4 + 5)
            ```
            
4. **Statements in Python**
    
    - Instructions written in Python are called statements.
        - **Single-line statement:**
            
            ```python
            print("This is a single-line statement.")
            ```
            
        - **Multi-line statement:** Achieved by breaking long code lines as shown above.
5. **Multiple Statements in a Single Line**
    
    - Use a semicolon `;` to separate multiple statements in one line.
        
        ```python
        a = 12; b = 13; print(a + b)
        ```
        

### Summary

By following these practices, you can write clean, readable, and efficient Python code. Proper use of comments, indentation, and line formatting makes your code easier to maintain and understand.

# References