![[image_overfitting and underfitting.png]]

> [!NOTE] **Overfitting**
> Occurs in ML when a model learns the training data **too well**, capturing not only underlying patterns but also the **noise** and **irrelevant details** (*like outliers*) in the dataset. As a result, the model performs very well on the training data **but fails to generalize to new, unseen data.**
> 
> **WE WANT TO GENERALIZE, NOT MEMORIZE**


> [!NOTE] **Underfitting**
> Model is too simple to reflect the complexity of the training data. (**think:** *linear regression on nonlinear data... oof*)

# Overcoming the problems from shit fits
## General stuff

## Overfitting

- **Collect more training examples**
  ![[image_overfitting and underfitting-1.png]]
- (at least in [[logistic regression]]) **regularization**
  ![[image_logistic regression-6.png]]
- 


## Underfitting
- Increase model complexity how??
- Training the model for a longer period of time (more epochs) to reduce the error
- Increasing the number of features
- improve the learning algorithm
- increase training data size
- 