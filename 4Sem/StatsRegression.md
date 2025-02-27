[KILDE](https://github.com/agangster1/Sandsynlighed-og-statestik-formelsamling/blob/main/MM6_Regression.ipynb)
# Linear regression
- data in the form $(X_{1},Y_{1}),\dots,(X_{n},Y_{n})$ 
- assume their relation is linear
$$Y_{i}=\beta_{0}+\beta_{1}X_{i}+\varepsilon_{i}$$
wherein:
- $\beta_{0}$ is the y-intercept
- $\beta_{1}$ is the slope
- $\varepsilon_{i}$ is the error (**noise**)
- $𝔼(𝜖_{i}|𝑋_{i}) = 0$
- $Var(𝜖_{i}|𝑋_{i}) =\sigma^2$
## Simple Linear regression
If params $\beta_{0}\text{ and }\beta_{1}$ are unknown, then the yhave to be estimated such that the **fitted line** is: $$\hat{r}(x)=\beta_{0}+\beta_{1}X$$
predicted values are: $$\hat{Y}_{i}=\hat{r}(X_{i})$$
and residuals:
$$\hat{\epsilon}_{i}=Y_{i}-\hat{Y}_{i}=Y_{i}-(\hat{\beta}_{0}+\hat{\beta}_{1}X_{i})$$
By estimating params and analyzing residuals, lin reg allows understanding and quantification of the relation between variables. We ca nmake predictions based on the fitted model

## Least Squares Estimators
- how to best fit the line to the coordinates
- this one tries to minimize the area between the estimated line and the points.
### Least Square Regression
- minimize Mean Square Error (**MSE**) for residuals
	- $\hat{\epsilon}_{i}=Y_{i}-(\hat{\beta}_{0}+\hat{\beta}_{1}X_{i})$

**more specifically** Minimize Residual Sum of Squares (**RSS**)
$$\min_{\hat{\beta}_0, \hat{\beta}_1} \sum_{i=1}^{n} (y_i - (\hat{\beta}_0 + \hat{\beta}_1 X_i))^2$$

```python

```



```python

```



```python

```



```python

```



```python

```



```python

```



```python

```



```python

```



```python

```