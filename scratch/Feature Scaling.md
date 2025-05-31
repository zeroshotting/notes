This note is relevant to (multiple) linear regression.

Sometimes, having features that differ vastly in range can produce problems in the training process. For example, in a model that is to predict the price of houses based on the size of the house and number of bedrooms, if the size of the house ranged from 0 - 2000 feet and the number fo bedrooms ranged from 0 - 5 rooms, the parameters for both features would vary greatly. To ensure model accuracy, parameters would have to compensate for the size of the feature values. The parameter corresponding to the size of the house in feet would need to be relatively small compared to the parameter corresponding to the number of rooms in the house. We would have something like this:

$$ f_{w,b} = \mathbf w_1 \cdot \mathbf x_1 + \mathbf w_2 \cdot \mathbf x_2 + b$$
where $\mathbf x_1$ represents the size of the house, and $\mathbf w_2$ represents the number of rooms in the house. If a house of size 2000 feet and 5 bedrooms cost $500k, which of they following equations would model the data more accurately?
$$ f_{w,b} = 0.1 \mathbf x_1 + 50 \mathbf x_2 + 50$$
$$ f_{w,b} = 50 \mathbf x_1 + 0.1 \mathbf x_2 + b $$
The second would produce a value that is far too large, so the answer is the second. With this, we can deduce that changes in $\mathbf w_1$ would affect the output value far more than comparable changes in $\mathbf w_2$ because of the size of the values that are being multiplied.

If we tried to visualize $\mathbf w_1$, $\mathbf w_2$, and $J(w,b)$ using a contour plot, we'd notice quickly that the shape of the contours are skewed. They would appear elongated (due to difference in ranges). And if gradient descent is performed on the training data in such a state, it might end up bouncing back and forth for a long time before arriving at the global minimum. In such situations, it would help greatly to scale the features such that they become comparable in range.