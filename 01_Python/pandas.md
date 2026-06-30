# Pandas

## Key concepts

- Series vs DataFrame
- Indexing: `loc`, `iloc`
- GroupBy, merge, concat

## Common operations

```python
import pandas as pd

data = pd.read_csv("file.csv")
data.head()
data.isnull().sum()
data.groupby("col").mean()
```

## Notes

<!-- Add your notes here -->
```
data = pd.read_csv("file.csv")
```
I'll use this to read a csv file
```
data.head()
```
I'll use this to access the first 5 rows of the data set
