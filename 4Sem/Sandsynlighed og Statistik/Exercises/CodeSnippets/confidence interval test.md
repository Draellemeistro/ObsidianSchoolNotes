 The manufacturer of a new fiberglass tire claims that its average life will be at least 40,000 miles.  
To verify this claim a sample of 12 tires is tested, with their lifetimes (in 1,000s of miles) being as follows:  
Tire 1 2 3 4 5 6 7 8 9 10 11 12  
Life 36.1 40.2 33.8 38.5 42 35.8 37 41 36.8 37.2 33 36  
Test the manufacturer’s claim at the 5 percent level of significance.
```python
import numpy as np
import math
from scipy.stats import t

#inset the observations in a array
sample = [36.1, 40.2, 33.8, 38.5, 42, 35.8, 37, 41, 36.8, 37.2, 33, 36]

#Based on the array we calculate the mean
sample_mean = np.mean(sample)

#Based on the array we calculate the standard deviation
sample_std = np.std(sample, ddof=1)

#based on the array we calculate the sample size
n = len(sample)

#insert the procent of confidence needed
#standards being 0.1, 0.05, 0.01
alpha = 0.05

#Based on the array and alpha the t score for two sided is calculated
t_score_two = abs(t.ppf(alpha/2, n-1))

#Based on the array and alpha the t score for one sided is calculated
t_score_one = abs(t.ppf(alpha, n-1))

#Then a lower Confidence interval is being calculated
CIlower = (sample_mean - t_score_one * sample_std / math.sqrt(n))
#Then a upper Confidence interval is being calculated
CIupper = (sample_mean + t_score_one * sample_std / math.sqrt(n))

#Then to Confidence interval is being calculated
CI = (sample_mean - t_score_two * sample_std / math.sqrt(n), sample_mean + t_score_two * sample_std / math.sqrt(n))

print(f"With {(1-alpha)*100}% confidence, the interval is below {CIupper}.")
print(f"With {(1-alpha)*100}% confidence, the interval is above {CIlower}.")
print(f"With {(1-alpha)*100}% confidence, the interval is {CI}.")
# With 95.0% confidence, the interval is below 38.69963013892556.
# With 95.0% confidence, the interval is above 35.867036527741114.
# With 95.0% confidence, the interval is (35.54756040462653, 39.01910626204015).
```
