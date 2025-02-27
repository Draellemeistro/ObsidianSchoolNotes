$$
s^2 = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2
$$
where:
- $(s^2)$ represents the sample variance
- $(n)$ is the number of observations in the sample
- $(x_i)$ represents each individual observation in the sample
- $(\bar{x})$ represents the sample mean

**==Important The square root of the variance is the standard deviation Look at the denominator in the formula for the sample variance==**

```python
numbers = [1, 1, 4, 4, 5, 5]

number_length = len(numbers)  # Number of observations in the sample

mean_value = 0
for n in numbers:
    mean_value += n  # Calculate the sample mean manually
mean_value = mean_value / number_length

sum_squared_diff = 0
for n in numbers:
    sum_squared_diff += (n - mean_value) ** 2

sample_variance = sum_squared_diff / (number_length - 1)

print("Sample variance:", sample_variance)
```
