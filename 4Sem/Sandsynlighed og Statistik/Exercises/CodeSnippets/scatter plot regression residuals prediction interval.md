Consider the following observed values of (xi, yi)  
xi -3 -1 -0.4 0 0.5 2 2.5 4 5.2  
yi -5.11 -1.49 -2.07 -0.12 5.33 4.81 10.20 12.53 18.51

1. Make a scatter plot
2. Find the estimated regression line $\hat{y} = \hat{β}0 + \hat{β}1x$ based on the observed data
3. For each xi compute the fitted value of yi using $\hat{y} = \hat{β}0 + \hat{β}1x_i$
4. Compute the residuals $ϵ_i = y_i − \hat{y}_i$
5. . Find R-squared (the coefficient of determination).
6. Predict the value for x = 7. Give a prediction interval for α = 0.05.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import t
# Number of data points
n = 9

# Given data
x = np.array([-3, -1, -0.4, 0, 0.5, 2, 2.5, 4, 5.2])
y = np.array([-5.11, -1.49, -2.07, -0.12, 5.33, 4.81, 10.20, 12.53, 18.51])

x = np.column_stack((np.ones(n), x))  # Add a column of ones to the input x for the constant term
B = np.linalg.lstsq(x, y, rcond=None)[0]  # Perform linear regression using least squares

# Plotting the scatter plot and the regression line
plt.scatter(x[:, 1], y)
plt.plot(x[:, 1], B[0] + B[1] * x[:, 1], 'r-')
plt.xlabel('x')
plt.ylabel('y')
plt.show()

meanx = np.mean(x[:, 1])
Sxx = np.sum((x[:, 1] - meanx) ** 2)
Sxy = B[1] * Sxx
meany = np.mean(y)
Syy = np.sum((y - meany) ** 2)
SSR = (Sxx * Syy - (Sxy) ** 2) / Sxx
sigma2 = SSR / (n - 2)

# Calculate the test statistics
TS = np.sqrt((n - 2) * Sxx / SSR) * np.abs(B[1])

# Calculate the p-value
pvalue = 2 * t.cdf(-TS, n - 2)

x0 = 3400
# Calculate the confidence interval
Delta = np.sqrt(1 / n + (x0 - meanx) ** 2 / Sxx) * np.sqrt(SSR / (n - 2)) * np.abs(t.ppf(0.05, n - 2))
C_low = B[0] + B[1] * x0 - Delta
C_up = B[0] + B[1] * x0 + Delta

# Print the results
print("Regression coefficients: B0 =", B[0], "and B1 =", B[1])
print("Test statistics:", TS)
print("p-value:", pvalue)
print("Confidence interval for x0 =", x0, ": [", C_low, ",", C_up, "]")

# Regression coefficients: B0 = 1.5406570841889105 and B1 = 2.931029208397939

# Test statistics: 10.187850325584954

# p-value: 1.89215228195249e-05

# Confidence interval for x0 = 3400 : [ 8114.403804159608 , 11819.676127114757 ]
```
![[Pasted image 20240604020402.png]]