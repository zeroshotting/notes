This note is relevant to [[Multiple Linear Regression|(multiple) linear regression]].

Sometimes, having features that differ vastly in range can produce problems during training. For example, in a model that predicts house price based on the size of the house and number of bedrooms:

$$ f_{w,b} = \mathbf w_1 \cdot \mathbf x_1 + \mathbf w_2 \cdot \mathbf x_2 + b $$

where $\mathbf x_1$ is the house size (in square feet) and $\mathbf x_2$ is the number of bedrooms.

If the house size ranges from 300–2000 feet and bedroom count from 0–5, then the input features differ significantly in scale. To keep predictions accurate, the model must compensate by adjusting the parameter magnitudes accordingly. For instance, given a house of 2000 ft^2 and 5 bedrooms priced at $500k:

- Equation 1: 

$$ f=0.1⋅2000+50⋅5+50=500 $$
$$ f = 0.1 \cdot 2000 + 50 \cdot 5 + 50 = 500 $$

- Equation 2: 

$$ f=50⋅2000+0.1⋅5+b $$
$$ f = 50 \cdot 2000 + 0.1 \cdot 5 + b $$

results in an unrealistically large value

So the first equation more accurately models the data. This shows how large-magnitude inputs lead to smaller weight values to prevent them from dominating the output.

If we plot the cost function $J(w,b)$ over $\mathbf w_1$ and $\mathbf w_2$, we observe skewed, elongated contours due to the disproportionate feature ranges. Gradient descent on such a landscape will zigzag inefficiently, delaying convergence.

In such situations, it helps greatly to scale the features so they become comparable in range. So how do we go about achieving this? There are two ways:

- Method 1: Basic min-max scaling
$$ x_{n,scaled} = \frac{x_n}{x_{max}} $$
- Method 2: Mean normalization
$$ x_{j,scaled} = \frac{x_j - \mu}{x_{max} - x_{min}} $$