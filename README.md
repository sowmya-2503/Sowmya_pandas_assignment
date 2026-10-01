# Pandas Data Analysis & Data Cleaning

A Python/Jupyter Notebook focused on practicing **Pandas operations, data analysis, code correction, edge cases, and data-cleaning techniques**.

The notebook contains worked examples, output-prediction questions, explanations, corrected code, and scenario-based data-cleaning exercises.

## 📌 Topics Covered

### 1. Output Prediction

The notebook begins with exercises that require predicting the output of Pandas and NumPy code and explaining the underlying operations.

Topics include:

* NumPy array operations
* Pandas Series operations
* Vectorization
* Boolean filtering
* Descriptive statistics
* Group-wise analysis
* Correlation

Examples include:

```python
arr * 2
s * 2
```

and filtering DataFrame records based on marks.

### 2. Descriptive Statistics

Practice with common statistical operations:

* `mean()`
* `max()`
* `median()`

The notebook also explains the difference between the mean and median.

### 3. Group-wise Analysis

Using `groupby()` to calculate department-wise statistics.

Example:

```python
df.groupby('Department')['Salary'].mean()
```

This demonstrates how data can be grouped and aggregated based on categorical columns.

### 4. Correlation

The notebook covers both positive and negative correlation.

Examples include:

* Study hours vs. marks
* Price vs. demand

It demonstrates:

```python
df['Hours'].corr(df['Marks'])
```

and explains the meaning of positive and negative correlation coefficients.

## 🔧 Code Correction Exercises

Several exercises present incorrect Pandas code and require correcting it.

Topics include:

### CSV Reading

Understanding the use of:

```python
pd.read_csv()
```

and the difference between using `header=None` and allowing Pandas to read the header row.

### Sorting Data

Finding the highest salaries using:

```python
df.sort_values('Salary', ascending=False).head(5)
```

### Missing Data

Using `fillna()` correctly and assigning the result back to the DataFrame:

```python
df['Marks'] = df['Marks'].fillna(df['Marks'].mean())
```

### Correlation Syntax

Correctly calculating the correlation between two columns using:

```python
df['Hours'].corr(df['Marks'])
```

## 🧪 Edge Cases

The notebook contains questions involving situations that commonly cause problems during data analysis.

### NumPy Broadcasting

Explores arrays with shapes:

```text
(3, 1)
(1, 3)
```

and demonstrates how broadcasting produces a `(3, 3)` result.

### CSV Parsing

Discusses CSV files containing:

* Commas inside quoted fields
* Missing values
* Different date formats
* Potential parsing issues

### Outliers

Uses a salary dataset containing an extreme value to demonstrate how an outlier affects:

* Mean
* Median
* Interpretation of a typical value

The notebook emphasizes that extreme values can strongly influence the mean while the median is more resistant to outliers.

## 🧹 Data Cleaning

A major part of the notebook focuses on cleaning a student-assessment dataset.

The cleaning workflow includes:

1. Loading and inspecting the dataset
2. Standardizing department names
3. Finding and removing duplicate records
4. Converting marks to numeric values
5. Investigating missing marks
6. Identifying invalid marks
7. Reporting the final cleaned dataset

### Dataset Inspection

The notebook uses:

```python
df.head()
df.info()
df.isnull().sum()
```

to inspect the dataset.

### Standardizing Departments

Department names such as:

```text
IT
it
I.T.
Finance
FIN.
```

are standardized using string operations and replacements.

### Removing Duplicates

Duplicate records are identified using:

```python
df.duplicated()
```

and removed using:

```python
df.drop_duplicates()
```

### Converting Marks

Values such as:

```text
88 marks
Absent
NA
blank
```

are processed and converted into an appropriate numeric representation.

The notebook uses:

```python
pd.to_numeric(df["Marks"], errors="coerce")
```

to convert invalid/non-numeric values to `NaN`.

### Missing Marks

The notebook distinguishes between genuinely missing marks and students who may have been absent.

It also discusses the risk of deleting missing records without investigating why the values are missing, since doing so could introduce bias into the analysis.

### Invalid Marks

Marks outside the valid range of **0–100** are identified using conditions such as:

```python
(df["Marks"] < 0) | (df["Marks"] > 100)
```

Invalid values can then be investigated or converted to missing values.

## 🛠️ Technologies Used

* **Python 3**
* **Pandas**
* **NumPy**
* **Jupyter Notebook**

## 📋 Requirements

Install the required Python libraries with:

```bash
pip install pandas numpy jupyter
```

## 🚀 Running the Notebook

Start Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
Sowmya_pandas.ipynb
```

Run the cells individually to reproduce the examples and exercises.

## 🎯 Learning Objectives

This notebook is designed to practice:

* Creating and manipulating Pandas DataFrames and Series
* Performing vectorized operations
* Filtering data
* Calculating descriptive statistics
* Grouping and aggregating data
* Calculating correlations
* Reading CSV files
* Correcting common Pandas mistakes
* Handling missing values
* Detecting duplicates
* Standardizing inconsistent data
* Converting columns to appropriate data types
* Detecting outliers and invalid values
* Building a basic data-cleaning workflow

## 📁 Repository Structure

```text
.
└── Sowmya_pandas.ipynb
```

## 📄 License

No license information is specified in the notebook.
