# Data Analysis with Python
## Cheat Sheet: Exploratory Data Analysis

### Complete dataframe correlation
- **Description:** Correlation matrix created using all the attributes of the dataset.
- **Code Example:**
  ```python
  df.corr()
  ```

### Specific Attribute Correlation
- **Description:** Correlation matrix created using specific attributes of the dataset.
- **Code Example:**
  ```python
  df[['attribute1', 'attribute2', ...]].corr()
  ```

### Scatter Plot
- **Description:** Create a scatter plot using the data points of the dependent variable along the x-axis and the independent variable along the y-axis.
- **Code Example:**
  ```python
  from matplotlib import pyplot as plt
  plt.scatter(df[['attribute_1']], df[['attribute_2']])
  ```

### Regression Plot
- **Description:** Uses the dependent and independent variables in a Pandas data frame to create a scatter plot with a generated linear regression line for the data.
- **Code Example:**
  ```python
  import seaborn as sns
  sns.regplot(x='attribute_1', y='attribute_2', data=df)
  ```

### Box Plot
- **Description:** Create a box-and-whisker plot that uses the pandas dataframe, the dependent,, and the independent variables.
- **Code Example:**
  ```python
  import seaborn as sns
  sns.boxplot(x='attribute_1', y='attribute_2', data=df)
  ```

### Grouping by Attributes
- **Description:** Create a group of different attributes of a dataset to create a subset of the data.
- **Code Example:**
  ```python
  df_group = df[['attribute_1', 'attribute_2', ...]]
  ```

### GroupBy Statements
- **Description:** 
  - **a)** Group the data by different categories of an attribute, displaying the average value of numerical attributes with the same category.
  - **b)** Group the data by different categories of multiple attributes, displaying the average value of numerical attributes with the same category.
- **Code Example:**
  ```python
  # a) Group by one attribute
  df_group = df_group.groupby(['attribute_1'], as_index=False).mean()
  
  # b) Group by multiple attributes
  df_group = df_group.groupby(['attribute_1', 'attribute_2'], as_index=False).mean()
  ```

### Pivot Tables
- **Description:** Create Pivot tables for better representation of data based on parameters.
- **Code Example:**
  ```python
  grouped_pivot = df_group.pivot(index='attribute_1', columns='attribute_2')
  ```

### Pseudocolor Plot
- **Description:** Create a heatmap image using a PseudoColor plot (or pcolor) using the pivot table as data.
- **Code Example:**
  ```python
  from matplotlib import pyplot as plt
  plt.pcolor(grouped_pivot, cmap='RdBu')
  ```

### Pearson Coefficient and p-value
- **Description:** Calculate the Pearson Coefficient and p-value of a pair of attributes.
- **Code Example:**
  ```python
  from scipy import stats
  pearson_coef, p_value = stats.pearsonr(df['attribute_1'], df['attribute_2'])
  ```

---

