# Student Dataset – Data Cleaning & Preprocessing Project
## Project Overview

### This project uses a Student Dataset to demonstrate the essential steps of data preprocessing, including:

##### Data Cleaning
##### Handling Missing Values
##### Outlier Detection and Treatment
##### Feature Engineering
##### Feature Scaling
##### Encoding Categorical Data

## Dataset Description

### The dataset contains demographic and academic information about students, including:

##### Age, Gender, Country, Residence
##### Education background
##### Weekly study hours
##### Exam and course performance

## Data Challenges

### Inconsistencies

##### Mixed formats in categorical fields (gender, country, prevEducation).
###### Example: "Male" vs "M", "Rsa" vs "RSA".

### Missing Values

##### Incomplete scores in Python and DB.
###### Missing categories in gender or country.

### Outliers

##### Unrealistic values in studyHOURS (e.g., > 70 hours/week).
###### Invalid exam scores outside the 0–100 range.

## Data Cleaning Steps
### Part 1 – Data Cleaning
##### Used df.info(), df.head(), and df.shape() to inspect structure.
##### Standardized categorical values with .str.strip().str.title().
##### Fixed inconsistent entries ("M" → "Male", "Barrrchelors" → "Bachelor").
##### Removed duplicate rows with df.drop_duplicates().
### Part 2 – Missing Data
##### Checked missing values using df.isnull().sum().
##### Numerical (Python, DB): imputed with median.
##### Categorical (gender, country): imputed with mode.
### Part 3 – Outliers
##### Used boxplots (sns.boxplot) and summary stats (.describe()).
##### Handled with IQR capping to reduce influence of extreme values.
### Part 4 – Feature Engineering
##### ProgrammingAvg = (Python + DB)/2
##### isAdult = 1 if Age ≥ 25 else 0
##### studyHOURS_cat = categorized into Low / Medium / High
### Part 5 – Feature Scaling
##### Detected numeric columns with df.select_dtypes().
##### Applied:
###### StandardScaler → mean=0, std=1 (for SVM, Logistic Regression).
###### MinMaxScaler → range 0–1 (for Neural Networks, KNN).
### Part 6 – Encoding Categorical Data
##### Detected categorical columns.
##### Used:
###### One-Hot Encoding for gender, country, residence.
###### Label Encoding for ordered fields (prevEducation).

## Deliverables
#### cleaned_students.csv → Final cleaned dataset
#### student_cleaning.ipynb → Jupyter Notebook with cleaning & preprocessing code
#### README.md → Project summary (this file)
