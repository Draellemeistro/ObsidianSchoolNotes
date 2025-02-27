```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import binom

# Parameters for mean and variance
mean = 22
variance = 17.16

# Calculate the number of trials and probability of success
n = mean**2 / (mean - variance)
p = 1 - variance / mean

# Create an array of x values
x = np.arange(0, int(n)+1)

# Calculate the CDF for each x value
cdf = binom.cdf(x, n, p)

# Find P(X ≥ 15)
p_greater_than_or_equal_to_15 = 1 - binom.cdf(14, n, p)

# Plot the CDF
plt.plot(x, cdf, marker='o', linestyle='-', label='Binomial CDF')

# Add labels and title to the plot
plt.xlabel('Number of Successes')
plt.ylabel('Cumulative Probability')
plt.title('CDF of Binomial Distribution (mean={}, variance={})'.format(mean, variance))

# Display the plot
plt.legend()
plt.grid(True)
plt.show()

print("P(X ≥ 15) =", p_greater_than_or_equal_to_15)
# P(X ≥ 15) = 0.969547088727553
```
![[Pasted image 20240604014852.png]]