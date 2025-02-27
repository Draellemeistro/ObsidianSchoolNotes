
> [!NOTE] Terms
> - True Positive, True Negative, False Positive, False Negative
> - Confusion Matrix
> - **Metrics:**
> 	- Precision
> 	- Recall
> 	- F1-score



# Visualization
## Confusion Matrix

|              | Predicted 0 | Predicted 1 |
| ------------ | ----------- | ----------- |
| **Actual 0** | TN          | FP          |
| **Actual 1** | FN          | TP          |
### True Positive
acttual test result is **positive**, predicted as **positive**
### True Negative
acttual test result is **negative**, predicted as **negative**
### False Positve
acttual test result is **negative**, predicted as **positive**
### False Negative
acttual test result is **positive**, predicted as **negative**
# Metrics

> [!NOTE] **Precision**
> $$\text{Precision}=\frac{TP}{TP+FP}$$
> The percentage of positive out of all the predicted positives. **For a perfect model precision should be 1**

> [!NOTE] **Recall**
> $$\text{Recall}=\frac{TP}{TP+FN}$$
> The percentage of correct positive predictions by the model of all the actual positives. **Ideally Recall should be 1for a perfect model.**

> [!NOTE] **F1-score**
> $$\text{F1-score}=2\times \frac{\text{Precision}\times \text{Recall}}{\text{Precision}+ \text{Recall}}$$
> F1 score takes into account both precision and recall. it is the harmonic mean of both precision and recall.

