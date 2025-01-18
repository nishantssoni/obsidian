2025-01-19 00:05

Status:

Tags: [[numpy]] 

# Numpy Indexing and Slicing


### Indexing and Slicing in NumPy

NumPy allows accessing and modifying elements in an array using indexing and slicing, which are similar to other Python sequences like lists. Here's a breakdown:

#### 1. **Indexing**

- You can access individual elements of a NumPy array just like a Python list.

```python
a = np.arange(10)
print(a[5])  # Output: 5
```

For multi-dimensional arrays, you use tuples of integers to access elements.

```python
a = np.diag([1, 2, 3])
print(a[2, 2])  # Output: 3
```

You can also assign values to elements in the array:

```python
a[2, 1] = 5
print(a)  
# Output: 
# [[1 0 0]
#  [0 2 0]
#  [0 5 3]]
```

#### 2. **Slicing**

- Slicing in NumPy follows the pattern `[start: end (exclusive) : step]`.

Example:

```python
a = np.arange(10)
print(a[1:8:2])  # Output: array([1, 3, 5, 7])
```

You can also combine slicing and assignment:

```python
a = np.arange(10)
a[5:] = 10
print(a)  # Output: array([ 0,  1,  2,  3,  4, 10, 10, 10, 10, 10])
```

Assigning reversed values:

```python
b = np.arange(5)
a[5:] = b[::-1]  # Output: array([0, 1, 2, 3, 4, 4, 3, 2, 1, 0])
```

#### 3. **Copies vs. Views**

- **View:** When you slice an array, it creates a view of the original array. Modifying the view will affect the original array.

Example:

```python
a = np.arange(10)
b = a[::2]
print(np.shares_memory(a, b))  # Output: True

b[0] = 10
print(a)  # Output: array([10,  1,  2,  3,  4,  5,  6,  7,  8,  9])
```

- **Copy:** If you want to avoid modifying the original array, you can create a copy.

Example:

```python
c = a[::2].copy()
print(np.shares_memory(a, c))  # Output: False

c[0] = 10
print(a)  # Output: array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```

#### 4. **Fancy Indexing**

- Fancy indexing allows you to index arrays using boolean arrays or arrays of integers.

**Boolean Indexing:** You can create a boolean mask to filter elements based on a condition.

Example:

```python
a = np.random.randint(0, 20, 15)
print(a)

mask = (a % 2 == 0)  # True for even numbers
print(a[mask])  # Output: array of even numbers

a[mask] = -1  # Assign new values
print(a)
```

**Integer Indexing:** You can also index arrays with an array of integers.

Example:

```python
a = np.arange(0, 100, 10)
print(a)
print(a[[2, 3, 2, 4, 2]])  # Output: array([20, 30, 20, 40, 20])

# Assign new values
a[[9, 7]] = -200
print(a)  # Output: array([   0,   10,   20,   30,   40,   50,   60, -200,   80, -200])
```

In summary, **indexing** provides efficient access to individual elements, while **slicing** allows you to create subsets of an array. **Fancy indexing** gives more flexibility, especially when working with conditions or multiple indices.

# References