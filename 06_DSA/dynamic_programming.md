# Dynamic Programming

## Patterns

- 1D DP (climbing stairs, house robber)
- 2D DP (grid paths, LCS)
- Knapsack

## Template

```python
def dp(nums):
    n = len(nums)
    dp = [0] * (n + 1)
    for i in range(1, n + 1):
        dp[i] = # recurrence
    return dp[n]
```

## Notes

<!-- Add your notes here -->
