2025-01-18 23:34

Status:

Tags: [[python]] [[fileio]]

# Python File Handling


### **File Handling in Python**

File handling in Python is essential for storing data on disk, which is non-volatile, meaning the data persists even when the program is closed. This is in contrast to RAM, which is volatile and loses data when the computer is turned off.

---

### **File Operations Flow**

The basic flow of file input/output (I/O) in Python is:

1. **Open the file**
2. **Read or write data**
3. **Close the file**

---

### **File Modes**

Python provides several modes to interact with files:

- **`'r'`**: Read (default mode). Opens the file for reading.
- **`'w'`**: Write. Opens the file for writing (creates a new file or overwrites an existing one).
- **`'x'`**: Exclusive creation. Raises an error if the file already exists.
- **`'a'`**: Append. Opens the file for appending without truncating it.
- **`'t'`**: Text mode (default). Opens the file in text mode.
- **`'b'`**: Binary mode. Opens the file in binary mode.
- **`'+'`**: Update. Opens the file for updating (reading and writing).

Example:

```python
f = open('example.txt', 'r')  # Open in read mode
f = open('example.txt', 'w')  # Open in write mode
f = open('example.txt', 'a')  # Open in append mode
```

---

### **File Encoding**

When working with text files, specifying the encoding type is recommended to avoid platform differences:

```python
f = open('example.txt', encoding='utf-8')
```

---

### **Closing a File**

Closing a file ensures the data is properly saved and resources are freed. Use the `close()` method:

```python
f.close()
```

To ensure the file is closed even if an exception occurs, use a `try-finally` block:

```python
try:
    f = open('example.txt')
finally:
    f.close()
```

---

### **Writing to a File**

To write data into a file, open the file in `'w'`, `'a'`, or `'x'` mode. The `write()` method is used to write strings or bytes (for binary files).

Example:

```python
f = open('test.txt', 'w')
f.write("This is a First File\n")
f.write("Contains two lines\n")
f.close()
```

---

### **Reading from a File**

Python provides multiple methods to read from a file:

- **`read(size)`**: Reads up to `size` bytes.
- **`readline()`**: Reads a single line.
- **`readlines()`**: Returns a list of lines.

Example:

```python
f = open('test.txt', 'r')
print(f.read())  # Read the entire file
print(f.readline())  # Read the first line
f.seek(0)  # Reset cursor to the beginning
lines = f.readlines()  # Read all lines as a list
print(lines)
```

The `seek()` and `tell()` methods can help control the cursor position:

- **`seek(offset)`**: Moves the cursor to a specific position.
- **`tell()`**: Returns the current cursor position.

---

### **Renaming and Deleting Files**

Use the `os` module for file management:

```python
import os

# Rename file
os.rename('test.txt', 'sample.txt')

# Delete file
os.remove('sample.txt')
```

---

### **Directory and File Management**

Python's `os` module helps with directory and file operations:

- **`getcwd()`**: Get current working directory.
- **`chdir(path)`**: Change the current working directory.
- **`listdir()`**: List files in a directory.
- **`mkdir()`**: Create a new directory.

Example:

```python
import os
os.getcwd()  # Get the current directory
os.chdir("/home/user/")  # Change directory
os.mkdir('new_folder')  # Create a new directory
```

---

### **Removing Non-Empty Directories**

To remove a non-empty directory, use `shutil.rmtree()`:

```python
import shutil
shutil.rmtree('non_empty_directory')  # Remove non-empty directory
```

This provides a complete overview of file handling in Python, from basic file operations to advanced directory management.

# References
[[Python Standard Input and Output]]