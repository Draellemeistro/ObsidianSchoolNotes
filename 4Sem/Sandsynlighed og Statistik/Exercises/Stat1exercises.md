# Excercises

## Attempts
### Exercise 1: Use the data in the moodle materials folder to plot the absolute, relative, and normalized histograms of:
#### A) he latency for communication in our Starlink setup (==file: Starlink latency.csv==)
```python
import matplotlib.pyplot as plt  
import numpy as np  
import pandas as pd  
  
# Load the data  
file_path = 'Starlink_latency.csv'  
data = pd.read_csv(file_path)  
data.columns = data.columns.str.strip()  
latency = data['pop_latency[ms]']  
  
  
# Decide the number of bins
#############################

# Relative Histogram  
plt.figure(figsize=(10, 6))  
plt.hist(latency, bins=50, density=True, edgecolor='black')  
plt.title('Relative Histogram of Latency')  
plt.xlabel('Latency [ms]')  
plt.ylabel('time[s]')  
plt.show()  
  
# Normalized Histogram  
mu, sigma = np.mean(latency), np.std(latency)  
count, bins, ignored = plt.hist(latency, bins=50, density=True)  
plt.plot(bins, 1/(sigma * np.sqrt(2 * np.pi)) * np.exp(-(bins - mu)**2 / (2 * sigma**2)), linewidth=2, color='orange')  
plt.title('Normalized Histogram of Latency')  
plt.xlabel('Latency [ms]')  
plt.ylabel('time[s]')  
plt.show()


```
![[Pasted image 20240603162034.png]]


#### B) The temperature measured by a sensor during a PhD course at Oulu University (==file: temperature.csv==)
```python
# Define the column names  
column_names = ["temp", "temperature", "sample_timestamp", "time1", "received timestamp", "time2", "Message length",  
                "length"]  
  
# Load the temperature data  
file_path_temperature = 'temperature.csv'  
temperature_data = pd.read_csv(file_path_temperature, names=column_names, header=None)  
  
# Extract the temperature column  
temperature = temperature_data['temperature']  
  
# Print the temperature data  
print(temperature)  
  
# Calculate the frequency of each temperature  
frequency = temperature.value_counts()  
  
print(frequency)  
  
# Plot the absolute histogram  
plt.figure(figsize=(10, 6))  
plt.hist(temperature, bins=30)  
plt.title('Absolute Histogram of Temperature')  
plt.xlabel('Temperature')  
plt.ylabel('Frequency')  
plt.show()  
  
# Plot the relative histogram  
plt.figure(figsize=(10, 6))  
plt.hist(temperature, bins=30, density=True, edgecolor='black')  
plt.title('Relative Histogram of Temperature')  
plt.xlabel('Temperature')  
plt.ylabel('Relative Frequency')  
plt.show()  
  
# Plot the normalized histogram  
plt.figure(figsize=(10, 6))  
count, bins, ignored = plt.hist(temperature, bins=30, density=True, edgecolor='black')  
mu, sigma = np.mean(temperature), np.std(temperature)  
plt.plot(bins, 1 / (sigma * np.sqrt(2 * np.pi)) * np.exp(-(bins - mu) ** 2 / (2 * sigma ** 2)), linewidth=2,  
         color='orange')  
plt.title('Normalized Histogram of Temperature')  
plt.xlabel('Temperature')  
plt.ylabel('Density')  
plt.show()
```
![[Pasted image 20240603174526.png]]
#### Are these datasets approximately normal?
No. They don't follow the normal(Gaussian) distribution

### Exercise 2: Simulate rolling a fair dice n times

> [!tip] TIP
> ***Tip***: *You can use the code *dice_loln.py* in the moodle page as a base*

#### a) Calculate the sample mean $\bar{X_{i}}$ and $\bar{X_{i}}+S_{i}$ for all $i=1,2,\dots,n$

#### b) Plot the sample mean $\bar{X_{i}}$
![[Pasted image 20240603181417.png]]
#### c) Plot a normalized histogram with the *n* outcomes. How many times do you need to roll the dice so the histogram resembles the pmf of a uniform RV?
![[Pasted image 20240603184500.png]]
![[Pasted image 20240603184508.png]]
![[Pasted image 20240603184513.png]]
![[Pasted image 20240603184517.png]]
![[Pasted image 20240603184520.png]]

