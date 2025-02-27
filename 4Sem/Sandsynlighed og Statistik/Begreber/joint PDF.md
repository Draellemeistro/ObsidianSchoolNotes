
> [!NOTE] Intro
> We say that **X** and **Y** are jointly **continuous**, if there exists a function **f(x,y)** defined for all real **x** and **y**, having the property that for every set **C** in the 2-dimensional plane
> $$P\{(X,Y)\in C\}=\int \,\int_{(x,y)\in C}  \, f(x,y)dx dy $$
> 
> ![[Pasted image 20240602162431.png]]
> 
> **f(x,y)** is called **joint probability density function**
> $$P\{X\in [a,b],Y\in [c,d]\}=\int_{c}^{d} \int_{a}^{b}  \,f(x,y) dx  \, dy $$
> 
> **joint PDF -->marginal [[Probability Density Function (PDF)|PDF]]**
> the **marginal PDFs** are obtained by integrating out the variables that are not of interest:
> $$f_{X}(x)=\int_{-\infty}^{\infty} f(x,y) \, dy $$
> $$f_{Y}(y)=\int_{-\infty}^{\infty}  f(x,y)\, dx $$

