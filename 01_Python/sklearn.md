# Scikit-learn

## Key concepts

- Estimator API: `fit`, `predict`, `transform`
- train_test_split
- Pipeline, cross_val_score

## Common operations

```python
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = LogisticRegression()
model.fit(X_train, y_train)
model.score(X_test, y_test)
```

## Notes

<!-- Add your notes here -->
