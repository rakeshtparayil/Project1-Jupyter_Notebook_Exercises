
# Common Seaborn Plot Types and Their Use Cases

## 1. Line Plot (`sns.lineplot`)
**Use Case**:
- Plotting trends over **continuous variables** (e.g., time series).
- Comparing changes across multiple categories.

**Example**:
```python
sns.lineplot(data=your_data, x='time', y='value', hue='category')
```

---

## 2. Bar Plot (`sns.barplot`)
**Use Case**:
- Comparing **aggregated values** across categories (e.g., means, sums).
- Shows relationships between a categorical variable and a numeric variable.

**Example**:
```python
sns.barplot(data=your_data, x='category', y='value', hue='sub_category')
```

---

## 3. Count Plot (`sns.countplot`)
**Use Case**:
- Visualizing the **frequency** of categories.

**Example**:
```python
sns.countplot(data=your_data, x='category', hue='sub_category')
```

---

## 4. Histogram (`sns.histplot`)
**Use Case**:
- Analyzing the **distribution** of a single numeric variable.

**Example**:
```python
sns.histplot(data=your_data, x='numeric_variable', bins=20, kde=True)
```

---

## 5. KDE Plot (`sns.kdeplot`)
**Use Case**:
- Visualizing a **smoothed distribution** of data.
- Alternative to histograms.

**Example**:
```python
sns.kdeplot(data=your_data, x='numeric_variable', hue='category', fill=True)
```

---

## 6. Pair Plot (`sns.pairplot`)
**Use Case**:
- Exploring **pairwise relationships** between multiple numeric variables.

**Example**:
```python
sns.pairplot(data=your_data, hue='category', diag_kind='kde')
```

---

## 7. Box Plot (`sns.boxplot`)
**Use Case**:
- Summarizing the **distribution** of a numeric variable for different categories.
- Identifying **outliers** and comparing medians.

**Example**:
```python
sns.boxplot(data=your_data, x='category', y='numeric_variable', hue='sub_category')
```

---

## 8. Violin Plot (`sns.violinplot`)
**Use Case**:
- Combines a box plot and KDE plot to show **distribution** and **variability**.

**Example**:
```python
sns.violinplot(data=your_data, x='category', y='numeric_variable', hue='sub_category', split=True)
```

---

## 9. Heatmap (`sns.heatmap`)
**Use Case**:
- Visualizing **correlations** or **matrices** with color coding.

**Example**:
```python
sns.heatmap(data=correlation_matrix, annot=True, cmap='coolwarm')
```

---

## 10. Scatter Plot (`sns.scatterplot`)
**Use Case**:
- Visualizing the relationship between **two numeric variables**.

**Example**:
```python
sns.scatterplot(data=your_data, x='x_variable', y='y_variable', hue='category')
```

---

## 11. Joint Plot (`sns.jointplot`)
**Use Case**:
- Examining the **relationship** between two variables along with their **distributions**.

**Example**:
```python
sns.jointplot(data=your_data, x='x_variable', y='y_variable', kind='reg')
```

---

## 12. Displot (`sns.displot`)
**Use Case**:
- Plotting distributions for one or two variables with flexible faceting.

**Example**:
```python
sns.displot(data=your_data, x='numeric_variable', col='category', kde=True)
```

---

## 13. Swarm Plot (`sns.swarmplot`)
**Use Case**:
- Visualizing the **distribution** of points for small datasets with less overlap.

**Example**:
```python
sns.swarmplot(data=your_data, x='category', y='numeric_variable', hue='sub_category')
```

---

### Choosing the Right Plot:
- **Comparison across categories**: `barplot`, `countplot`.
- **Distributions**: `histplot`, `kdeplot`, `boxplot`, `violinplot`.
- **Relationships**: `scatterplot`, `jointplot`, `pairplot`.
- **Time-series or trends**: `lineplot`.
- **Correlations**: `heatmap`.
