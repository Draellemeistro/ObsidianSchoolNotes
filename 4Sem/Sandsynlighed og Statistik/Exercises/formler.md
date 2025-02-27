### Sample mean
$$\bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i$$

### Sample variance
$$s^2 = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2$$

### Law of large numbers
(X can also be referred to as the sample mean of a given set of numbers)
$$[ \bar{X}_{n} = \frac{1}{n} \sum_{i=1}^{n} X_i ]$$
where
- $\bar{X}$ rerpesents sample mean
- $n$ number of observations in the sample
- $X_i$ represents each individual observation in the sample
```python
# Sample observations of X and Y
x_values = [1, 2, 3, 4, 5]
Y_values = [6, 7, 8, 9, 10]

# Number of observations in the sample
n = len(x_values)
sample_mean = 0

# Calculate the sample mean
for xi, yi in zip(x_values, Y_values):
    sample_mean += xi + yi

sample_mean = sample_mean/n

# Print the sample mean
print("Sample Mean:", sample_mean)
```
## Gaussian distribution (normal distribution)
(Also called normal distribution)
The Gaussian distribution Also called normal distribution
The probability density function (PDF) of the Gaussian distribution is defined as:
$$f(x) = \frac{1}{σ\sqrt{2π}} {e}^\frac{-{(x - μ)}^{2}}{(2σ^2)}$$
![[Pasted image 20240604021936.png]]
Where:

- $μ$ (**mu**) represents the mean, located at the center of the distribution.
- $σ$ (**sigma**) represents the variance, which tells us how wide the distribution is.
- The compact representation of a random variable X following a Gaussian distribution is $X\sim N(μ,\sigma^2)$

### Standard normal distribution
$$\phi(x) = \frac{1}{\sqrt{2\pi}} \cdot e^{-\frac{x^2}{2}}$$
![[Pasted image 20240604022114.png]]
Mean: $𝜇$ - This is the average Standard Deviation: $\sigma$

### PDF - Product mass function of normal distribution based on mean and standard deviation
```python
import scipy as scp
import numpy as np
import matplotlib.pyplot as plt

# This is the mean and standard deviation of the first random variable
X1 = scp.stats.norm(0, 10)  # Create object of a 'frozen' normal RV with mean = 0 and std = 1

print(dir(X1))

# This defines the picture scaling of the graph
x = np.linspace(-20, 40, 1000)
pdf = X1.pdf(x)

print("The first graph is the normal distribution of one random variables")
# This plots the first random variable x1 as a normal distribution based on X1´s values
plt.figure()
plt.plot(x,pdf)
plt.show()
plt.clf()

# This is the mean and standard deviation of the second random variable
X2 = scp.stats.norm(2,0.5) # Create a second object of a normal RV with mean = 1 and std = 0.5
a = 1
b = 5

# This is the combination of the two defined random variables x1 and x2 which is plotted below
W = scp.stats.norm(a*X1.mean()+b*X2.mean(),a*X1.std()+b*X2.std())

print("The second graph is the normal distribution of the two random variables combined")
pdfW = W.pdf(x)
plt.figure()
plt.plot(x,pdfW)
plt.show()
```


# multiple RVs
## The linearity of expectation and sample mean
#### Expectation formula:
$$E(X+Y)=E[X]+E[Y]$$
$$E[aX+Y]=aE[X]+b$$
## The formula for the sample mean:
$$[ \bar{Z} = \frac{1}{n} \sum_{i=1}^{n} (X_i + Y_i)]$$
WHERE
- $\bar{Z}$ represents the sample mean of the combined random variables $(Z_i=X_i+Y_i)$
- $n$ is number of observations in the sample
- $X_i$ represents each individual observation of the random variable $X$ in the sample
- $Y_I$ represents each individual observation of the random variable $Y$ in sample