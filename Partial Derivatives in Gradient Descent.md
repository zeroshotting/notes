---
created: 2025-03-16
confidence level: low
review count: 0
---
## Explanation
---
Let's say we have a feature vector $\mathbf x$ with 2 features and target array $y$, with the training set consisting of $m$ examples. Modelling this linear regression we have:

$$ \hat y^{(i)} = w_1 \cdot x_1^{(i)} + w_2 \cdot x_2^{(i)} $$
$$ J(w_1, w_2) = \frac{1}{2m}\sum_{i=1}^{m}(\hat y^{(i)} - y^{(i)})^2 $$

For the sake of this explanation the bias has been done away with, or could even itself be included in the weight vector.  Our cost function $J$ is defined as:

Now if we plot $w_1$ vs $w_2$ vs  $J$, the cost surface takes the shape of a paraboloid. Representing the $w_1$ vs $w_2$ plane as a gradient vector field, we can observe the gradient vector of $J$ at any singular point - a vector that points in the direction of steepest ascent for the cost function $J$ at that point with respect to $w_1$ and $w_2$. In other words, if we select a vector in the field, it tells us what direction on both axes increases the cost function the fastest.

This vector is computed as:

$$ \nabla J = [\frac{\partial J}{\partial w_1}, \frac{\partial J}{\partial w_2}] $$

The partial derivatives of the cost function with respect to $w_1$ and $w_2$ respectively, are the components of the gradient vector. These individual partial derivatives can be understood to be directional derivatives along their respective axes. A directional derivative is the rate at which a function changes in a specific direction from a particular point. Directional derivatives are only partials when the direction aligns with the axes.

## Further  Reading
- [[Linear Regression]]
- [[Multiple Linear Regression]]
- [[Gradient Descent]]
- [[Feature Scaling]]