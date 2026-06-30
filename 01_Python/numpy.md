# NumPy

## Key concepts

- ndarray, shape, dtype
- Broadcasting
- Vectorization

## Common operations

```python
import numpy as np

arr = np.array([1, 2, 3])
arr.reshape(3, 1)
arr.mean()
np.dot(a, b)
```

## Notes

<!-- Add your notes here -->
# NumPy Functions — Regularization Lab Notes

| Function | Description | Example |
|---|---|---|
| `np.linspace(start, stop, num)` | Generates `num` evenly spaced values between `start` and `stop` | `X_real = np.linspace(0, 1.0, 100)` |
| `np.sin(x)` | Computes element-wise sine | `Y_real = np.sin(2 * np.pi * X_real)` |
| `np.log1p(x)` | Computes `log(1 + x)`, used to reduce skewness | `train[col] = np.log1p(train[col])` |
| `np.sqrt(x)` | Square root, element-wise | `np.sqrt(mean_squared_error(ytrue, ypredicted))` |
| `np.array(list)` | Creates a NumPy array from a list | `alphas2 = np.array([1e-5, 5e-5, 0.0001, 0.0005])` |
| `.ravel()` | Flattens an array to 1-D | `lr.coef_.ravel()` |
| `.nonzero()` | Returns indices of non-zero elements | `lassoCV.coef_.nonzero()[0]` |
| `np.mean(arr)` | Computes the mean of array elements | `np.mean([1, 2, 3, 4])` → `2.5` |
| `np.std(arr)` | Computes the standard deviation | `np.std([1, 2, 3, 4])` → `1.118` |
| `np.var(arr)` | Computes the variance | `np.var([1, 2, 3, 4])` → `1.25` |
| `np.exp(x)` | Exponential function — used in sigmoid, log-odds | `sigmoid = 1 / (1 + np.exp(-x))` |
| `np.expm1(x)` | Inverse of `log1p` — reverses a log-transform | `original = np.expm1(np.log1p(100))` → `100.0` |
| `np.where(cond, a, b)` | Vectorized if-else condition | `np.where(arr > 0, 1, 0)` → labels positives as 1, rest 0 |
| `np.reshape(arr, shape)` | Reshapes an array | `X = arr.reshape(-1, 1)` → converts 1-D array to a column vector |
| `np.concatenate((a, b))` | Joins arrays along an axis | `np.concatenate((np.array([1,2]), np.array([3,4])))` → `[1 2 3 4]` |
| `np.vstack((a, b))` | Stacks arrays vertically (row-wise) | `np.vstack(([1,2],[3,4]))` → `[[1,2],[3,4]]` |
| `np.hstack((a, b))` | Stacks arrays horizontally (column-wise) | `np.hstack(([1,2],[3,4]))` → `[1 2 3 4]` |
| `np.random.seed(n)` | Sets random seed for reproducibility | `np.random.seed(42)` |
| `np.random.randn(n)` | Generates samples from a standard normal distribution | `noise = np.random.randn(100)` |
| `np.argsort(arr)` | Returns indices that would sort the array | `np.argsort([3,1,2])` → `[1 2 0]` |
| `np.argmax(arr)` | Returns index of the maximum value | `np.argmax([0.1, 0.7, 0.2])` → `1` (predicted class in classification) |
| `np.unique(arr)` | Returns sorted unique elements | `np.unique([1,2,2,3,1])` → `[1 2 3]` |
| `np.zeros(shape)` / `np.ones(shape)` | Creates arrays filled with 0s or 1s | `weights = np.zeros(5)` |
| `np.dot(a, b)` | Matrix/vector dot product | `np.dot([1,2,3], [4,5,6])` → `32` |
| `np.abs(x)` | Element-wise absolute value | `np.abs([-1, -2, 3])` → `[1 2 3]` |
| `np.clip(a, min, max)` | Clips values to a given range | `np.clip([-1, 5, 10], 0, 8)` → `[0 5 8]` |
