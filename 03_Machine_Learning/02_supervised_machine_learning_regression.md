# Supervised Machine Learning: Regression

**IBM Machine Learning Professional Certificate — Course 2**

## Topics

- Linear regression
- Error metrics (MSE, RMSE, MAE, R²)
- Train/test splits
- Regularization (Ridge, LASSO, Elastic Net)
- Model selection and evaluation

## Notes

<!-- Add your notes here -->
- Regularization (Ridge, LASSO, Elastic Net)


Bias is like consistently missing the bullseye on a target but always hitting the same wrong spot. It means the model is too simple or rigid, so it consistently makes the same kind of error—this is called underfitting.
Variance, on the other hand, is like trying to hit the bullseye but your shots scatter all over the target, sometimes close, sometimes far. This means the model is too sensitive to the training data and changes a lot with small differences—this is called overfitting.

In L1(Lasso) & L2(Ridge) regularizer, a regularization term is added to loss function, in order to penalize learned parameters to avoid overfitting. There are L1 regularizer, L2 regularizer and a combined regularizer:  

Ridge regression, i.e. L2 regularizer, adds "squared magnitude" of coefficient as penalty term to the loss function.
Lasso Regression (Least Absolute Shrinkage and Selection Operator), i.e. L1 regularizar, adds "absolute value of magnitude" of coefficient as penalty term to the loss function.
Elastic Net: Elastic Net is a middle ground between Ridge Regression and Lasso Regression by adding a mix ratio of L1 and L2 term.
The key difference between these techniques is that Lasso shrinks the less important feature’s coefficient to zero thus, removing some feature altogether. So, this works well for feature selection in case we have a huge number of features. It is useful if our concern is interpretibility

In practice, Ridge regression is a good default. It is useful if our concern is computational time. If you suspect that only a few features are actually useful, then use Lasso or Elastic Net (Elastic Net is more perferable).
(so basically regularization is a technique to be used to deal with over fitting data. it penalises the overfitting data and there are two ways to do it ridge and lasso regression)
