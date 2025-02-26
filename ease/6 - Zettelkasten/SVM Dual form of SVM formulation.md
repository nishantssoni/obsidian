2025-02-22 08:59

Status:

Tags:

---
## SVM Dual form of SVM formulation


**Primal Form(or soft margin SVM)**
$$
(w^{*},b^{*}) = argmin_{w,b} \ \frac{||w||}{2} + c*\sum_{i=1}^{n} \xi_{i}
$$
 contraints :
$$
1-y_{i} (w^{T}x + b) \geq \xi_{i} \ ; \ \forall \ \xi_{i} \geq_{0}
$$

but it can be written as a second form which is ==equivalent and often refres as **dual form**.==
$$
max_{\alpha_{i}} = \sum_{i=1}^{n}\alpha_{i} - \frac{1}{2}\sum_{i=1}^{n}\sum_{j=1}^{n}\alpha_{i}\alpha_{j}y_{i}y_{j}x_{i}^{T}x_{j}
$$
such that
$$
C \geq \alpha_{i} \geq 0 \text{ and } \sum_{i=1}^{n}\alpha_{i}y_{i} = 0
$$

**observation**:
- for every $x_{i}$ there is corrosponding $\alpha_{i}$

### Links
[Andrew ng svm notes](https://web.archive.org/web/20190108042134/https://cs229.stanford.edu/notes/cs229-notes3.pdf)
[[SVM Loss function Hinge Loss based interpretation]]
# References