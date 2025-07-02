---
created: 2025-04-14
confidence level: medium
review count: 1
---
# Intro
---
With regular linear regression there is a single input, $x$ used to predict a single output, $y$. With _multiple linear regression_, multiple inputs, $\mathbf x$ are used to predict $y$. Here are some additional notations:
+ $x_j$: $j^{th}$ feature
+ $n$: number of features
+ $\mathbf x^{(i)}$: features of $i^{th}$ training example
+ $x_j^{(i)}$: value of feature $j$ in $i^{th}$ training example

Example model definition for multiple linear regression:

$$f_{\mathbf w,b}(x) = w_1 \cdot x_1 + w_2 \cdot x_2 + \cdots + w_n \cdot x_n + b$$
$$or$$
$$f_{\mathbf w,b}(\mathbf x)=\mathbf w \cdot \mathbf x + b$$
# Vectorization
---
Writing vectorized code allows you to take advantage of modern hardware to perform operations in parallel. It makes use of SIMD (Simple Instruction Multiple Data) which is a parallel processing technique that allows you to perform a single instruction on multiple data points simultaneously. Vectorized code is faster and more efficient.

# Cost
---
The cost function remains the same as in univariate linear regression.

# Gradient Descent
---
The calculations involved in gradient descent change slightly:
$$ w_j = w_j - \alpha\cdot\frac{\partial}{\partial{w_j}}J(\mathbf w,b) \; for \; j = 0,1,...,n $$
$$ b = b - \alpha\cdot\frac{\partial}{\partial b}J(\mathbf w,b) $$
$\mathbf w$ is a vector here rather than a scalar as in univariate regression.

Quick Note: The bias does not need to be calculated separately from the weights. Using something called the _bias trick_ or _bias augmentation_, we can add the bias to the weight vector and the model will behave the same.

Given:
$$ \hat y = \mathbf w \cdot \mathbf x + b \; with \; \mathbf w \in \mathbb R^N,\; \mathbf x \in \mathbb R^N,\; b \in \mathbb R $$

Define $\mathbf x' = [x_1, x_2,..., x_N, 1] \in \mathbb R^{N+1}$
Define $\mathbf x' = [w_1, w_2,...,w_N,b] \in \mathbb R^{N+1}$

Then the model prediction becomes:
$$ \hat y = \mathbf w \cdot \mathbf x + b = \mathbf w' \cdot \mathbf x' $$
And the gradient descent update step becomes:
$$ w_j' \rightarrow w_j' - \alpha \cdot \frac{\partial J}{\partial w_j} $$

## Further Reading
- [[Linear Regression]]
- [[Vectorized Dot Product in C]]
- [[Feature Scaling]]
- [[Gradient Descent]]
- [[Debugging Gradient Descent]]
- [[Partial Derivatives in Gradient Descent]]
- [[ML Math Introduction]]
- [[NumPy]]
- [[GEMM]]