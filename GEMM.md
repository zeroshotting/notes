---
created: 2025-07-01
confidence level: low
review count: 0
---
# Intro
---
GEMM stands for General Matrix-Matrix Multiplication. It can be formally expressed as:

$$ C \rightarrow \alpha AB + \beta C $$
Where:
- $A$ is an $m \times k$ matrix
- $B$ is a $k \times n$ matrix
- $C$ is an $m \times n$ matrix
- $\alpha, \beta \in \mathbb R \; or \; \mathbb C$

This is a core operation in dense linear algebra libraries (e.g. BLAS, cuBLAS, LAPACK) and underlies most high-performance computing tasks. All dense linear algebra reduces to GEMM at some level.

# Further Explanation
---
Let:
$$ A = [a_{ij}],\; B = [b_{jk}],\; C = [c_{ik}] $$
Then:
$$ c_{ij} \rightarrow \alpha \sum_{l=1}^k a_{il}b_{lj} + \beta c_{ij} $$
This scales the matrix product $AB$ by $\alpha$ and adds the result to $C$, scaled by $\beta$. If $\alpha = 1,\; \beta = 0$ just compute $C = AB$ and if $\beta \neq 0$, we're accumulating into $C$.

# Further Reading
---
- [[Vectorized Dot Product in C]]
- [[ML Math Introduction]]
- [[NumPy]]
- [[Multiple Linear Regression]]