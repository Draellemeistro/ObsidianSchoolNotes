# Problem P1
On average **Peter receives 125 emails per day**. Out of these 125 emails, **25 emails are spam**. A special software is used that allows to automatically filter the spam emails and put them in a special Spam folder. Specification of this software states that the detection rate of spam is **98%** and the **probability of a false positive is 7%**. Peter never checks the messages in Spam folder. What are the c**hances that he overlooks an important message** ( in other words, what is the probability that **an email that is classified as a spam and put in Spam folder is in fact not a spam**)?
**Note that a false positive in this case is a situation when a non-spam email is marked as spam. A false positive refers to a situation when a spam email is not marked as spam.**

**EVENTS**
S: received mail is spam
$S_{flat}$ mail is not spam
D: mail is put in spam folder
$D_{flat}$ mail is not put in spam folder

$P(S)=\frac{25}{125}=0.2$ mail is spam

$P(S_{flat})=1-0.2=0.8$ mail is not spam

$P(D_{flat}|S)=1-0.98=0.02$ mail is spam and is not put in spam folder
$P(D|S)=0.98$  The mail is spam, and is put in spam-folder

$P(D|S_{flat})=0.07$ mail is not spam, and is put in spam-folder

$P(D_{flat}|S_{flat})=1-0.07=0.93$ mail is not spam and is not put in spam folder

**If it was thrown in spam, what is the prob. that it is not a spam mail?** 
this is: $P(S_{flat}|D)$

The prob that a mail is in spam depends on the probability of whether or not it is spam, together with whether or not it is put into the spam folder, so: $P(D)$ 
$=P(D|S)*P(S)+ P(D|S_{flat})*P(S_{flat})$
$=0.98*0.2+0.07*0.8=0.252$

$P(S_{flat}|D)$ Can now be found through \____ 

$$P(S_{flat}|D)=\frac{P(D | S_{flat})*P(S_{flat})}{P(D)}$$
$$=\frac{P(D | S_{flat})*P(S_{flat})}{P(D|S)*P(S)+P(D|S_{flat}*P(S_{flat}))}$$
$$=\frac{0.07*0.8}{0.98*0.2+0.07*0.8}=\frac{0.07*0.8}{P(D)}=\frac{0.07*0.8}{0.252}$$
$$=0.22$$

# Problem P2
The bus arrivals at a bus stop follows a Poisson process. On average there are 4 busses coming to the bus stop during one hour.
**==avg of4 busses per hour==**
### (A) You are coming to the bus stop. What is the probability that you have to wait for a bus for more than 10 minutes?
$W:$ RV for time between arrivals
$P(X>10)$ ?
4 busses arriving during an hour, means the avg wait time should be about $\frac{4}{60}=15$ minutes.
$E[X]=15$ minutes
$\implies \lambda=\frac{1}{15}$

$P(X>10)=e^{-\lambda *10}=e^{-\frac{10}{15}}=e^{-\frac{2}{3}}\approx \frac{0.5}{3}$


### (B) What is the probability that you have to wait for a bus for exactly 10 minutes?
$P(X=10)$

### (C) Suppose that you are already waiting for a bus 5 minutes. What is the probability that you have to wait for a bus for yet another 10 minutes or more?


# Problem P3
X and Y are random variables that can take on values 0 and 1. It is known that: $$P(X=0,Y=0)=\frac{1}{2};P(X=1,Y=0)=\frac{1}{4};P(X=0,Y=1)=\frac{1}{4};P(X=1,Y=1)=0 $$
### (A) Explain why the probabilities specified above give us a valid joint pmf
Bernoulli 
$P(X=0,Y=0)=\frac{1}{2};P(X=1,Y=0)=\frac{1}{4};P(X=0,Y=1)=\frac{1}{4}$

$$P(X=0,Y=0)+P(X=1,Y=0)+P(X=0,Y=1)$$
$$\frac{1}{2}+\frac{1}{4}+\frac{1}{4}=1$$
### (B) Write down the pmf of X.



| X\Y | 0   | 1   |     |
| --- | --- | --- | --- |
| 0   | 1/2 | 1/4 | 3/4 |
| 1   | 1/4 | 0   | 1/4 |
|     | 3/4 | 1/4 |     |

