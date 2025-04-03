2025-03-26 13:49

Status:

Tags: [[pandas]]

---
## pivot and pivot table

Here's a simple example demonstrating the difference between `pivot()` and `pivot_table()` in **pandas**.

### **Sample DataFrame**

```python
import pandas as pd

data = {
    'date': ['2024-03-25', '2024-03-25', '2024-03-26', '2024-03-26', '2024-03-26'],
    'product': ['A', 'B', 'A', 'B', 'A'],
    'sales': [100, 200, 150, 250, 180]
}

df = pd.DataFrame(data)
print(df)
```

#### **Using `pivot()`**

```python
df_pivot = df.pivot(index='date', columns='product', values='sales')
print(df_pivot)
```

**Output:**

```
product          A      B
date                    
2024-03-25    100    200
2024-03-26    150    250
```

🔹 **`pivot()` works only if there are unique index-column pairs.** If duplicate entries exist for a combination of `date` and `product`, it will raise an error.

---

#### **Using `pivot_table()`**

If there are duplicate values, `pivot_table()` helps by aggregating them:

```python
df_pivot_table = df.pivot_table(index='date', columns='product', values='sales', aggfunc='sum')
print(df_pivot_table)
```

**Output:**

```
product          A      B
date                    
2024-03-25    100    200
2024-03-26    330    250
```

🔹 Here, `pivot_table()` **automatically sums up duplicate entries** (150 + 180 for `A` on `2024-03-26`).

👉 **Use `pivot()` for strict reshaping** (when unique values exist), and **use `pivot_table()` for summarization** when duplicates exist. 🚀


## References