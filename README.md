# Analyzing Student Performance to Improve Study Strategies

## Objectives
- **Mathematical Operations**: Calculate basic statistics, correlations, and perform element-wise operations.
- **Data Analysis**: Manipulate the dataset to identify trends and outliers.
- **Scientific Computing**: Use linear regression to model the relationship between study hours and academic performance.
- **Data Visualization**: Visualize the findings using graphs and charts.

## Steps

### 1. Load the Dataset
- Load the dataset using `NumPy` and `Pandas`.
- Convert the relevant columns into NumPy arrays for processing.

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('student_performance_dataset.csv')

# Convert relevant columns to NumPy arrays
math_scores = np.array(df['Math_Score'])
english_scores = np.array(df['English_Score'])
science_scores = np.array(df['Science_Score'])
study_hours = np.array(df['Study_Hours'])
attendance = np.array(df['Attendance'])

**Why use Pandas?**
1. **Data Loading**: Pandas simplifies loading CSV files into DataFrames, handling headers and missing values efficiently.
2. **Initial Data Processing**: For large or complex datasets, Pandas is more efficient for filtering, sorting, or manipulating data before converting it into NumPy arrays.
3. **Real-World Workflow**: Pandas is commonly used for initial data manipulation in real-world projects, with NumPy handling more specialized numerical operations.

### 2. Convert Categorical Data (if needed)
If you have categorical data like gender, you may need to convert it to numerical form manually:

# Converting 'M' to 0 and 'F' to 1
genders = np.array([0 if gender == 'M' else 1 for gender in df['Gender']])

### 3. Basic Statistical Analysis
- Calculate the mean, median, and standard deviation of scores in each subject.
- Determine the correlation between study hours and scores, as well as between attendance and scores.

# Calculate basic statistics
math_mean = np.mean(math_scores)
english_mean = np.mean(english_scores)
science_mean = np.mean(science_scores)

math_std = np.std(math_scores)
english_std = np.std(english_scores)
science_std = np.std(science_scores)

# Correlation between study hours and scores
study_science_corr = np.corrcoef(study_hours, science_scores)[0, 1]

# Correlation between attendance and scores
attendance_math_corr = np.corrcoef(attendance, math_scores)[0, 1]
attendance_english_corr = np.corrcoef(attendance, english_scores)[0, 1]
attendance_science_corr = np.corrcoef(attendance, science_scores)[0, 1]

print(f"Mean Math Score: {math_mean}, Std: {math_std}")
print(f"Correlation between Study Hours and Science Score: {study_science_corr}")
print(f"Correlation between Attendance and Math Score: {attendance_math_corr}")

### 4. Identify Outliers
- Identify students with very low or very high scores in each subject.
- Use element-wise operations to flag these students.

# Identify outliers (scores below 60 or above 90)
low_scores = np.where((math_scores < 60) | (english_scores < 60) | (science_scores < 60))
high_scores = np.where((math_scores > 90) | (english_scores > 90) | (science_scores > 90))

print(f"Students with low scores: {low_scores}")
print(f"Students with high scores: {high_scores}")

### 5. Modeling and Prediction
- Use linear regression to predict math scores based on study hours.
- Calculate the slope and intercept of the regression line.

# Simple linear regression (study hours vs math scores)
slope, intercept = np.polyfit(study_hours, math_scores, 1)
print(f"Regression line: Math_Score = {slope} * Study_Hours + {intercept}")

### 6. Data Visualization
- Plot the relationship between study hours and math scores.
- Create a scatter plot with the regression line overlaid.
![output](https://github.com/user-attachments/assets/dc8c5d85-b5ea-4d5c-ac68-a155d26c8c5f)

# Scatter plot of study hours vs math scores
plt.scatter(study_hours, math_scores, label='Data points')
plt.plot(study_hours, slope * study_hours + intercept, color='red', label='Regression line')
plt.xlabel('Study Hours')
plt.ylabel('Math Scores')
plt.title('Relationship between Study Hours and Math Scores')
plt.legend()
plt.show()
