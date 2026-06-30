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
# Pandas Functions — Regularization Lab Notes

| Function | Description | Example |
|---|---|---|
| `pd.read_csv(url)` | Loads a dataset from a CSV file or URL into a DataFrame | `data = pd.read_csv("data.csv")` |
| `df.head(n)` | Previews the first `n` rows (default 5) | `data.head(10)` |
| `df.set_index('col')` | Sets a column as the DataFrame index | `data.set_index('x')['y'].plot()` |
| `pd.get_dummies(df, drop_first=True)` | One-hot encodes categorical columns | `data = pd.get_dummies(data, drop_first=True)` |
| `df.dtypes` | Returns the data type of each column | `mask = data.dtypes == float` |
| `df.columns[mask]` | Boolean-mask filtering of columns | `float_cols = data.columns[mask]` |
| `df.skew()` | Computes skewness of numeric columns | `skew_vals = train[float_cols].skew()` |
| `.sort_values(ascending=False)` | Sorts a Series/DataFrame by value | `skew_vals.sort_values(ascending=False)` |
| `.to_frame()` | Converts a Series into a DataFrame | `skew_vals.sort_values().to_frame()` |
| `.rename(columns={...})` | Renames columns | `.rename(columns={0:'Skew'})` |
| `.query('expr')` | Filters rows using a string expression | `.query('abs(Skew) > 0.75')` |
| `df.apply(func)` | Applies a function along an axis | `train[field].apply(np.log1p)` |
| `.applymap(func)` | Applies a function element-wise to entire DataFrame | `coefficients.applymap(abs)` |
| `pd.options.mode.chained_assignment` | Setting to suppress `SettingWithCopyWarning` | `pd.options.mode.chained_assignment = None` |
| `pd.DataFrame()` | Creates a new (empty) DataFrame | `coefficients = pd.DataFrame()` |
| `df.describe()` | Generates summary statistics | `coefficients.describe()` |
| `pd.Series(data, index=labels)` | Creates a labeled Series | `pd.Series(rmse_vals, index=labels)` |
| `.index.tolist()` | Converts an Index object to a list | `skew_cols.index.tolist()` |
| `df.isnull().sum()` | Counts missing values per column | `df.isnull().sum()` → shows NaN count per column |
| `df.fillna(value)` | Fills missing values | `df['Age'].fillna(df['Age'].mean(), inplace=True)` |
| `df.dropna()` | Drops rows/columns with missing values | `df.dropna(subset=['SalePrice'])` |
| `df.corr()` | Computes pairwise correlation between columns | `df.corr()['SalePrice'].sort_values(ascending=False)` |
| `df.groupby('col')` | Groups data by a column for aggregation | `df.groupby('Neighborhood')['SalePrice'].mean()` |
| `df.value_counts()` | Counts frequency of unique values | `df['HouseStyle'].value_counts()` |
| `pd.concat([df1, df2])` | Concatenates DataFrames/Series | `pd.concat([train, test], axis=0)` |
| `df.merge(other, on='key')` | SQL-style join of two DataFrames | `orders.merge(customers, on='customer_id')` |
| `df.sample(n)` | Randomly samples `n` rows | `df.sample(5, random_state=42)` |
| `df.astype(dtype)` | Casts column(s) to a different data type | `df['Year'] = df['Year'].astype(int)` |
| `df.drop(columns=[...])` | Drops specified columns/rows | `df.drop(columns=['Id'])` |
| `df.duplicated()` | Flags duplicate rows | `df[df.duplicated()]` |
| `df.pivot_table()` | Creates a spreadsheet-style pivot table | `df.pivot_table(values='SalePrice', index='YrSold', aggfunc='mean')` |
| `df.shape` | Returns (rows, columns) tuple | `print(df.shape)` → `(1460, 81)` |
| `df.info()` | Summary of DataFrame (dtypes, non-null counts) | `df.info()` |
| `df.copy()` | Creates a deep copy of a DataFrame | `train_copy = train.copy()` |
