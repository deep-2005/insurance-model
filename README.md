# 🏥 Medical Insurance Cost Analysis

## 📌 Project Overview

This project focuses on **Exploratory Data Analysis (EDA), Data Cleaning, Preprocessing, Feature Engineering, and Statistical Analysis** of a medical insurance dataset.

The dataset contains information about individuals such as their age, gender, BMI, number of children, smoking status, residential region, and medical insurance charges.

The main objective of this project is to understand the structure of the dataset, identify patterns and relationships between different variables, prepare the data for further analysis, and investigate relationships between categorical features and insurance charges.

---

## 📊 Dataset

The project uses the **Medical Cost Personal Dataset (`insurance.csv`)**.

### Features

| Feature    | Description                        |
| ---------- | ---------------------------------- |
| `age`      | Age of the individual              |
| `sex`      | Gender of the individual           |
| `bmi`      | Body Mass Index                    |
| `children` | Number of children/dependents      |
| `smoker`   | Whether the individual is a smoker |
| `region`   | Residential region                 |
| `charges`  | Medical insurance charges          |

---

## 🎯 Objectives

The major objectives of this project are:

* Perform Exploratory Data Analysis (EDA)
* Understand the structure and characteristics of the dataset
* Check for missing values and duplicate records
* Analyze numerical and categorical variables
* Visualize data distributions using graphs
* Examine correlations between numerical variables
* Clean and preprocess the dataset
* Convert categorical variables into numerical form
* Perform feature engineering
* Categorize individuals according to BMI
* Standardize selected numerical features
* Calculate Pearson correlation
* Perform Chi-Square statistical tests

---

## 🔍 Exploratory Data Analysis

The following steps are performed during EDA:

### Dataset Inspection

* Dataset shape
* First few records
* Data types
* Statistical summary
* Column names
* Missing-value analysis

### Data Visualization

Several visualizations are created using **Seaborn** and **Matplotlib**, including:

* Histograms of numerical variables
* Count plots for:

  * Number of children
  * Gender
  * Smoking status
* Box plots for numerical variables
* Correlation heatmap

These visualizations help understand the distribution of the data and identify potential relationships and outliers.

---

## 🧹 Data Cleaning & Preprocessing

The following preprocessing operations are performed:

### 1. Duplicate Removal

Duplicate records are removed from the dataset.

```python
df_cleaned.drop_duplicates(inplace=True)
```

### 2. Encoding Categorical Variables

The `sex` column is converted into a binary variable:

```text
male → 0
female → 1
```

It is then renamed to:

```text
is_female
```

Similarly, the `smoker` column is encoded as:

```text
no → 0
yes → 1
```

and renamed to:

```text
is_smoker
```

### 3. One-Hot Encoding

The `region` variable is converted into dummy variables using one-hot encoding.

```python
pd.get_dummies(df_cleaned, columns=['region'], drop_first=True)
```

This converts categorical regions into numerical features that can be used for statistical analysis and machine learning.

---

## 🧬 Feature Engineering

A new feature called `bmi_category` is created from the BMI value.

The BMI categories used in the notebook are:

| BMI Range     | Category    |
| ------------- | ----------- |
| `< 18.5`      | Underweight |
| `18.5 – 24.9` | Normal      |
| `25 – 29.9`   | Overweight  |
| `≥ 30`        | Obese       |

The newly created categorical feature is then converted into dummy variables.

---

## 📏 Feature Scaling

The following numerical features are standardized using `StandardScaler`:

* `age`
* `bmi`
* `children`

Standardization transforms the variables so that they are on a comparable scale.

```python
from sklearn.preprocessing import StandardScaler

cols = ['age', 'bmi', 'children']

scaler = StandardScaler()
df_cleaned[cols] = scaler.fit_transform(df_cleaned[cols])
```

---

## 📈 Pearson Correlation Analysis

Pearson correlation is calculated for selected variables to examine their linear relationships.

The analysis includes variables such as:

* Age
* Gender
* BMI
* Children
* Smoking status
* Insurance charges
* Region
* BMI categories

The resulting correlation matrix helps identify the strength and direction of linear relationships between variables.

---

## 🧪 Chi-Square Test

A **Chi-Square Test of Independence** is performed to investigate relationships between categorical features and categorized insurance charges.

The continuous `charges` variable is divided into three categories:

```text
Low
Medium
High
```

using quantile-based binning.

The Chi-Square test is then performed between `charges_cat` and categorical/binary variables such as:

* `is_female`
* `is_smoker`
* `region_northwest`
* `region_southeast`
* `region_southwest`
* `bmi_category_Normal`
* `bmi_category_Overweight`
* `bmi_category_Obese`

A significance level of **0.05** is used in the notebook.

---

## 🛠️ Technologies & Libraries

The project is implemented in **Python** using Jupyter Notebook.

### Libraries Used

* **NumPy** – Numerical operations
* **Pandas** – Data manipulation and analysis
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization
* **Scikit-learn** – Feature scaling
* **SciPy** – Statistical testing

---

## 📁 Project Structure

```text
Medical-Insurance-Cost-Analysis/
│
├── insurance.csv
├── Medical_Insurance_Analysis.ipynb
└── README.md
```



---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the project directory

```bash
cd Medical-Insurance-Cost-Analysis
```

### 3. Install the required libraries

```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the notebook

Open:

```text
Medical_Insurance_Analysis.ipynb
```

Make sure `insurance.csv` is located in the appropriate directory so that the following code works:

```python
df = pd.read_csv('insurance.csv')
```

---

## 📌 Key Analysis Areas

This project demonstrates practical skills in:

* Data Exploration
* Data Cleaning
* Data Preprocessing
* Categorical Encoding
* One-Hot Encoding
* Feature Engineering
* Feature Scaling
* Data Visualization
* Correlation Analysis
* Statistical Hypothesis Testing
* Python Data Analysis

---

## 🚀 Future Scope

This analysis can be extended by:

* Building a machine learning model to predict medical insurance charges
* Comparing Linear Regression, Random Forest, and other regression models
* Performing train-test splitting
* Evaluating models using MAE, MSE, RMSE, and R²
* Performing more detailed outlier analysis
* Creating an interactive dashboard
* Performing deeper statistical analysis

---

## 📝 Conclusion

This project provides a complete data-analysis workflow starting from **raw medical insurance data** and progressing through **EDA, cleaning, preprocessing, feature engineering, scaling, correlation analysis, and statistical testing**.

The notebook demonstrates how Python-based data analysis techniques can be used to understand patterns and relationships within a real-world-style healthcare insurance dataset.

---

## 👨‍💻 Author

**Debaneek Roy**

---


