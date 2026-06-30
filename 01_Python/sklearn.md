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

# 1. Split data into training and testing sets (80/20 split)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 2. Scale features (crucial for Logistic Regression convergence)
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

# 3. Initialize and train the model
model = LogisticRegression()
model.fit(X_train_scaled, y_train)

# 4. Evaluate the accuracy score on the test sets
accuracy = model.score(X_test_scaled, y_test)
print(f"Test Accuracy: {accuracy:.4f}")

```

## Notes

<!-- Add your notes here -->
Recursive Feature Elemination

```python
# Initialize the RFE selector with your base estimator (e.g., est)
rfeMod = RFE(estimator=est, n_features_to_select=5)

# Fit the selector and transform the datasets to keep only top 5 features
X_train_selected = rfeMod.fit_transform(X_train, y_train)
X_test_selected = rfeMod.transform(X_test)

# Train the base model on the newly selected features
est.fit(X_train_selected, y_train)

# Predict the expected values using the trained model
y_predict = est.predict(X_test_selected)

```


