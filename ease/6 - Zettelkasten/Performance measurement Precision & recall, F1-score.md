2025-02-02 21:17

Status:

Tags:

# Performance measurement Precision & recall, F1-score


These metrics are often used in **information retrieval problems** to evaluate model performance.

---

####  ✅ Precision
- **Formula:**  
  $$
  \text{Precision} = \frac{TP}{TP + FP}
  $$
- **Meaning:** Of all the predicted positives, how many are actually positive.
- **Range:** [0, 1]

---

#### 🔍 Recall
- **Formula:**  
$$  
  \text{Recall} = \frac{TP}{TP + FN}
 $$
- **Meaning:** Of all actual positives, how many were correctly predicted as positive.
- **Range:** [0, 1]
- **Note:** Recall is the same as the **True Positive Rate (TPR)**.

---

#### 🎯 F1-Score
- **Definition:** Combines both precision and recall into a single metric.
- **Formula:**  
 $$ 
  F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
$$
  *(Harmonic mean of precision and recall)*  
- **Key Points:**  
  - High precision and recall result in a high F1 score.
  - Range of F1 score: [0, 1]

---

**TP** = True Positives, **FP** = False Positives, **FN** = False Negatives


# References