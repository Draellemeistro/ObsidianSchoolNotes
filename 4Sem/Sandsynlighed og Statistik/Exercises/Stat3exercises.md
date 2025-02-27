# Excercises

## Attempts
### Exercise 1: adapted from chapter 8, problem 25
#### It is claimed that a certain type of bipolar transistor has a mean value of current gain that is at least $210$. A sample of these transistors is tested. If the sample mean value of the current gain is $200$ and it is known that the standard deviation is $35$, would the claim be rejected at the $5$  percent level of significance if:


> [!NOTE] info from problem
> - mean current gain $210<$ 
> - sample mean: $200$
> - std. deviation: $35$
> - lvl of significance: $5\%$
> 
> **==TIPS:==**
> - first formulate the null hypothesis $H_0$ then identify the type of test:
> 	- is it one-sided or two-sided?
> 	- what is the test statistic $T$ that you should use?
> 	- Will you compare $T$ to the threshold $c$ or the $p-value$ tto $\alpha$

The null and alternative hypotheses are: 
$$H_{0}:\mu\geq210, H_{a}:\mu<210$$
We use the ***z-test*** formula for the sample mean:
$$z=\frac{{\bar{x}-\mu_{0}}}{\sigma/\sqrt{ n }}$$


> [!NOTE] further info:
> - $\bar{x}$ is the sample mean
> - $\mu_0$ is the pop mean under the null hypothesis($H_0$)
> - $\sigma$ is the pop std deviation
> - $n$ is the sample size

The critical value for a one-tailed test at the 5% significance level($\alpha=0.05$) is approx $-1.645$. if the calculated $z-value$ is less than $-1.645$ we reject the null hypothesis($H_0$)
#### a) the sample size is 25?
$$z=\frac{{200-210}}{35/\sqrt{25}}=\frac{{200-210}}{7}=1.4286$$

#### b) the sample size is 100?

$$z=\frac{200-210}{35/\sqrt{ 100 }}=\frac{{200-210}}{3.5}=2.8571$$

#### using T-test for one-sided test:
$$T=\frac{(\hat{\mu}_{n}-\mu_{0})\sqrt{ n }}{S_{n}}$$
the rejection region is: $$R=\{x:T(x)<c\}$$
we also need to calculate the value of $c=-Z_{\alpha}$

we have two options,
==option 1:==  compare $T$ to the threshold $c$
$$c=-t_{\alpha,n-1}$$
if $T<c$ we reject null hypothesis $H_0$

==option 2:== the $p-value$ to $\alpha$
The p-value is obtained from the t-distribution. If the p-value is less than $\alpha$, we reject the null hypothesis $H_0$

$$\text{for n=25: }T=\frac{(200-210)\sqrt{ 25 }}{35}=\frac{{-10*5}}{35}=-1.4286$$
$$\text{for n=100: }T=\frac{(200-210)\sqrt{ 100 }}{35}=\frac{{-10*10}}{35}=-2.8571$$

#### Interpret the results

### Exercise 2
#### According to the U.S. Bureau of Census, $25.5 \text{ percent}$ of the population of those age 18 or over smoked in 1990. A scientist has recently claimed that this percentage has since increased, and to prove her claim she randomly sampled $500$ individuals from this population. If $138$ of them were smokers, is her claim proved? Use the 5 percent level of significance


> [!NOTE] info from problem
> - $25.5 \text{ percent}$ of pop were smokers in 1990
> - sample n: $500$
> - smokers: $138$
> - lvl of significance: $5\%$

$$v=Pr(X\geq 138;p_{0})=\sum_{k=138}^{500}{500\choose k}p_{0}^k(1-p_{0})^{500-k}=0.1525$$

$$T=\frac{(\hat{p}_{n}-p_{0})\sqrt{ n }}{p_{0}(1-p_{0})}$$
the rejection region is $$T>T_{n-1,\alpha}$$
### Exercise 3


### Exercise 4


### Exercise 5
#### A question of medical importance is whether jogging leads to a reduction in one’s heart rate. To test this hypothesis, 8 nonjogging volunteers agreed to begin a 1-month jogging program. After the month, their pulse rates were determined and compared with their earlier values. If the data are as follows, can we conclude that jogging has an effect on the pulse rates with a 5 percent level of significance?

> [!NOTE] INFO from problem
> - **n**: 8 joggers
> - significance level: $5\%$

#### Explanation
- **Mean of differences**: The average of the differences between the pulse rates before and after jogging.
- **Standard deviation of differences**: The standard deviation of the differences between the pulse rates.
- **t-value**: The test statistic calculated using the mean and standard deviation of the differences.
- **Critical t-value**: The value from the t-distribution for 𝑛−1n−1 degrees of freedom and 𝛼/2α/2 significance level (for two-tailed test).
- **P-value**: The probability of obtaining a test statistic at least as extreme as the one observed, under the null hypothesis.
- **Reject 𝐻0H0​**: A boolean indicating whether to reject the null hypothesis based on the p-value and significance level.

If the p-value is less than 0.05, we reject the null hypothesis and conclude that jogging has a statistically significant effect on pulse rates. Otherwise, we fail to reject the null hypothesis.

The test to use is a paired two-sided t-test where the null hypthesis is $H_0: \mu_{A}-\mu_{B}$
We calculate mean of the pulse rate before $\bar{X}_{B}=81.125$ and after $\bar{X}_{A}=83.875$
Then, we calcilate the variance before $S_{B}^2=\frac{1}{8-1}\sum_{i=1}^8(X_{i}-\bar{X})^2=193.2678$ amd after jogging $S_{A}^2=\sqrt{ (S_{B}^2+S_{A}^2)/n }=6.3157$
with these values we calculate tje test statostoc as $T=\frac{|\mu|}{S}=0.4354$ and the threshold is $c=T_{2n-2,\alpha/2}=2.1447$
## Problems
![[Statistics2024-ExercisesSession3.pdf]]
## Solutions
![[Solutions-Statistics2024-Exercises3-CPH.pdf]]