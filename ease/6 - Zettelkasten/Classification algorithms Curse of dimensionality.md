2025-01-31 16:11

Status:

Tags:

# Classification algorithms Curse of dimensionality


## When \( d \) is high in machine learning:
- Let all features be binary; for \( d \)-number of features, we will have \( 2^d \) values.
- **As dimensionality increases, the number of data points required for the model to perform well increases exponentially or incrementally, because we need data points in every dimension, not just in a few columns.

## Hughes Phenomenon:
- For a fixed number of training samples (let’s say 10k points), the predictive power (or performance) reduces as the dimensionality increases.

## Distance Functions:
- Intuition of distances (especially Euclidean distance) becomes invalid in high dimensionality.
- Suppose a large number of uniform/random data points are selected in a high-dimensional space:

$$
  \frac{\text{dist}_{\max}(x_i) - \text{dist}_{\min}(x_i)}{\text{dist}_{\min}(x_i)} > 0
$$

  - If

$$    
    \lim_{\text{dim} \to \infty} \frac{\text{dist}_{\max}(x_i) - \text{dist}_{\min}(x_i)}{\text{dist}_{\min}(x_i)} \to 0
$$   
    then the equation tends to zero in Euclidean distance, where ${dim}$ is dimensionality.
  - This means $\text{dist}_{\max}(x_i) \approx \text{dist}_{\min}(x_i)$.
  - So, any two points $x_i$ and $x_j$ in a high dimension have almost the same distance, and distances become uniformly distributed.
  - \( k \)-NN primarily uses Euclidean distance, so in high dimensions, \( k \)-NN does not perform well.
  - Cosine similarity can be considered instead of Euclidean distance; though cosine similarity is also affected by the curse of dimensionality, the impact is less compared to Euclidean distances.
  - The minimum distance between every pair of points is roughly similar to the maximum distance, making the comparison of Euclidean distances for data point similarity impossible as dimensionality increases.
  - ==If the data is high-dimensional and dense, the impact of the curse of dimensionality is more significant compared to high-dimensional sparse data (because in sparse data, most values are zero, making dimensions non-uniform and randomly spread).==

## Overfitting and Underfitting:
- As dimensionality increases, the chances of overfitting increase.
- We can mitigate this with forward feature selection.
- We can also use **PCA** or **t-SNE**, which are not classification-oriented but help preserve proximity and variance.

## \( k \)-NN on Text Data or High-Dimensional Data:
- Cosine similarity and sparse representations (like **BoW**) are less impacted by the curse of dimensionality.

## Additional Considerations:
- Consider the length of the diagonal for a unit hypercube:
  - In **2D**: $L_{\text{dia}} = \sqrt{2}$
  - In **3D**: $L_{\text{dia}} = \sqrt{3}$
  - In **10,000D**: $L_{\text{dia}} = \sqrt{10,000} = 100$
  - Even though data points lie in the same unit hypercube, they are very far apart.
  - The average distance of random data points in an \( n \)-dimensional hypercube is given by:

    $$\sqrt{\frac{10^{n}}{n}}$$


    - **For 2D**: $text_{avg dist} = \sqrt{\frac{100}{2}} = 7.07$
    - **For 3D**: $text_{avg dist} = 18.25$
    - **For 6D**: $text_{avg dist} = 408.24$

  - This shows that the average distance in a **6D dataset** is already very large.
  - ==Real-world problems often have dimensions in the **hundreds or thousands**, making distance-based similarity measures even worse.==


# References