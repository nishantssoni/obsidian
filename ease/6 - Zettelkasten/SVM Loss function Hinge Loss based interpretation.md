2025-02-19 13:03

Status:

Tags: [[svm]] [[ml_loss]]

---

- `Logistic Regression: Logistic loss + reg`
- `Linear Regression: Linear loss + reg`
- `SVM: Hinge loss + reg`
![[loss_functions.png]]
here,
$$
\text{x-axis}=Z_{i} = y_{i}.f(x_{i}) = y_{i}(w^{T}x_{i} + b)
$$

For 0-1 loss:
- if $Z_{i}$ > 0 is correctly classified
- if $Z_{i}$ < 0 is incorrectly classified

but, for Hinge Loss:
- If $Z_{i}$ >= 1, hinge loss = 0.
- If $Z_{i}$ <= 1, hinge loss = 1 - $Z_{i}$.
- **Hinge loss = max (0, 1 - $Z_{i}$)**

![[Pasted image 20250219130943.png]]
- Hinge loss is not differentiable at point x = 1

#### Geometric formulation:

ξi = 0 for correctly classified data points
For incorrectly classified data points:
![[Pasted image 20250219131045.png]]
ξi = dist for xj to the correct hyper plane = max(0,1- Zj)
Soft-SVM: min(W,b) ||W||/2 + C sum(ξi) such that ( 1- yi (WTXi + b)) <= ξi
C increases - Overfitting
Loss-minimization: min (W,b) sum(max(0, 1-yi(WTXi + b)) + λ||W||2
λ increases – Underfitting
(C when multiplied with loss function and λ for regularizing term)


# References
[[Logistic Regression Loss minimization interpretation]]
[[SVM Mathematical derivation]]
[[Performance measurement Log-loss]]