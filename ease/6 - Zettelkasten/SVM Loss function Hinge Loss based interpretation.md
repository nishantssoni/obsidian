2025-02-19 13:03

Status:

Tags: [[svm]]

---
Logistic Regression:Logistic loss + reg
Linear Regression:Linear loss + reg
SVM:Hinge loss + reg

Zi = yi f(xi) = yi (WTXi + b)
For 0-1 loss: if Zi > 0 is correctly classified; if Zi < 0 is incorrectly classified

Hinge Loss:

![[Pasted image 20250219130943.png]]
If Zi >= 1, hinge loss = 0;
If Zi <= 1, hinge loss = 1 - Zi;
Hinge loss = max (0, 1 - Zi)

Geometric formulation:
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
