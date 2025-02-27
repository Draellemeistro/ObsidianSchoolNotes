
> [!NOTE] **Parameters** vs **[[Hyperparameter Tuning|Hyperparameters]]**
> - **Parameters:** *something that is learned during the ML process*
> 	- Weights
> 	- Bias
> - **Hyperparameters:** *Manually specified*
> 	- Learning Rate
> 	- Number of layers
> 	- Neurons in each layer
> 	- epochs

> [!NOTE]  Diagnosing bias and variance problems with learning curves
> ![[image_Hyperparameter Tuning-3.png]]
# stuff

## Holdout Method
![[image_Hyperparameter Tuning.png]]

> [!NOTE] **Weakness** of the holdout method
> A disadvantage of the holdout method is that **the performance estimate may be very sensitive to how we partition the training set into the training and validation subsets**; the estimate will vary for different samples of the data

## K-Fold Cross-Validation
![[image_Hyperparameter Tuning-1.png]]

## Nested Cross-Validation
![[image_Hyperparameter Tuning-2.png]]

# [[Performance Metrics]] (*for evaluation*)

> [!NOTE] **Performance Metrics**
> - Precision
> - Recall
> - F-1-score
> - Confusion matrix


