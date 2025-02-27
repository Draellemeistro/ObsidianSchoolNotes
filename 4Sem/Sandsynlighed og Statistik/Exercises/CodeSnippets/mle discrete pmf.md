Suppose that X is a discrete random variable with the following probability mass function:  
X 0 1 2 3  
P(X) 2θ/3 θ/3 2(1 − θ)/3 (1 − θ)/3  
where 0 ≤ θ ≤ 1 is a parameter. The following 10 independent observations were taken from such a distribution: (3, 0, 2, 1, 3, 2, 1, 0, 2, 1). What is the maximum likelihood estimate of θ?.

```python
import numpy as np
from scipy.optimize import minimize

# Define the negative log-likelihood function
def neg_log_likelihood(theta, observations):
    probabilities = np.array([(2*theta/3)**2, theta/3, (2*(1-theta)/3)**2, (1-theta)/3])
    return -np.sum(np.log(probabilities))

# Observations
observations = np.array([3, 0, 2, 1, 3, 2, 1, 0, 2, 1])

# Minimize the negative log-likelihood function
result = minimize(neg_log_likelihood, x0=0.5, args=(observations,), method='BFGS')

# Extract the maximum likelihood estimate of theta
mle_theta = result.x[0]

# Display the maximum likelihood estimate of theta
print("Maximum Likelihood Estimate of θ:", mle_theta)
```
Consider an industrial scenario where two robots, labeled as R1 and R2 respectively, are carrying out some tasks in a manufacturing plant. Robot R1 needs to know how far R2 is in order to avoid collisions. To that end, R1 asks R2 to send a constant signal S during N time slots. The signal is transmitted in a wireless way, so R1 does not receive S but an attenuated version of S plus some noise terms wi at each time slot i (the attenuation does not affect the noise):  
𝑦𝑖=𝛼𝑆+𝑤𝑖where α is the attenuation and the noise samples wi are independent and Gaussian distributed with zero mean and known variance σ^2;that is,  
𝑤𝑖∼𝑁(0,𝜎2)

1. If R1 knows that the attenuation due to the distance d is given by𝛼=0.5/𝑑how can R1 estimate the distance d to R2?
2. Given a sample(𝑦1,𝑦2,...,𝑦10)=(1.1,0.68,0.54,0.99,0.26,0.84,0.41,0.5,0.42,0.81)𝑆=5and𝜎2=0.1, what is the estimated distance between R1 and R2?

```python
# Given variables
S = 5  # Signal strength
sigma_squared = 0.1  # Variance of noise
yi = [1.1, 0.68, 0.54, 0.99, 0.26, 0.84, 0.41, 0.5, 0.42, 0.81]  # Received signal observations

# Step 1: Calculate the reciprocal of the attenuation
reciprocal_alpha = 1 / (0.5 / S)

# Step 2: Calculate the estimated distance
distance_estimate = 1 / (reciprocal_alpha * sum(yi))

# Print the estimated distance
print("Estimated Distance:", distance_estimate)
```