### Exercise 3: 
#### Consider the case of flipping a fair coin $n$ times and let $H_{n}$ be the random variable (RV) of the number of heads. Also recall that the sum of n Bernoulli RVs is a Binomial random variable with mean $np$ and variance $np(2−p)$. Calculate and compare the probability of observing $H_{10} ≥ 7$ and $H_{100} ≥ 70$ using each of the following methods.


> [!NOTE] info from problem
> - $H_{n}$: RV for the number of heads
> - sum of n Bernoulli RVs is a Binomial random variable with:
> 	- mean $np$
> 	- variance $np(2-p)$
> - $H_{10}$: number of heads after 10 coin-flips. 100 flips for $H_{100}$
> 	- so calc and compare probability of flipping 7 or more heads in 10 flips
> - $p$: assuming the coin is fair: $p=0.5$

![[Pasted image 20240603192450.png]]

#### a) Summing over the formula for the probability mass function (pmf) of Binomial RVs $$P(H_{n}\geq k)=\sum_{i=1}^{n}{n\choose k}p^k(1-p)^{n-i}$$
##### $H_{10}$ 
$$P(H_{10}\geq 7)=\sum_{i=1}^{10}{10\choose 7}0.5^7(0.5)^{10-i}$$
##### $H_{100}$ 
$$P(H_{100}\geq 70)=\sum_{i=1}^{100}{100\choose 70}0.5^{70}(0.5)^{100-i}$$
##### Fra gpten
The probability of observing 𝐻𝑛≥𝑘Hn​≥k for a Binomial random variable 𝐻𝑛Hn​ with parameters 𝑛n and 𝑝p is given by:
$$P(H_{n}\geq k)=\sum_{i=k}^{n}{n\choose i}p^i(1-p)^{n-i}$$

###### Case 1: $𝐻10≥7$
we need to calculate $P(H_{10}\geq 7)$
$$P(H_{n}\geq 7)=\sum_{i=7}^{10}{10\choose i}(0.5)^i(0.5)^{10-i}$$
This can be calculated as:

$$P(H_{n}\geq 7)=\sum_{i=7}^{10}{10\choose 7}(0.5)^{10}+{10\choose 8}(0.5)^{10}+{10\choose 9}(0.5)^{10}+{10\choose 10}(0.5)^{10}$$

###### Case 2: $𝐻100≥70$
we need to calculate $P(H_{100}\geq 70)$
$$P(H_{100}\geq 70)=\sum_{i=70}^{100}{100\choose i}(0.5)^i(0.5)^{100-i}$$
This can be calculated similarly, but due to the large number of terms, it's typically computed using statistical software.

#### b) Using the central limit theorem
he CLT approximates the distribution of the sum of a large number of i.i.d. random variables by a normal distribution. For a Binomial distribution $H_n$ with parameters $n$ and $p$:
$$\text{Mean: }\mu=np$$
$$\text{Variance: }\sigma^2=np(1-p)$$
We can approximate $H_n$ by a normal distribution $N(np,np(1-p))$. The probability $$P(H_n\geq k)\approx P\left( Z\geq \frac{k-np}{\sqrt{ np(1-p) }} \right)$$
Where $Z$ is a standard normal variable.
###### Case 1: $𝐻_{10}≥7$
$$\mu=10*0.5=5$$
$$\sigma=\sqrt{ 10*0.5*0.5}=\sqrt{ 2.5 }\approx1.58$$
$$P(H_{10}\geq 7)\approx P\left( Z\geq \frac{7-5}{\sqrt{ 10*0.5*0.5}} \right)=$$
$$P\left( Z\geq \frac{7-5}{1.58} \right)=$$
$$=P(Z\geq1.27)$$
Using standard normal tables or a calculator
$$P(Z\geq1.27)\approx 1-0.8980=0.1020$$

