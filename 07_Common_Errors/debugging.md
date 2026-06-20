# Debugging Common Errors

## Shape mismatch

```
ValueError: shapes (n,) and (m,) not aligned
```

**Fix:** Check `.shape`, use `.reshape(-1, 1)` or `np.newaxis`.

## NaN in data

```
Input contains NaN
```

**Fix:** `df.dropna()` or `df.fillna()`.

## Train/test leakage

**Fix:** Fit scalers and encoders only on training data.

## Notes

<!-- Log errors you encounter and how you fixed them -->
