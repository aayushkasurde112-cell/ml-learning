# Pandas

## Key concepts

- Series vs DataFrame
- Indexing: `loc`, `iloc`
- GroupBy, merge, concat

## Common operations

```python
import pandas as pd

df = pd.read_csv("data.csv")
df.head()
df.isnull().sum()
df.groupby("col").mean()
```

## Notes

<!-- Add your notes here -->