###### Case 2: $𝐻_{100}≥70$
$$\mu=100*0.5=50$$
$$\sigma=\sqrt{ 100*0.5*0.5}=\sqrt{ 25 }=5$$

$$P(H_{100}\geq 70)\approx P\left( Z\geq \frac{70-0}{\sqrt{ 100*0.5*0.5}} \right)=$$
$$P\left( Z\geq \frac{70-50}{5} \right)=$$
$$=P(Z\geq4)$$
Using standard normal tables or a calculator
$$P(Z\geq 4)\approx 1-0.99997=0.00003$$



### Exercise 4: 
#### A football team will play $60$ games this year. Thirty-two of these games are against teams playing the champions league, denoted as class A teams, and $28$ are against other teams, denoted as class B teams. The outcomes of the games are independent. The team will win each game against a class A team with probability $0.5$, and it will win each game against a class B team with probability $0.7$. Let X denote its total number of victories in the year.


> [!NOTE] Info from problem
> - 60 games
> 	- 32 games agains class A teams
> 	- 28 games against class B teams
> - independent outcomes
> 	- outcome of a game is a **Bernoulli RV** (*win/lose*)
> - prob. of win
> 	- against class A team: $0.5$
> 	- against class B team: $0.7$
> - $X$: total number of victories


Lets start by plotting the individual probabilities for $X$, or rather, the distributions for $X_A$ and $X_B$ **WE NEED TO DO THE FOLLOWING:**
1. Define the parameters for the Binomial distributions for class A and class B teams.
2. 1. Calculate the PMF for the number of wins against class A and class B teams.
$$X_{A}\sim Binomial(32,0.5)$$
$$X_{B}\sim Binomial(28,0.7)$$



#### a) is $X$ a Binomial RV?
both $X_A$ and $X_B$ are binomial distributions. Both are independent. $X$ as a joint distribution of those two, is simply just the sum of the two binomial distributions: $X=X_A+X_B$

#### b) Let $X_A$ and $X_B$ denote, respectively, the number of victories against class **A** and class **B** teams. What are their distributions?


``` python
# Parameters  
n_A = 32  
p_A = 0.5  
n_B = 28  
p_B = 0.7  
  
# Define the range of possible wins  
x_A = np.arange(0, n_A + 1)  
x_B = np.arange(0, n_B + 1)  
  
# Calculate the PMF for class A and class B teams  
pmf_A = binom.pmf(x_A, n_A, p_A)  
pmf_B = binom.pmf(x_B, n_B, p_B)  
  
# Plotting the PMF for class A teams  
plt.figure(figsize=(12, 6))  
  
plt.subplot(1, 2, 1)  
plt.bar(x_A, pmf_A, color='blue', alpha=0.7)  
plt.title('PMF of Wins against Class A Teams')  
plt.xlabel('Number of Wins')  
plt.ylabel('Probability')  
plt.grid(True)  
  
# Plotting the PMF for class B teams  
plt.subplot(1, 2, 2)  
plt.bar(x_B, pmf_B, color='green', alpha=0.7)  
plt.title('PMF of Wins against Class B Teams')  
plt.xlabel('Number of Wins')  
plt.ylabel('Probability')  
plt.grid(True)  
  
# Show plots  
plt.tight_layout()  
plt.show()
```
![[Pasted image 20240603195553.png]]
#### c) What is the relationship between $X$, $X_{A}$ and $X_B$
 To find the total number of wins, we can combine the wins against class A teams and class B teams. Since the total number of wins $X$ is the sum of the two independent Binomial RVs, we need to compute the distribution of the sum. EZ PZ
 $$X=X_{A}+X_{B}$$
