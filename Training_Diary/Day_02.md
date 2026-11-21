# Day 02 – Data Cleaning

## Topics Covered

- Data cleaning and why it is important
- Missing values and methods to handle them (remove, mean, median, mode)
- Duplicate records
- Standardizing text values and removing extra spaces
- Outlier detection using boxplots and the IQR method
- Verifying and saving cleaned data

## Practice Tasks and Code

## Loading the Dataset

```python
from google.colab import drive
drive.mount('/content/drive')
```

```python
import pandas as pd

df = pd.read_csv("/content/drive/MyDrive/student_dataset.csv")
```

```python
df.head()
```

## Inspecting the Dataset

```python
df.info()
```

```python
df.describe()
```

## Identifying Missing Values

```python
df.isnull()
```

```python
df.isnull().sum()
```

```python
df[df.isnull().any(axis=1)]
```

## Handling Missing Values

```python
# To remove rows this command can be used
# Removes any row containing a missing value.
# Good when only a few records are affected.
df.dropna()
```

```python
# Fill the mean
# Best for numerical columns
df["Age"] = df["Age"].fillna(df["Age"].mean())
df["CGPA"] = df["CGPA"].fillna(df["CGPA"].mean())
```

```python
# Fill the median
# Best when outliers are present
df["Attendance"] = df["Attendance"].fillna(df["Attendance"].median())
```

```python
# Fill the mode
# Best when categorical data present
df["Gender"] = df["Gender"].fillna(df["Gender"].mode()[0])
df["City"] = df["City"].fillna(df["City"].mode()[0])
```

```python
# Verify the cleaning process
df.isnull().sum()
```

## Duplicate Records

```python
#Check duplicate rows
df.duplicated()
```

```python
# Count duplicate rows
df.duplicated().sum()
```

```python
# Drop the duplicate rows
df = df.drop_duplicates()
```

## Text Data Cleaning

```python
# Cleaning the text data
# Suppose gender contains Male, male, MALE
# Standardize them using below

df["Gender"] = df["Gender"].str.title()
```

```python
# Remove extra spaces:
df["Name"] = df["Name"].str.strip()
```

```python
# Convert to uppercase
df["Department"] = df["Department"].str.upper()
```

## Detecting and Handling Outliers

```python
# Method 1 to detect outlier
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(y=df["CGPA"])

plt.show()
```

```python
# Method 2 detect outlier usin IQR

Q1 = df["CGPA"].quantile(0.25)
Q3 = df["CGPA"].quantile(0.75)

IQR = Q3 - Q1
```

```python
lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR
```

```python
outliers = df[(df["CGPA"] < lower) | (df["CGPA"] > upper)]

outliers
```

```python
df_clean = df[(df["CGPA"] >= lower) & (df["CGPA"] <= upper)]
```

```python
# Verify the cleaned dataset
df.info()

df.describe()
```

## Saving the Cleaned Dataset

```python
df.to_csv("/content/drive/MyDrive/student_cleaned.csv", index=False)
```

## Key Learnings

- Raw data can contain missing values, duplicates, inconsistent text, and outliers.
- Different missing-value methods are selected based on the data type and distribution.
- Cleaning improves the reliability of analysis.
- A cleaned dataset can be saved separately for future use.
