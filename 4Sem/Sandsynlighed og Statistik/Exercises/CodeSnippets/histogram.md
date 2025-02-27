The average particulate concentration, in micrograms per cubic meter, was measured in a petrochemical complex at 36 randomly chosen times, with the following concentrations resulting:  
5, 18, 15, 7, 23, 220, 130, 85, 103, 25, 80, 7, 24, 6, 13, 65, 37, 25,  
24, 65, 82, 95, 77, 15, 70, 110, 44, 28, 33, 81, 29, 14, 45, 92, 17, 53

1. Represent the data in a histogram.
2. Find the sample mean, median and mode.
3. Is the histogram approximately normal?

```python
import matplotlib.pyplot as plt
import numpy as np
import scipy.stats as st

data = [5, 18, 15, 7, 23, 220, 130, 85, 103, 25, 80, 7, 24, 6, 13, 65, 37, 25, 24, 65, 82, 95, 77, 15, 70, 110, 44, 28, 33, 81, 29, 14, 45, 92, 17, 53]
#a)
plt.hist(data)
#b)
mu = np.mean(data)
print("Mean:", mu)
median = np.median(data)
print("median:", median)
mode = st.mode(data) #Nummeret der opstår flest gange
print("mode:", mode)
#c)
print("c) No it is not normal distributed")
```