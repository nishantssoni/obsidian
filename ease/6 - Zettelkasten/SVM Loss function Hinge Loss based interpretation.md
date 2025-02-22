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
- in the above picture a correctly classified point $x_{i}$ and a incorrectly classify point $x_{j}$ with the wrong distance of $d_{j}=1-y_{i}(w^{T}x_{i} + b)$
- $\xi = \text{dist of the point to the correct hyper plane }= max(0,1-Z_{i})$
- $\xi_{x_{i}} = 0$
- $\xi_{x_{j}} = 1-Z_{j}$

**Now the soft SVM is**
$$
(w^{*},b^{*}) = argmin_{w,b}\left( \frac{||w||}{2} + c*\frac{1}{n}\sum_{i=1}^{n} \xi_{i} \right)
$$
 contraints :
$$
1-y_{i} (w^{T}x + b) \geq \xi_{i} \ ; \ \forall \ \xi_{i} \geq_{0}
$$


**Loss-minimization:**
$$
min_{w,b} = \sum_{i=1}^{n} max(0,1-y_{i}(w^{T}\xi+b)) + \lambda||w||^{2}
$$

> [!important] 
> Now see both equation is kind a similer
> c increases - overfitting, $\lambda$ increases - underfit
> c decreases - underfit, $\lambda$ decreases - 0verfit
> both  are inverted of each other
> 

> [!info] 
>  C multiplied with loss function and λ multiplied for regularizing term
>  so loss minimizatio of svm and soft svm are kind a similer


# References
[[Logistic Regression Loss minimization interpretation]]
[[SVM Mathematical derivation]]
[[Performance measurement Log-loss]]