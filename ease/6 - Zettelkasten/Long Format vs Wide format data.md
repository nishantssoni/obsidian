2025-03-23 17:56

Status:

Tags: [[pandas]] [[statistics]] [[data_wrangling]]

---
## Long Format vs Wide format data

In **data analysis and machine learning**, datasets can be structured in two main formats:

---

### **1. Long Format (Tidy Format)**

- Each **row represents a single observation**.
- Columns typically contain **variables (attributes)** and **values**.
- Commonly used in **time series data, logs, and relational databases**.

**Example (Sales Data in Long Format):**

|Date|Product|Sales|
|---|---|---|
|2024-03-01|A|100|
|2024-03-01|B|150|
|2024-03-02|A|120|
|2024-03-02|B|180|

📌 **Use case:** Suitable for **grouping, filtering, and visualization**.

---

### **2. Wide Format**

- Each **row represents a unique entity** with **multiple attributes as columns**.
- Often used in **spreadsheets, pivot tables, and machine learning models**.

**Example (Sales Data in Wide Format):**

|Date|Sales_A|Sales_B|
|---|---|---|
|2024-03-01|100|150|
|2024-03-02|120|180|

📌 **Use case:** Used in **statistical analysis, machine learning models, and fast lookups**.

---

### **Key Differences:**

|Aspect|Long Format|Wide Format|
|---|---|---|
|**Structure**|Rows = Observations|Rows = Entities|
|**Columns**|Variables & values|Separate columns for each category|
|**Best for**|Grouping, visualization|Fast lookups, ML models|
|**Example Use**|Time-series data|ML features, pivot tables|

## References