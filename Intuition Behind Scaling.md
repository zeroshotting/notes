---
created: 2025-07-04
confidence level: low
review count: 0
---
# Intro
---
This note is relevant to [[Feature Scaling]].

After studying the need for feature scaling, I had a question. How is it that these operations allow us to scale the features so well. Why do these specific operations produce this specific output. What is the intution behind the processes? Take _min-max scaling_ for example:
$$ x_{j,scaled} = \frac{x_j - x_{min}}{x_{max} - x_{min}} $$
Why are we subtracting $x_{min}$ from $x_j$? Why are we dividing the result by $x_{max} - x_{min}$? What does this achieve?

# More Context
---
I realized that when you have a list of numbers, dividing by a certain constant also divides the range of that list of numbers by that constant. Let's take the following list:
$$ [10, 20, 30, 40, 50] $$
If we divide each number by 10:
$$ [1, 2, 3, 4, 5] $$
We can see that the range of the initial list, $50 - 10 = 40$ was reduced to $5 - 1 = 4$ which is the same $40 \div 10 = 4$. We can also see that the new values represent how many 'tens' each point is. Generally this would mean that dividing by $x$ tells us how many units of $x$ each point is. Multiplying/dividing either spreads out the numbers or makes them more tightly packed. What about adding/subtracting? If we look at the original list, performing and addition or subtraction has a very obvious effect:

**It shifts the list of numbers left or right (relative to the number line).**

Adding 10 to the number line produces $[20, 30, 40, 50, 60]$. The range and spread remains the same but the maximum and minimum values have increased. The same concept applies if we subtract 10 from each element except the maximum and minimum values will reduce this time.

Combining these two ideas we can move items left or right to center them around certain values and then either spread them out more or make them more tightly packed. With min-max scaling, we're doing both. Let's take a look using our sample list:

$$ x = [10, 20, 30, 40, 50];\; x_{max} = 50,\; x_{min} = 10,\; x_{max} - x_{min} = 40$$
$$ x_{scaled} = [0, 0.25, 0.5, 0.75, 1]$$
By subtracting $x_{min}$ from each value in the list, we shifted the list to start from 0. Then by dividing by $x_{max} - x_{min}$, we scaled down the numbers so the range becomes 1. This effectively causes the list to range from 0 - 1.

With other scaling techniques line _mean normalization_ and _Z-score normalization_, we do things like subtracting the mean of the values ($\mu$) so that the values are centered around $\mu$ (thus causing $\mu_{new} = 0$ ), and dividing the values by the standard deviation ($\sigma$) so that each value now represents how many standard deviations away from the mean that point is.

# Further  Reading
---
- [[Feature Scaling]]
- [[Relationship between Mean, Variance and SD]]