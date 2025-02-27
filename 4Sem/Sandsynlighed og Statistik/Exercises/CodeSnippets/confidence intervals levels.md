The Polychlorinated biphenyls (PCB) concentration of a fish caught in Lake Michigan was measured by a technique that is known to result in an error of measurement that is normally distributed with a standard deviation of 0.08 ppm (parts per million). Suppose the results of 10 independent measurements of this fish are:
$$
11.2, 12.4,10.8,11.6,12.5,10.1,11.0,12.2,12.4,10.6
$$
1. Give a 95 percent confidence interval for the PCB level of this fish.
2. Give a 95 percent lower confidence interval.
3. Give a 95 percent upper confidence interval

```python
import numpy as np
import math
from scipy.stats import norm

#inset the observations in a array
sample = [11.2, 12.4, 10.8, 11.6, 12.5, 10.1, 11.0, 12.2, 12.4, 10.6]

#Based on the array we calculate the mean
sample_mean = np.mean(sample)

#choose one of the three confidence levels
#standards being 0.1, 0.05, 0.01
confidence_level = 0.05
conf_lvl_pro = (1 - confidence_level)*100

#the z_score of the most common confidence levels is shown and used here
z_score = norm.ppf(1-confidence_level/2)

#sigma is the confidence interval
#offent shown as +-sigma
#also known as standard error
#this is the number being squred
sigma = 0.08

#based on the array we calculate the sample size
n = len(sample)

#Then to Confidence interval is being calculated
CIlower = (sample_mean - z_score * sigma / math.sqrt(n))
CIupper = (sample_mean + z_score * sigma / math.sqrt(n))

print(f"a) With {conf_lvl_pro}% confidence, the interval is between {CIlower}, {CIupper}.")

z_score = norm.ppf(1-confidence_level) # ikke dele alpha
#Then to Confidence interval is being calculated
CIlower = (sample_mean - z_score * sigma / math.sqrt(n))
CIupper = (sample_mean + z_score * sigma / math.sqrt(n))

print(f"b) With {conf_lvl_pro}% confidence, the interval is below {CIupper}.")

print(f"c) With {conf_lvl_pro}% confidence, the interval is above {CIlower}.")
# a) With 95.0% confidence, the interval is between 11.430416397415636, 11.529583602584365.
# b) With 95.0% confidence, the interval is below 11.521611871030045.
# c) With 95.0% confidence, the interval is above 11.438388128969956.
```

