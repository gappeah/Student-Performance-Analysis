# Student Performance Analysis
![output](https://github.com/user-attachments/assets/fb5a3a03-d938-43f8-bbdc-b010e5f22265)


This repository contains a Jupyter Notebook that analyzes student performance based on various factors such as study hours, attendance, and scores in Math, English, and Science. The analysis uses the `pandas`, `numpy`, and `matplotlib` libraries to perform statistical calculations and visualize the relationships between the variables.

## Dataset

The dataset used in this analysis is `student_performance_dataset(in).csv`, which contains the following columns:

- **Student_ID**: A unique identifier for each student.
- **Age**: The age of the student.
- **Gender**: The gender of the student (M for Male, F for Female).
- **Math_Score**: The score obtained by the student in Mathematics.
- **English_Score**: The score obtained by the student in English.
- **Science_Score**: The score obtained by the student in Science.
- **Study_Hours**: The number of hours the student spends studying.
- **Attendance (%)**: The percentage of classes attended by the student.

## Analysis Overview

### 1. Data Inspection
- The dataset is loaded and displayed to understand its structure and contents.

### 2. Data Conversion
- The gender column is converted into numerical values (0 for Male and 1 for Female) to facilitate analysis.

### 3. Statistical Analysis
- **Mean and Standard Deviation**: The mean and standard deviation for Math, English, and Science scores are calculated.
- **Correlation Analysis**: The correlations between study hours and science scores, as well as between attendance and scores in Math, English, and Science, are computed.

### 4. Identifying Low and High Performers
- **Low Scores**: Identifies students with scores below 60 in any subject.
- **High Scores**: Identifies students with scores above 90 in any subject.

### 5. Regression Analysis
- A linear regression model is fitted to the data to examine the relationship between study hours and Math scores.
- The regression line is plotted along with the data points to visualize the trend.

### 6. Visualisation
- A scatter plot is generated to show the relationship between study hours and Math scores, with the regression line overlaid.

## How to Run the Notebook

1. Clone the repository:
   ```bash
   git clone <https://github.com/gappeah/Student-Performance-Analysis.git>
   ```
2. Navigate to the project directory:
   ```bash
   cd <repository_directory>
   ```
3. Install the required packages:
   ```bash
   pip install pandas numpy matplotlib
   ```
4. Run the Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open the notebook file and execute the cells to see the analysis.

## Conclusion

This notebook provides insights into how study habits and attendance can influence student performance in different subjects. By analyzing the data and visualizing the relationships, it helps in understanding the factors contributing to high and low academic performance.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.**
