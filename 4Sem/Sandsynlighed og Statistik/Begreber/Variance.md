# Motivation 
The variations are given by r.v. $D=X-E[X]$. D can take on positive and negative values. We are only interested in magnitude ->we work with |D| or D^
# Definition
variance of r.v. X is defined as(using [[Expectation]]): $$Var(X)=E[(X-E(X))^2]$$
Which can be simplified to: $$Var(X)=E[X^2]- E[X]^2$$
## Another formula for variance
![[Pasted image 20240218163329.png]]

## Standard deviation of r.v. X is
$$Std(X)=\sqrt{Var(X)}$$
## Some useful identities concerning variances
$$Var(aX+b)= a^2 Var(X)$$
$$Var(b)= 0$$
$$Var(X+b)= Var(X)$$
### proof
![[Pasted image 20240218163607.png]]

## Example
Variance of an Indicator of an event


#TODO fix it up and add links
![[Pasted image 20240218163634.png]]
![[Pasted image 20240218163641.png]]
# Covariance
## What does it show?
The covariance is an indicator of the relationship between two r. vs. and shows the joint variability of two r.vs.

If two variables tend to vary together (when one is above its expectation, then the other is also above its expectation), then covariance is positive. And negative otherwise.
## Definition
Covariance of 2 r.v. X and Y is defined by
$$Cov(X,Y)=E[(X-E[X]) (Y-E[Y])]$$
simplified to $$Cov(X,Y)=E[XY]-E[X]E[Y]$$
![[Pasted image 20240218163856.png]]
### Proof
![[Pasted image 20240218163912.png]]
## Properties of Covariance #TODO 
![[Pasted image 20240218163942.png]]
### Prop 5.
![[Pasted image 20240218164008.png]]
#### Proof
![[Pasted image 20240218164042.png]]
![[Pasted image 20240218164056.png]]

### Prop 4
![[Pasted image 20240218164022.png]]

# Variance of a sum of r.vs
![[Pasted image 20240218164127.png]]![[Pasted image 20240218164142.png]]
# Correlation coefficient
Instead of covariance, we can work with dimensionless quality:
Correlation coefficient of X and Y: $$Corr(X,Y) = \dfrac{Cov(X,Y)}{\sqrt{Var(X)}\sqrt{Var(Y)}}$$
==**CAREFUL: UNIT FUCKERY**== 
	![[Pasted image 20240218164630.png]]

Values of correlation coefficient lie between –1 and 1.
# The nth moment of r.v. X
![[Pasted image 20240218164714.png]]
## Moment generating function
![[Pasted image 20240218164727.png]]
### How to obtain E\[X] and Var(X) from moment generating function?
![[Pasted image 20240218164824.png]]
![[Pasted image 20240218164831.png]]
![[Pasted image 20240218164843.png]]
![[Pasted image 20240218164850.png]]
