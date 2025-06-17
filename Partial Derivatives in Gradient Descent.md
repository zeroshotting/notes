---
created: 2025-03-16
confidence level: low
review count: 0
---
## Explanation

Let's say we have a feature vector $\mathbf x$ with 2 features and target array $y$, with the training set consisting of $n$ examples. Modelling this linear regression we have:

$$ \hat y = \mathbf w_1 \cdot \mathbf x_1 + \mathbf w_2 \cdot \mathbf x_2 $$
$$ J(\mathbf w_1, \mathbf w_2) = \frac{1}{2m}\sum_{i=0}^{n}(\hat y - y)^2 $$

For the sake of this explanation the bias has been done away with, or could even itself be included in the weight vector.  Our cost function $J$ is defined as:

Now if we plot $\mathbf w_1$ vs $\mathbf w_2$ vs  $J$, the cost surface takes the shape of a paraboloid. Representing the $\mathbf w_1$ vs $\mathbf w_2$ plane as a vector field, we can observe the gradient vector of $J$ at any singular point - a vector that points in the direction of steepest ascent for the cost function $J$ at that point with respect to $\mathbf w_1$ and $\mathbf w_2$. In other words, if we select a vector in the field, it tells us what direction on the both axes increases the cost function the fastest.

How is this vector computed? Simply,

$$ \nabla J = [\frac{\partial J}{\partial \mathbf w_1}, \frac{\partial J}{\partial \mathbf w_2}] $$

The partial derivatives of the cost function with respect to $\mathbf w_1$ and $\mathbf w_2$ respectively, are the components of the gradient vector. These individual partial derivatives can be understood to be directional derivatives along the their respective axes. A directional derivative is the rate at which a function changes in a specific direction from a particular point.

## Further  Reading
- [[Linear Regression]]
- [[Multiple Linear Regression]]
- [[Gradient Descent]]
- [[Feature Scaling]]