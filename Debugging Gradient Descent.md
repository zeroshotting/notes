---
created: 2025-06-15
confidence level: low
review count: 0
---
# Intro
---
When running gradient descent it is important to try to figure out:
1. If gradient descent is converging
2. At what point gradient descent converges
3. The right learning rate $(\alpha)$ to apply

# Explanation
---
The solution for the first is somewhat intuitive. We can plot the cost function $(J)$ against the number of iterations of gradient descent that have been performed and observe the resulting curve (learning curve). If $J$ reduces as the number of iterations increases, then we can conclude that gradient descent is converging. If we notice $J$ rise it could either mean $\alpha$ was selected poorly (most likely too large), or there is a bug in the code.

To ascertain the point at which gradient descent converges, we can observe the plot $J \; vs \; number \; of \; iterations$. At some point the learning curve will flatten out and at that point we can safely assume convergence. Another method we can apply is called an _Automatic Convergence Test_. In this test, we select a very small number $\varepsilon$ (let's say $10^{-3}$) and if the cost $J$ decreases by less than this number after an iteration of gradient descent, then we can declare convergence. Although, picky a good threshold for $\varepsilon$ is not exactly straightforward.

# Further  Reading
---
- [[Gradient Descent]]
- [[Linear Regression]]
- [[Multiple Linear Regression]]