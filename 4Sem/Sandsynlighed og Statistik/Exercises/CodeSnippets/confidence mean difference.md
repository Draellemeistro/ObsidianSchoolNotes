A psychologist was interested in exploring whether or not male and female college students have different driving behaviors. There were several ways that she could quantify driving behaviors. She opted to focus on the fastest speed ever driven by an individual. Therefore, the particular statistical question she framed was as follows: “Is the mean fastest speed driven by male college students different than the mean fastest speed driven by female college students?”  
She conducted a survey of a random male college students and a random female college students. Here is a descriptive summary of the results of her survey:  
Males Females  
sample size 34 29  
sample mean 105.5 90.9  
sample std. 20.1 12.2  
Is there sufficient evidence at the α = 0.05 level to conclude that the mean fastest speed driven by male college students differs from the mean fastest speed driven by female college students?
```python
import numpy as np
from scipy.stats import t
import math

#choose one of the three confidence levels known as alpha
#standards being 0.1, 0.05, 0.01
confidence_level = 0.05

# Calculate the sample means and variances
mean1 = 105.5
mean2 = 90.9
var1 = math.pow(20.1, 2)
var2 = math.pow(12.2, 2)

# Calculate the pooled sample variance
n1 = 34
n2 = 29
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
# 95% Confidence Interval for the Difference in Means: (6.038845924801011, 23.16115407519898)
```