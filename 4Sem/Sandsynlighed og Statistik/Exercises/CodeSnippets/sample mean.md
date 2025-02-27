(This not always equal to the median the middle of the sample but is always equal to the avarage)
$$\bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i$$

where:
- $\bar{X}$ represents the sample mean
- $n$ is the number of observations
- $X_i$ represents each indivbidual observation in the sample

```python
x = [1, 2, 4, 4, 5, 6]  # X is the observed values
n = 6  # Number of observations

summen = 0
one_divided_by_n = 1 / n

# Summate the observed values in x
for num in x:
    summen += num

# Calculate the mean by multiplying the two parts of the equation
mean = one_divided_by_n * summen
print(mean)
```