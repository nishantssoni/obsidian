2025-02-18 13:19

Status:

Tags:

---

### **Why L1 Regularization Creates Sparsity?**

- **L1 Regularization** induces **sparsity** into the weight vector.
- **Sparsity** means most elements of the weight vector are zero.

---

### **Difference Between L1 and L2 Regularization:**

In the optimization formulation, **loss and $\lambda$** can be ignored for comparison since they are the same for both **L1 and L2 regularizations**.

- **L2 Regularization:**  
    Objective Function:
    $$
\min_{W} (W_1^2 + W_2^2 + \cdots + W_d^2)
$$
    Shape: A **parabola**.
    
- **L1 Regularization:**  
    Objective Function:
    
   $$
 \min_{W} (|W_1| + |W_2| + \cdots + |W_d|)
$$
    Shape: A **V-shaped curve**.
    
---

###  **Derivatives Comparison:**

#### **1. L2 Regularization Derivative:**

- $L_2(W_1) = W_1^2$
- $\frac{dL_2}{dW_1} = 2W_1$ (Derivative is a straight line)

#### **2. L1 Regularization Derivative:**

- $L_1(W_1) = |W_1|$
- $\frac{dL_1}{dW_1} = \begin{cases} +1, & \text{if } W_1 > 0; \ -1, & \text{if } W_1 < 0 \end{cases}$ (Derivative is a step function)

---

###  **Weight Update Formula:**

The general weight update rule for both L1 and L2 is:
$$
W_{1}^{j+1} = W_{1}^{j} - \eta \left( \frac{dL}{dW_1} \right)_{W_1^j}
$$


- Let’s consider **$W_1$ is positive** (a similar logic applies for negative $W_1$).

### 🔹 **L2 Regularization Update:**
$$
W_{1}^{j+1} = W_{1}^{j} - \eta (2W_{1}^{j})
$$


### 🔹 **L1 Regularization Update:**
$$
W_{1}^{j+1} = W_{1}^{j} - \eta (1)
$$

---

### **Why L1 Creates Sparsity:**

1. **L2 Updates Slow Down Near Optimum:**  
    In **L2 regularization**, the derivative depends on the weight value ($2W_1$).  
    As $W_1$ gets smaller, the update step gets smaller:
    
   $$\text{Update} \propto 2W_1$$
    
    This means **L2 updates shrink gradually** but rarely hit exactly zero.
    
2. **L1 Updates Remain Constant:**  
    In **L1 regularization**, the derivative is constant ($\pm 1$).  
    Even when $W_1$ is small, the update remains the same:
    
    $$Update=η$$
    
    This **pushes weights directly to zero**, creating **sparsity**.

==The chance that (w1 =0) are more at the end of kth iteration in L1 regularization than L2 regularization==
# References
[[Logistic Regression L1 regularization and sparsity]]
[[Logistic Regression L2 Regularization Overfitting and Underfitting]]
