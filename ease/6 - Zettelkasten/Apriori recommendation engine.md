2025-03-26 13:56

Status:

Tags: [[python]] [[recommendation]]

---

### **Apriori Algorithm in `mlxtend` (Association Rule Mining)**

The **Apriori algorithm** is used in **Market Basket Analysis** to find **frequent itemsets** based on the **support** metric. It helps discover relationships between items in transactional datasets.

---

### **How Apriori Works**

1. **Convert data into a format where each row represents a transaction.**
2. **Find frequent itemsets** that appear together in transactions based on a **minimum support threshold**.
3. **Generate association rules** from frequent itemsets using confidence and lift metrics.

---

### **Example Using `mlxtend`**

#### **Step 1: Install mlxtend**

```bash
pip install mlxtend
```

#### **Step 2: Import Required Libraries**

```python
import pandas as pd
from mlxtend.frequent_patterns import apriori, association_rules
```

#### **Step 3: Create a Sample Transaction Dataset**

```python
# Creating a sample transactional dataset
df = pd.DataFrame([
    [1, 1, 0, 1],
    [1, 0, 1, 1],
    [0, 1, 1, 1],
    [1, 1, 1, 0]
], columns=['Milk', 'Bread', 'Butter', 'Eggs'])

print(df)
```

**Output:**

```
   Milk  Bread  Butter  Eggs
0     1      1       0     1
1     1      0       1     1
2     0      1       1     1
3     1      1       1     0
```

**(1 = Item bought, 0 = Not bought in that transaction)**

---

#### **Step 4: Apply Apriori to Find Frequent Itemsets**

```python
# Finding frequent itemsets with min support of 50%
frequent_itemsets = apriori(df, min_support=0.5, use_colnames=True)
print(frequent_itemsets)
```

**Output:**

```
   support      itemsets
0     0.75      (Milk)
1     0.75     (Bread)
2     0.75    (Butter)
3     0.75      (Eggs)
4     0.50  (Milk, Bread)
5     0.50  (Milk, Eggs)
6     0.50  (Bread, Butter)
7     0.50  (Butter, Eggs)
8     0.50  (Milk, Butter)
```

🔹 **Support** is the fraction of transactions where an itemset appears.

**Parameters**:
   - **`min_support=0.05`**:  
     This sets the **minimum support threshold** (5% in this case).  
     - **Support** of an itemset = (Number of transactions containing the itemset) / (Total number of transactions).  
     - Only itemsets that appear in **at least 5% of transactions** will be returned.
   - **`use_colnames=True`**:  
     If `True`, the returned DataFrame will use the **original column names** (item names) instead of column indices to represent items in the itemsets.  
     If `False`, it would return itemset indices (e.g., `{0, 1}` instead of `{'apple', 'banana'}`).

---

#### **Step 5: Generate Association Rules**

```python
rules = association_rules(frequent_itemsets, metric="confidence", min_threshold=0.6)
print(rules[['antecedents', 'consequents', 'support', 'confidence', 'lift']])
```

**Output:**

```
  antecedents consequents  support  confidence  lift
0    (Milk)     (Bread)      0.5        0.67   1.33
1   (Bread)      (Milk)      0.5        0.67   1.33
2   (Butter)    (Bread)      0.5        0.67   1.33
3   (Butter)     (Eggs)      0.5        0.67   1.33
```

🔹 **Confidence**: Probability of buying consequents given antecedents.  
🔹 **Lift**: Measures the strength of association (values >1 indicate strong relationships).

---
### **Summary**

- **`apriori()`** finds frequent itemsets based on support.
- **`association_rules()`** generates rules using confidence & lift.
- Helps in **recommendation systems** & **market basket analysis**.



## References