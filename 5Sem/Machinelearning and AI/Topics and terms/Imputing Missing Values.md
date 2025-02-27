### Under [[Data Preprocessing]]
# Dealing with missing data
Samples could be missing one or more values for various reasons.

Most computational tools are unable to handle such missing values, or produce unpredictable result if we simply ignore them
- **Eliminate the samples or features with missing values**
	- ![[MachineLearning AI Modul 6.png]]

**==However, there is a problem when we eliminate rows or columns. What kind of problem? How to solve it?==**

## Impute Shit
- the removal of samples or dropping of entire feature columns is simply not feasible, because **we might lose too much valuable data**
- In this case, we can use different interpolation techniques to estimate the missing values from the other training samples in our dataset
- One of the most common interpolation techniques is mean imputation, where we simply **replace the missing value with the mean value of the entire feature column**

+ If we change **the axis=0 setting to axis=1, we'd calculate the row means**
+ Other options for the strategy parameter are median most_frequent, where **the latter replaces the missing values with the most frequent values**.
+ This is useful for **inputting categorical feature** values, for example, a feature column that stores **an encoding of color names, such as red, green, and blue**