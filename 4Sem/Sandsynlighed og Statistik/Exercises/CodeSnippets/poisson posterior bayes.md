It is known that disks produced by a certain company will be defective with probability 0.01 independently of each other. The company sells the disks in packages of 10 and offers a moneyback guarantee that at most 1 of the 10 disks is defective. What proportion of packages is returned? If someone buys three packages, what is the probability that exactly one of them will be returned?
``` python
# using the poisson r.v. in python
from scipy.stats import poisson

lambda_val = 10 * 1/100  # Mean of the Poisson distribution (λ = np)  # Mean of the Poisson distribution (λ = np)

# Calculate the probability using the survival function (1 - cumulative distribution function)

probability = 1 - poisson.cdf(1, lambda_val)  # P(X >= 5) = 1 - P(X <= 4)

print(f"The probability of having 1 or more errors in 1 packet is: {probability:.4f}")

import numpy as np

def bayes_formula(prior_prob, likelihood, evidence):
    # Convert lists to numpy arrays for element-wise multiplication
    prior_prob = np.array(prior_prob)
    likelihood = np.array(likelihood)
    
    # Calculate the probability using Bayes' formula
    numerator = likelihood * prior_prob
    denominator = np.sum(likelihood * prior_prob)
    posterior_prob = numerator / denominator
    return posterior_prob

# Example usage
prior_prob = [probability, 1-probability] # Prior probabilities P(A)
likelihood = [0.8, 0.2]  # Likelihoods P(B | A)
evidence = 0.4  # Evidence P(B)

posterior_prob = bayes_formula(prior_prob, likelihood, evidence)
print("Posterior Probability:", posterior_prob)
```
