# 🤖 Machine Learning Fundamentals

## 1. The Bias-Variance Tradeoff

The fundamental problem in Supervised Learning.

### A. Bias (Underfitting)
* **Definition:** The error introduced by approximating a real-world problem with a too-simple model.
* **Symptoms:** High error on Training Data AND Testing Data.
* **Example:** Fitting a straight line (Linear Regression) to a complex curved pattern.
* **Fix:** Use a more complex model, add more features.

### B. Variance (Overfitting)
* **Definition:** The error introduced by the model being too sensitive to small fluctuations (noise) in the training set.
* **Symptoms:** Low error on Training Data but **High error** on Testing Data. The model "memorized" the training set but failed to generalize.
* **Example:** A Decision Tree that grows until every single leaf has 1 sample.
* **Fix:** Get more data, simplify the model, use regularization, prune trees.

### Summary Visual
* **Underfitting:** High Bias, Low Variance. (Model is "Too Dumb").
* **Overfitting:** Low Bias, High Variance. (Model is "Too Smart" / Memorizing).
* **Ideal Model:** Balance between the two (Low Bias, Low Variance).