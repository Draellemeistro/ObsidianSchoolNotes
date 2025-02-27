**==FOR MULTIPLE R.V.'s IN RELATION TO EACHOTHER SEE:==   [[joint CDF]]**

> [!NOTE] Definition
> The **CDF** of a r.v. X is defined for any real number x as the probability of the event $\{X\leq x\}$ $$F_{X}(x)=P(X\leq x)=P(X \in (-\infty,x])$$
> - F is a function of x
> - All probability questions about X can be answered in terms of its distributions function
> - **Example:** $$\{X\leq b\}=\{X\leq a\}\cup\{a<X\leq b\}$$ 
>   $$P\{X\leq b\}=P\{X\leq a\}+P\{a<X\leq b\}$$
>   **==SEEMS THE ONE BELOW IS IMPORTANT==**
>   $$P\{a<X\leq b\}=F(b)-F(a)$$


> [!example] CDF for [[Discrete Random Variables|Discrete r.v.]]
> the **CDF** is a step-function and can be expressed as: $$F(a)=\sum_{all\_x\leq a}p(x)$$
> ==!!!!!!== **[[Probability Mass Function (PMF)|PMF]] ---> CDF** ==!!!!!!==
>  ![[Pasted image 20240602152922.png]]
>  ![[Pasted image 20240602152933.png]]
>  see [[Bernoulli rv]] for coin-flip example



> [!NOTE] CDF for [[Continuous Random Variables and their Distributions|Continuous r.v]]
> The relationship between **CDF** and **[[Probability Density Function (PDF)|PDF]]** is expressed by:
> $F(a)=P(X\in(-\infty,a])=\int_{-\infty}^{a}  \, f(x)dx$:       ==**[[Probability Density Function (PDF)|PDF]]** --> **CDF**==
> $\frac{d}{da}F(a)=F(a)$:  ==**CDF** --> **[[Probability Density Function (PDF)|PDF]]**==


# Properties of CDF

> [!NOTE] Title
> 1. $0\leq F(x)\leq 1$
> 2. $\lim_{ x \to \infty }F(x)=1$
> 3. $\lim_{ x \to -\infty }F(x)=0$
> 4. $F(x)$ is a nondecreasing function: 
>    $F(x)\leq F(b)$ if $a<b$
> 5. $F(x)$ is a continuous from the right: 
>    $F(b)=\lim_{ h \to 0 }F(b+h)=F(b+)$
> 6. probability that a [[random variables|r.v.]] X takes on a specific value *b* is equal to the jump(*step*) of **CDF** at the point *b*: 
>    $P(X=b)=F(b+)-F(b-)$
> 

![[Pasted image 20240602154335.png]]
![[Pasted image 20240602154354.png]]
## Property no 1

## Property no 2

## Property no 3

## Property no 4

## Property no 5
**Continuous from the right:**
![[Pasted image 20240602154449.png]]

## Property no 6
we know $$P\{a<X\leq b\}=F(b)-F(a)$$
$$P\{x=b\}=\lim_{ \epsilon \to 0 }\{b-\epsilon<X\leq b+\epsilon\}=$$
$$=\lim_{ \epsilon \to 0 }[F(b+\epsilon)-F(b-\epsilon)]=$$
$$=F(b+)-F(b-)$$

![[Pasted image 20240602155109.png]]
![[Pasted image 20240602155119.png]]
# Example of a mixed [[random variables|r.v.]]

# Slides
$$F(x) = P(X=<x)  = P(X∈(-\infty , x]) $$
![[Pasted image 20240218155404.png]]
![[Pasted image 20240218155454.png]]![[Pasted image 20240218155512.png]]
![[Pasted image 20240218155534.png]]
![[Pasted image 20240218155550.png]]
## Properties of CDF
1. $0 =< F(x) =< 1$
2. $lim_{x\to\infty}F(x)=1$
3. $lim_{x\to -\infty}F(x)=0$
4. $F(x)$ is a nondecreasing function $F(a)\leq F(b)$ if $a<b$
5. $F(x)$ is a continuous from the right: $F(b) = lim_{h\to0}F(b+h)=F(b+)$
	1. ![[Pasted image 20240218160617.png]]
6. Probability that a [[random variables|r.v.]] X takes on a specific value b is equal to the jump (step) of CDF at the point b: $P(X=b)=F(b+)-F(b-)$
	1. ![[Pasted image 20240218160639.png]]
	2. ![[Pasted image 20240218160651.png]]
![[Pasted image 20240218160552.png]]
## example of a mixed [[random variables|r.v.]].
![[Pasted image 20240218160730.png]]
![[Pasted image 20240218160747.png]]
![[Pasted image 20240218160825.png]]

# Joint CDF (multiple r.v.)
![[Pasted image 20240218161039.png]]
