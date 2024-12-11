
# Step 1: Data Cleaning and Analysis with Pandas

### Import Necessary Libraries
```python
import numpy as np
import pandas as pd
```

---

### Load and Explore the Dataset
```python
movies = pd.read_csv('movies_2.csv')  # Load the CSV file
movies.head(5)  # Print the first 5 rows
movies.shape  # Get the total rows and columns
movies.isnull().sum()  # Find the null values in the dataset
movies.columns  # Print the column headers
```

---

### Handle Null Values
```python
null_rows = movies[movies.isnull().any(axis=1)]  # Print all rows with null values
movies.drop('Summary', axis='columns', inplace=True)  # Drop a specific column permanently
```

---

### Clean Column Names
```python
movies.columns = movies.columns.str.lower().str.replace(' ', '_')  # Convert column names to lowercase and remove spaces
```

---

### Remove Rows and Columns
```python
movies = movies.drop(movies.index[-1])  # Remove the last row
movies.dropna(axis=0)  # Remove rows with NaN values
movies.dropna(axis=1)  # Remove columns with NaN values
```

---

### Fill Missing Values
```python
movies.fillna({'rating': movies['rating'].median()}, inplace=True)  # Fill NaN values with the median of the 'rating' column
```

---

### Convert Data Types
```python
movies['budget'] = movies['budget'].astype(int)  # Convert the 'budget' column to integer
movies['release_date'] = pd.to_datetime(movies['release_date'])  # Convert 'release_date' to datetime
```

---

### Filter Data
```python
movies_updated = movies[(movies['rating'] > 7) & (movies['gross'] > 50000000)]  # Filter movies with rating > 7 and gross > 50M
comedy_movies = movies[movies['genre'] == 'Comedy']  # Filter movies by genre (Comedy)
```

---

### Sort Data
```python
movies_top5 = movies.sort_values('budget', ascending=False).head(5)  # Sort by budget and select the top 5
```

---

### Count and Aggregate
```python
genre_count = movies['genre'].value_counts()  # Count values in the 'genre' column
movies_release = movies[movies['release_date'].dt.year > 1999]  # Filter movies released after 1999
```

---

### Find Frequent and Statistical Values
```python
most_freq_mpaa = freq.idxmax()  # Find the most frequent value
least_freq_mpaa = freq.idxmin()  # Find the least frequent value
average = df['column'].mean()  # Calculate the average of a column
max_value = df['column'].max()  # Find the maximum value in a column
```

---

### Query Specific Data
```python
df.loc[df['column_name'] == 'some_value']  # Get details of rows where a column matches a specific value
total_benefits = sal.loc[sal['EmployeeName'] == 'JOSEPH DRISCOLL', ['TotalPayBenefits', 'JobTitle']]  # Extract specific values
```

---

### Aggregate and Group Data
```python
most_common = sal['JobTitle'].value_counts()  # Count occurrences in a column
most_common.head(5)  # Display the top 5 most common values
grouped_year = mkt_data.groupby(mkt_data['transaction_date'].dt.year)  # Group data by year
yearly_sums = grouped_year['revenue'].sum()  # Calculate yearly revenue sums
```
