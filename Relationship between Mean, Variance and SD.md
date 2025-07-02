---
created: 2025-07-01
confidence level: low
review count: 0
---
# Intro
---
Given the vector $x_1, x_2, ..., x_m$:

$$ \mu = \frac{1}{m}\sum_{i=1}^{m}x_i $$
$$ \sigma = \sqrt{\frac{1}{m} \sum_{i=1}^{m}(x_i - \mu)^2} $$

This transformation produces a new set of values with $\mu = 0$, $\sigma = 0$, $\sigma^2 = 0$:
$$ z_i = \frac{x_i - \mu}{\sigma} $$
Subtracting the mean from each value shifts all the data so that the mean becomes zero, because:

- The mean $\mu$ is the point that minimizes total squared deviation from all values

- Each new value becomes $x_i - \mu$, i.e., the deviation from the mean

- The sum of these deviations is always zero:

$$ \sum_{m}^{i=1}(x_i - \mu) = \sum(x_i) - m\mu = m\mu - m\mu = 0 $$

This forces the new set of values to balance exactly around zero — the center of mass has moved to the origin. That's why it's called **centering**.

Dividing by the standard deviation scales the spread because it **normalizes the average squared distance from the mean to 1**.

---

### Recall what standard deviation is:

$$ \sigma = \sqrt{\frac{1}{m} \sum_{i=1}^m (x_i - \mu)^2} $$

It measures the **typical size** of deviations from the mean.
### Step-by-step intuition:
---

Let’s say your original data has large variation, so standard deviation $\sigma$ is large. Dividing each deviation $x_i - \mu$ by $\sigma$:

$$ z_i = \frac{x_i - \mu}{\sigma} $$

produces a new set of deviations scaled relative to the original spread. That is, each transformed value says:  

**“How many standard deviations away from the mean is this value?”**

### Resulting effect:
---
- If a value was 10 units above the mean in a dataset where $\sigma = 10$, after scaling it becomes $z = 1$

- If it was 10 units above the mean in a dataset where $\sigma = 1$, then $z = 10$

So dividing by $\sigma$ adjusts **how “big” a deviation counts** — it rescales the entire set so that the new deviations’ **root mean square** is 1, which by definition means standard deviation is 1.

### Mathematical confirmation:
---
After transformation:
$$ z_i = \frac{x_i - \mu}{\sigma} $$
then the mean of $z$ is 0, and the standard deviation becomes:

$$ \sqrt{\frac{1}{m} \sum_{i=1}^m z_i^2} = \sqrt{\frac{1}{m} \sum_{i=1}^m \left(\frac{x_i - \mu}{\sigma}\right)^2} = \sqrt{\frac{1}{\sigma^2} \cdot \frac{1}{m} \sum_{i=1}^m (x_i - \mu)^2} = 1 $$
---
Dividing by the standard deviation **rescales all deviations** so their average squared size becomes 1. This produces a standardized dataset where the unit of measurement is the original standard deviation, making spread uniform across features.

# Further  Reading
---