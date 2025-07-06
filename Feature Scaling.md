---
created: 2025-06-15
confidence level: low
review count: 0
---
# Intro
---
This note is relevant to [[Multiple Linear Regression|(multiple) linear regression]].

Sometimes, having features that differ vastly in range can produce problems during training. For example, in a model that predicts house price based on the size of the house and number of bedrooms:

$$ f_{w,b} = w_1 \cdot x_1 + w_2 \cdot x_2 + b $$

where $x_1$ is the house size (in square feet) and $x_2$ is the number of bedrooms.

If the house size ranges from 300–2000 feet and bedroom count from 1–5, then the input features differ significantly in scale. To keep predictions accurate, the model must compensate by adjusting the parameter magnitudes accordingly. For instance, given a house of 2000 ft^2 and 5 bedrooms priced at $500k:

- Equation 1: 

$$ f=0.1⋅2000+50⋅5+50=500 $$
$$ f = 0.1 \cdot 2000 + 50 \cdot 5 + 50 = 500 $$

- Equation 2: 

$$ f=50⋅2000+0.1⋅5+b $$
$$ f = 50 \cdot 2000 + 0.1 \cdot 5 + b $$

results in an unrealistically large value

So the first equation more accurately models the data. This shows how large-magnitude inputs lead to smaller weight values to prevent them from dominating the output.

# Further Explanation
---
Let's take a deeper look at what is going on here. If we plot plot the loss function $J(w,b)$ over $w_1$ and $w_2$, we observe that the resulting paraboloid looks a bit _squeezed_. This is because the loss function is more sensitive to $w_1$ and far less sensitive to $w_2$. Since the loss is much more sensitive to $w_1$​, small changes in $w_1$​ lead to large changes in $J$, while $w_2$ needs to change significantly to have a comparable effect. To better visualize this, we can take the cross-section of the paraboloid at constant $w_2$ and observe the resulting parabola which shows us how changes in $w_1$ affect $J$, then vice-versa to observe $w_2$. The parabola for $w_1$ would be very steep and that of $w_2$ would be flatter, so the gradient tends to be large in the $w_1$ direction but small in the $w_2$ direction. The gradient at any point on the actual paraboloid is the vector $(\frac{\partial J}{\partial w_1}, \frac{\partial J}{\partial w_2})$ where each component tells us how fast $J$ rises in the direction of a particular parameter.

If we plot the loss function $J(w,b)$ over $w_1$ and $w_2$, we observe skewed, elongated contours due to the disproportionate feature ranges. Gradient descent on such a landscape will zigzag inefficiently, delaying convergence.

It's also worth noting that when calculating the partial derivative of the parameters for gradient descent,

$$ \frac{\partial}{\partial w_j}J(\mathbf w, b) = \frac{1}{m} \sum_{i=1}{m}(f_{\mathbf w, b}(x^{(i)}) - y^{(i)})x_j^{(i)} $$
the weights all have the error in common but the feature that multiplies the error is different for different weights. Having features that have different ranges would lead to uneven updates for the weights.

In such situations, it helps greatly to scale the features so they become comparable in range. So how do we go about achieving this? There are two ways:

- Method 1: Basic min-max scaling.
$$ x_{j,scaled} = \frac{x_j - x_{min}}{x_{max} - x_{min}} \; s.t. \; 0 < x_{j,scaled} < 1 $$
- Method 2: Mean normalization
$$ x_{j,scaled} = \frac{x_j - \mu}{x_{max} - x_{min}} \; typically \; in \; (-1, 1) \; but \; not \; strictly \; bounded $$
- Method 3: Z-Score normalization

$$ x_{j,scaled} = \frac{x_j - \mu}{\sigma} $$

# Further Reading
- [[Linear Regression]]
- [[Multiple Linear Regression]]
- [[Gradient Descent]]
- [[Debugging Gradient Descent]]
- [[Partial Derivatives in Gradient Descent]]
- [[Intuition Behind Scaling]]