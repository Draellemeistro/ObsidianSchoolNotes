The average adult male height in a certain country is 170 cm. However, we suspect that the men in a certain city in that country might have a different average height due to some environmental factors. We pick a random sample of size 9 from the adult males in the city and obtain the following values for their heights (in cm):
$$176.2, 157.9, 160.1, 180.9, 165.1, 167.2, 162.9, 155.7, 166.2$$
Assume that the height distribution in this population is normally distributed.  
Design a test (formulate hypothesis), and decide based on the observed data whether your suspicion is correct. Use significance level α = 0.05

```python
import numpy as np
import math
from scipy.stats import norm

#inset the observations in a array
sample = [176.2, 157.9, 160.1, 180.9, 165.1, 167.2, 162.9, 155.7, 166.2]

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
sigma = np.std(sample)

#based on the array we calculate the sample size
n = len(sample)

#Then to Confidence interval is being calculated
CIlower = (sample_mean - z_score * sigma / math.sqrt(n))
CIupper = (sample_mean + z_score * sigma / math.sqrt(n))

print(f"The {conf_lvl_pro}% confidence interval is {CIlower}, {CIupper}.")
# The 95.0% confidence interval is 160.7202195241127, 170.87978047588732.
```