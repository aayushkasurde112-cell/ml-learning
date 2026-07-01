# Matplotlib

## Key concepts

- pyplot vs object-oriented API
- subplots, legends, labels

## Common operations

```python
import matplotlib.pyplot as plt

plt.figure(figsize=(8, 4))
plt.plot(x, y)
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Title")
plt.show()
```

## Notes

<!-- Add your notes here -->
# Matplotlib & Seaborn Functions — Regularization Lab Notes

| Function | Description | Example |
|---|---|---|
| `%matplotlib inline` | Jupyter magic command to render plots inline | `%matplotlib inline` |
| `plt.plot(x, y, ...)` | Plots a line or scatter (with `ls='', marker='o'`) | `plt.plot(X_data, Y_data, marker='o', ls='')` |
| `plt.legend()` | Displays the legend on the plot | `plt.legend()` |
| `plt.gca()` | Gets the current Axes object | `ax = plt.gca()` |
| `ax.set(xlabel=, ylabel=, title=, xlim=, ylim=)` | Sets multiple Axes properties in one call | `ax.set(xlabel='x data', ylabel='y data')` |
| `data.set_index('x')['y'].plot(ls='', marker='o', label='data')` | Sets `'x'` column as index, selects `'y'` column, then plots it as a scatter plot — `ls=''` removes the line, `marker='o'` adds circle markers, `label='data'` sets the legend label | `x = data.set_index('x')['y'].plot(ls='', marker='o', label='data')` |
| `plt.figure(figsize=(w,h))` | Creates a new figure with a custom size | `plt.figure(figsize=(6,6))` |
| `plt.axes()` | Creates/returns an Axes object | `ax = plt.axes()` |
| `plt.subplots(nrows, ncols, figsize=)` | Creates a grid of subplots | `fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(10,5))` |
| `df[col].hist(ax=)` | Plots a histogram directly from a pandas Series | `train[field].hist(ax=ax_before)` |
| `fig.suptitle('text')` | Adds a title above all subplots | `fig.suptitle('Field "{}"'.format(field))` |
| `ax.twinx()` | Creates a second y-axis sharing the same x-axis | `ax2 = ax1.twinx()` |
| `ax.set_ylim(min, max)` | Sets y-axis limits | `ax1.set_ylim(-2e14, 2e14)` |
| `ax.get_legend_handles_labels()` | Retrieves handles/labels for manual legend merging | `h1, l1 = ax1.get_legend_handles_labels()` |
| `ax.set_xticks(range(n))` | Sets custom tick positions on x-axis | `ax1.set_xticks(range(len(lr.coef_)))` |
| `plt.legend(frameon=True)` | Legend with a visible border | `leg = plt.legend(frameon=True)` |
| `leg.get_frame().set_edgecolor()` | Sets legend box border color | `leg.get_frame().set_edgecolor('black')` |
| `leg.get_frame().set_linewidth()` | Sets legend box border width | `leg.get_frame().set_linewidth(1.0)` |
| `sns.set_style('white')` | Sets the Seaborn plot style/theme | `sns.set_style('white')` |
| `sns.set_context('talk')` | Adjusts font/element scaling for context | `sns.set_context('talk')` |
| `sns.set_palette('dark')` | Sets the Seaborn color palette | `sns.set_palette('dark')` |
| `sns.color_palette()` | Returns list of current palette colors | `colors = sns.color_palette()` |
| `plt.scatter(x, y, c=labels)` | Scatter plot, useful for visualizing classes/clusters | `plt.scatter(X[:,0], X[:,1], c=y)` |
| `plt.bar()` / `plt.barh()` | Bar charts, e.g. for feature importance | `plt.barh(feature_names, importances)` |
| `plt.imshow()` | Displays images or heatmaps (e.g. confusion matrix) | `plt.imshow(conf_matrix, cmap='Blues')` |
| `plt.colorbar()` | Adds a color scale bar next to a heatmap | `plt.imshow(corr_matrix); plt.colorbar()` |
| `plt.savefig('file.png')` | Saves the current figure to disk | `plt.savefig('output.png', dpi=300)` |
| `plt.tight_layout()` | Auto-adjusts subplot spacing to avoid overlap | `plt.tight_layout()` |
| `plt.xlabel()` / `plt.ylabel()` / `plt.title()` | Sets axis labels and title individually | `plt.xlabel('Predicted'); plt.title('Results')` |
| `plt.grid(True)` | Adds a grid to the plot | `plt.grid(True)` |
| `sns.heatmap(df.corr(), annot=True)` | Visualizes a correlation matrix as a heatmap | `sns.heatmap(df.corr(), annot=True, cmap='coolwarm')` |
| `sns.pairplot(df)` | Pairwise scatter plots across all features | `sns.pairplot(df[['SalePrice','GrLivArea','OverallQual']])` |
| `sns.boxplot()` | Box plot for distribution/outlier checks | `sns.boxplot(x='OverallQual', y='SalePrice', data=df)` |
| `sns.histplot()` / `sns.distplot()` | Histogram/density plot of a distribution | `sns.histplot(df['SalePrice'], kde=True)` |
| `sns.lineplot()` | Line plot with confidence interval support | `sns.lineplot(x='YrSold', y='SalePrice', data=df)` |
