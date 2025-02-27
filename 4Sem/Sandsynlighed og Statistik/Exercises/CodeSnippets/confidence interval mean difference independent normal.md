Independent random samples are taken from the output of two machines on a production line. The weight of each item is of interest. From the first machine, a sample of size 36 is taken, with sample mean weight of 120 grams and a sample variance of 4. From the second machine, a sample of size 64 is taken, with a sample mean weight of 130 grams and a sample variance of 5.
1. It is assumed that the weights of items from the first machine are normally distributed with mean µ1 and variance σ^2 and that the weights of items from the second machine are normally distributed with mean µ2 and variance σ2 (that is, the variances are assumed to be equal and unknown). Find a 99 percent confidence interval for µ1 − µ2 , the difference in population means.
2. Now, assume that we know in advance the true population variances, which are 4 and 5 respectively. Redo the calculations.

Hint: Remember the distinction between population mean/variance and sample mean/variance. Also, pay attention to the difference in terms of assumptions between subproblems 1) and 2) - how does it impact the choice of distribution you will need to work with?.

```python
import numpy as np
from scipy.stats import t
import math

#choose one of the three confidence levels known as alpha
#standards being 0.1, 0.05, 0.01
confidence_level = 0.01

# Calculate the sample means and variances
mean1 = 130
mean2 = 120
var1 = 5
var2 = 4

# Calculate the pooled sample variance
n1 = 36
n2 = 64
sp = ((n1-1)*var1 + (n2-1)*var2) / (n1+n2-2)

# Calculate the standard error of the difference in means
#also known as sigma
sigma = np.sqrt(sp/n1 + sp/n2)

# Calculate the t-value for a 95% confidence interval with 24 degrees of freedom
t_score = t.ppf(1-(confidence_level/2), n1+n2-2)

# Calculate the confidence interval
lower = (mean1 - mean2) - t_score * sigma
upper = (mean1 - mean2) + t_score * sigma

print(f"95% Confidence Interval for the Difference in Means: ({lower:}, {upper:})")
```