# Pandas Library

Pandas is a powerful and flexible data analysis and manipulation library for Python. It provides data structures and functions needed to work seamlessly with structured data, making it essential for data science, engineering, and various analytical tasks.

## Key Concepts

### 1. **DataFrame**

- **Overview**: The primary data structure in Pandas, akin to a table in a relational database or an Excel spreadsheet.
- **Features**:
  - Two-dimensional, size-mutable, and potentially heterogeneous tabular data.
  - Labeled axes (rows and columns).
  - Indexing, selection, and filtering capabilities.
- **Example**:
  ```python
  import pandas as pd

  data = {'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35]}
  df = pd.DataFrame(data)
  print(df)
  ```

### 2. **Series**

- **Overview**: A one-dimensional labeled array capable of holding any data type.
- **Features**:
  - Acts as a single column in a DataFrame.
  - Supports various operations like mathematical operations, filtering, and alignment.
- **Example**:
  ```python
  import pandas as pd

  s = pd.Series([1, 2, 3, 4, 5])
  print(s)
  ```

### 3. **Indexing and Selection**

- **Overview**: Accessing data in DataFrames or Series using labels, indices, or conditions.
- **Features**:
  - `.loc[]`: Label-based indexing.
  - `.iloc[]`: Integer-based indexing.
  - Conditional selection using Boolean arrays.
- **Example**:
  ```python
  import pandas as pd

  df = pd.DataFrame({
      'A': [1, 2, 3],
      'B': [4, 5, 6],
      'C': [7, 8, 9]
  })

  # Select column 'A'
  print(df['A'])

  # Select row where A > 1
  print(df[df['A'] > 1])
  ```

### 4. **Data Manipulation**

- **Overview**: Functions and methods to manipulate data in DataFrames and Series.
- **Features**:
  - **Adding/Removing Columns**: Easily add or remove columns.
  - **Missing Data Handling**: Detect and handle missing data using methods like `.isnull()` and `.fillna()`.
  - **Aggregation**: Summarize data using `.groupby()`, `.agg()`, etc.
- **Example**:
  ```python
  import pandas as pd

  df = pd.DataFrame({
      'A': [1, 2, None],
      'B': [4, None, 6],
      'C': [7, 8, 9]
  })

  # Fill missing values with 0
  df_filled = df.fillna(0)
  print(df_filled)

  # Group by column 'A' and compute sum
  grouped = df.groupby('A').sum()
  print(grouped)
  ```

### 5. **Data Input/Output**

- **Overview**: Pandas provides robust tools for reading from and writing to various file formats.
- **Supported Formats**:
  - **CSV**: `pd.read_csv()`, `df.to_csv()`
  - **Excel**: `pd.read_excel()`, `df.to_excel()`
  - **JSON**: `pd.read_json()`, `df.to_json()`
  - **SQL**: `pd.read_sql()`, `df.to_sql()`
- **Example**:
  ```python
  import pandas as pd

  # Reading data from a CSV file
  df = pd.read_csv('data.csv')
  print(df.head())

  # Writing data to an Excel file
  df.to_excel('output.xlsx', index=False)
  ```
