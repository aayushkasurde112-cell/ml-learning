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

# Scikit-learn Functions — Regularization Lab Notes

| Function | Description | Example |
|---|---|---|
| `PolynomialFeatures(degree)` | Generates polynomial and interaction features up to a given degree | `pf = PolynomialFeatures(20); X_poly = pf.fit_transform(X_data)` |
| `LinearRegression()` | Ordinary least squares regression model | `lr = LinearRegression().fit(X_poly, Y_data)` |
| `Ridge(alpha)` | L2-regularized regression; shrinks coefficients to reduce overfitting | `rr = Ridge(alpha=0.001).fit(X_poly, Y_data)` |
| `Lasso(alpha)` | L1-regularized regression; can shrink coefficients to exactly zero (feature selection) | `lassor = Lasso(alpha=0.0001).fit(X_poly, Y_data)` |
| `RidgeCV(alphas, cv)` | Ridge regression with built-in cross-validation to pick the best alpha | `ridgeCV = RidgeCV(alphas=[0.1,1,10], cv=4).fit(X_train, y_train)` |
| `LassoCV(alphas, max_iter, cv)` | Lasso regression with built-in cross-validation to pick the best alpha | `lassoCV = LassoCV(alphas=alphas2, max_iter=50000, cv=3).fit(X_train, y_train)` |
| `ElasticNetCV(alphas, l1_ratio)` | Combines L1 + L2 penalties with cross-validation to tune both | `enCV = ElasticNetCV(alphas=alphas2, l1_ratio=np.linspace(0.1,0.9,9)).fit(X_train, y_train)` |
| `SGDRegressor(penalty, alpha, eta0)` | Linear model trained via stochastic gradient descent; needs feature scaling | `SGD = SGDRegressor(penalty='l2', alpha=0.001, eta0=1e-7).fit(X_train_scaled, y_train)` |
| `MinMaxScaler()` | Scales features to a [0, 1] range | `scaler = MinMaxScaler(); X_scaled = scaler.fit_transform(X_train)` |
| `train_test_split(X, y, test_size, random_state)` | Splits data into training and test sets | `train, test = train_test_split(data, test_size=0.3, random_state=42)` |
| `mean_squared_error(y_true, y_pred)` | Computes the mean squared error between actual and predicted values | `mse = mean_squared_error(y_test, y_pred)` |
| `model.fit(X, y)` | Trains a model on the given data | `lr.fit(X_train, y_train)` |
| `model.predict(X)` | Generates predictions from a trained model | `y_pred = lr.predict(X_test)` |
| `model.coef_` | Returns the learned coefficients of a linear model | `lr.coef_.ravel()` |
| `StandardScaler()` | Standardizes features by removing the mean and scaling to unit variance | `scaler = StandardScaler(); X_scaled = scaler.fit_transform(X_train)` |
| `LabelEncoder()` | Encodes categorical labels into integers | `le = LabelEncoder(); y_encoded = le.fit_transform(y)` |
| `OneHotEncoder()` | One-hot encodes categorical features (alternative to `pd.get_dummies`) | `ohe = OneHotEncoder(); X_cat = ohe.fit_transform(X[['Neighborhood']])` |
| `LogisticRegression()` | Linear model for classification tasks | `clf = LogisticRegression().fit(X_train, y_train)` |
| `DecisionTreeClassifier()` / `DecisionTreeRegressor()` | Tree-based model for classification or regression | `tree = DecisionTreeClassifier(max_depth=5).fit(X_train, y_train)` |
| `RandomForestClassifier()` / `RandomForestRegressor()` | Ensemble of decision trees for classification or regression | `rf = RandomForestRegressor(n_estimators=100).fit(X_train, y_train)` |
| `KNeighborsClassifier()` | Classification based on nearest neighbors | `knn = KNeighborsClassifier(n_neighbors=5).fit(X_train, y_train)` |
| `SVC()` / `SVR()` | Support Vector Machine for classification/regression | `svc = SVC(kernel='rbf').fit(X_train, y_train)` |
| `KMeans(n_clusters)` | Unsupervised clustering algorithm | `km = KMeans(n_clusters=3).fit(X)` |
| `PCA(n_components)` | Dimensionality reduction via Principal Component Analysis | `pca = PCA(n_components=2); X_reduced = pca.fit_transform(X)` |
| `GridSearchCV(estimator, param_grid, cv)` | Exhaustive search over hyperparameters with cross-validation | `gs = GridSearchCV(Ridge(), {'alpha':[0.1,1,10]}, cv=5).fit(X_train, y_train)` |
| `cross_val_score(estimator, X, y, cv)` | Evaluates a model using k-fold cross-validation | `scores = cross_val_score(lr, X, y, cv=5)` |
| `accuracy_score(y_true, y_pred)` | Computes classification accuracy | `accuracy_score(y_test, y_pred)` |
| `confusion_matrix(y_true, y_pred)` | Computes the confusion matrix for classification results | `confusion_matrix(y_test, y_pred)` |
| `classification_report(y_true, y_pred)` | Prints precision, recall, F1-score per class | `print(classification_report(y_test, y_pred))` |
| `r2_score(y_true, y_pred)` | Computes the R² (coefficient of determination) score | `r2_score(y_test, y_pred)` |
| `Pipeline(steps)` | Chains preprocessing and modeling steps into one estimator | `pipe = Pipeline([('scaler', MinMaxScaler()), ('model', Ridge())])` |