### (C) Is X a discrete or continuous random variable? Does a distribution for X has a special name or it is a ”no-name” distribution?
X is discrete and a Bernoulli r.v
### (D) Are X and Y independent?
no $P(X=1)=\frac{1}{4}$ and $P(Y=1)=\frac{1}{4}$ 
if independent it should be= $P(X=1,Y=1)=P(X=1)*P(Y=1)=\frac{1}{4}*\frac{1}{4}$

### (E) Calculate the mean and variance for r.v. X.
$E[X]=\frac{1}{4}$ 
$Var(X)=E[(X-E[X])^2]=E[X^2]-E[X]^2$

$E[X^2]=E[X]$
$Var(X)=E[X]-E[X]^2=\frac{1}{4}-\left( \frac{1}{4} \right)^2=\frac{1}{4}\left( 1-\frac{1}{4} \right)=\frac{1}{4}*\frac{3}{4} = \frac{3}{16}$
### (F) Calculate $Cov(X,Y)$
$Cov(X,Y)=E[(X-E[X])*(Y-E[Y])]$ 
$Cov(X,Y)=E[XY]-E[X]*E[Y]$
$E[XY]=$


### (G) calculate $E[4X+8Y-3]$
we know a few things:
- $E[c*X]=c*E[X]$
- $E[X+Y]=E[X]+E[Y]$
- $E[X]=\frac{1}{4}$ (from earlier problems)

therefore:
$$E[4X+8Y-3]$$$$=4E[X]+8E[Y]-3$$
$$=4\frac{1}{4}+8 \frac{1}{4}-3$$
$$=1+2-3=0$$

# Problem s1
Table I shows the number of significant earthquakes recorded globally at every year from 2010 to 2017.


> [!quote] Table I
> 
> *NUMBER OF SIGNIFICANT EARTHQUAKES RECORDED GLOBALLY FROM 2010 TO 2017. SOURCE: OURWORLDINDATA.ORG*

| year | # of recorded earthquakes |
| ---- | ------------------------- |
| 2010 | 62                        |
| 2011 | 59                        |
| 2012 | 48                        |
| 2013 | 52                        |
| 2014 | 55                        |
| 2015 | 47                        |
| 2016 | 47                        |
| 2017 | 53                        |
### 1) Obtain the sample mean and variance

MEAN : 52.875
VAR : 31.2678

### 2) Assuming that the number of earthquakes per year shown in Table I is normally distributed, obtain the 95% confidence interval for the mean number of earthquakes per year.
$C_{0.95}=(\hat{\mu}_{n}-Z_{\frac{\alpha}{2}}\frac{\sigma}{\sqrt{ n }},\hat{\mu}_{n}+Z_{\frac{\alpha}{2}}\frac{\sigma}{\sqrt{ n }})$
$=(\hat{\mu}_{n}-1.96\frac{\sigma}{\sqrt{ n }},\hat{\mu}_{n}+1.96\frac{\sigma}{\sqrt{ n }})$
$$
### 3) You read in a newspaper that the average number of significant earthquakes per year is “60 or more.” Is this claim supported by the values in Table I with 95% confidence? Provide the means to support this conclusion.


# Problem S.2

An alternative way of defining the exponential distribution is: $$f(x;\beta)=\frac{1}{\beta}e^{-x/\beta}$$
### 1) Obtain the expression for the maximum likelihood estimator (MLE) for $\beta$


### 2) Is the MLE that you calculated consistent? Provide the necessary equations to support your answer


# Problem S.3
Table II shows the average CO2 emissions per capita from 2010 to 2019.

> [!quote] Table II
> YEARLY AVERAGE CO2 EMISSIONS PER CAPITA FROM 2010 TO 2019. SOURCE: OURWORLDINDATA.ORG

| year | yearly avg CO2 emissions per capita (tonnes) |
| ---- | -------------------------------------------- |
| 2010 | 7.20                                         |
| 2011 | 7.33                                         |
| 2012 | 7.32                                         |
| 2013 | 7.24                                         |
| 2014 | 7.24                                         |
| 2015 | 7.23                                         |
| 2016 | 7.03                                         |
| 2017 | 7.03                                         |
| 2018 | 7.04                                         |
| 2019 | 7.06                                         |

### 1) Perform linear regression on the data. Which parameters do you obtain?


### 2) Estimate the mean response (i.e., the average CO2 emissions per capita) for the year 2020.


### 3) Calculate the prediction interval for a new response in 2020 with 95% confidence. The measured CO2 emissions per capita in 2020 was 6.71, does this value fall within the calculated interval?