```python
 ################
 ##
 ## IN ADDITION TO THE CODE FROM (b)
 ##
 ################
 # Calculate the PMF for total wins using convolution  
pmf_total = np.convolve(pmf_A, pmf_B)  
  
# Define the range of possible total wins  
x_total = np.arange(0, n_A + n_B + 1)  
  
# Plotting the PMF for total wins  
plt.figure(figsize=(12, 6))  
plt.bar(x_total, pmf_total, color='purple', alpha=0.7)  
plt.title('PMF of Total Wins')  
plt.xlabel('Number of Wins')  
plt.ylabel('Probability')  
plt.grid(True)  
plt.show()
```
![[Pasted image 20240603200316.png]]
#### d) Approximate the probability that the team wins 40 or more games this year
$$P(X\geq 40)$$
**For a binomial distr. the PMF is given, where 
*n* is total number of games
*k* is number of wins
*p* is prob of win in a single game**
$$\text{PMF: }P(X=k)={n\choose k}p^k(1-p)^{{n-k}}$$
**The CDF gives the prob. of getting *k* or fewer wins:** $$P(X\leq k)=\sum_{i=0}^k{n\choose i}p^i(1-p)^{n-i}$$
**To find $P(X\geq 40)$** the complementary probability can be used: $$P(X\geq 40)=1-P(X\leq 40)=1-P(X\leq 39)$$
==**this means:** find $P(X\leq 39)$ and subtract it from 1==
Since $X_A$ and $X_B$ are independent, we should be able calculate them seperately: 
==!!!!! **PROBLEM: there are not enough games for either of the classes** !!!!!!!!==
To approximate the probability that the team wins 40 or more games, you can sum the probabilities of the PMF from 40 to the maximum number of games.
$$P(X\geq 40)=$$

$$\text{The probability that the team wins 40 or more games is approximately 0.1473}$$

We asssume that the distr. of $X_A$ and $X_B$ can be  approximated by normal distributions:
$N_{A}\sim N(n_{A}p_{A},n_{A}p_{A}(1-p_{A}))$ and $N_{B}\sim N(n_{B}p_{B},n_{B}p_{B}(1-p_{B}))$
the sum of them can be approximated: $X\sim N(\mu_{X},\sigma^2_{X})$ were $\mu_{X}=n_{A}p_{A}+n_{B}p_{B}$  and $\sigma^2_{X}=n_{A}p_{A}(1-p_{A})+n_{B}p_{B}(1-p_{B})$

with these, we approximate: $$P(X\geq 40)=11-\frac{1}{2}\left[ 1+erf\left( \frac{{40-\mu_{X}}}{\sigma_{X}\sqrt{ 2 }} \right) \right]=0.1187$$

```python
# Parameters  
n_A = 32  
p_A = 0.5  
n_B = 28  
p_B = 0.7  
  
# Mean and variance for the normal distributions  
mu_X = n_A * p_A + n_B * p_B  
sigma_X2 = n_A * p_A * (1 - p_A) + n_B * p_B * (1 - p_B)  
sigma_X = np.sqrt(sigma_X2)  
  
# Calculate the probability using the normal approximation  
prob_40_or_more = 1 - 0.5 * (1 + erf((40 - mu_X) / (sigma_X * np.sqrt(2))))  
  
print("Probability of achieving 40 or more wins:", prob_40_or_more)
# Output:  
# Probability of achieving 40 or more wins: 0.0002687997035848194  
# Compare this to the output of exercise4c.py:
```

### Exercise 5:
#### The room temperature during a PhD course was recorded using a Raspberry Pi and a temperature sensor. The collected values are in the file ==temperature.csv== (*the temperature is the second column*)
#### a) calculate the sample mean $\bar{X}_{n}$ and variance $S_{n}^2$ of the temperature with all the $n=253$ measurements

#### b) assume $\bar{X}_{n}$  is the true temperature $\mu$ and that $S_{n}^2$ is the real variance of the gaussian noise that affects each measurement of the sensor, denoted by $\sigma^2$. Consequently, assume that the temperature measurements have a distribution $X_i\sim N(\mu,\sigma^{2})$. Plot the likelighood or log-likelikood function for the first 10 and with first 100 measurements

#### c) Calculate the Maximum Likelihood Estimator (MLE) for $μ$ with the first 10 and with the first 100 measurements under the previous assumption.


## Problems

![[Statistics2024-Exercises1 (1).pdf]]
## Solution
![[Solution-Statistics2024-Session1 (1).pdf]]

# Quiz
![[Statistics2024-Quiz1.pdf]]
## Solutions
![[Solution-Statistics2024-Quiz1.pdf]]