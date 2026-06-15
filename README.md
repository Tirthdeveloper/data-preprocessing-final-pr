# 📊 Credit Risk Data Analysis & Preprocessing Project

## 📌 Project Overview

This project demonstrates a complete **Data Analysis and Data Preprocessing Pipeline** using a Credit Risk dataset collected from multiple sources. The objective is to transform raw financial data into a clean, structured, and machine-learning-ready dataset through various preprocessing and feature engineering techniques.

The project covers:

- Data Collection from multiple sources
- Data Integration
- Exploratory Data Analysis (EDA)
- Missing Value Treatment
- Outlier Detection & Treatment
- Feature Encoding
- Feature Scaling
- Feature Transformation
- Feature Engineering
- Final Dataset Preparation

---

## 🎯 Project Objectives

- Collect and integrate data from multiple sources.
- Perform exploratory data analysis.
- Handle missing values using different techniques.
- Detect and treat outliers.
- Encode categorical features.
- Scale and transform numerical features.
- Create meaningful business features.
- Prepare a clean dataset for Machine Learning models.

---

## 📂 Data Sources

The dataset was created by integrating data from multiple sources:

### 1. CSV Dataset
Contains customer financial and credit information.

### 2. JSON Dataset
Additional customer details and attributes.

### 3. SQLite Database
Historical records and transaction-related data.

### 4. API Data
Economic indicators such as:

- Inflation Rate
- Repo Rate
- GDP Growth

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SQLite3
- Scikit-Learn
- SciPy
- YData Profiling

---

# 📊 Exploratory Data Analysis (EDA)

The following analyses were performed:

- Dataset Shape Analysis
- Data Type Inspection
- Summary Statistics
- Missing Value Analysis
- Duplicate Detection
- Correlation Analysis
- Distribution Analysis

### Automated EDA Report

Generated using:

```python
from ydata_profiling import ProfileReport
```

Output:

```text
credit_report.html
```

---

# 🧹 Missing Value Treatment

Different missing value handling techniques were applied:

### Mean Imputation

Used for:

- age

### Median Imputation

Used for:

- annual_income

### Most Frequent Imputation

Used for:

- employment_type

### Random Sample Imputation

Used for:

- annual_income

### KNN Imputation

Applied on:

- annual_income
- loan_amount
- credit_score

### MICE (Iterative Imputer)

Applied for advanced missing value estimation.

### Complete Case Analysis (CCA)

Rows containing missing values were removed where necessary.

---

# 📈 Outlier Detection & Treatment

## Z-Score Method

Used to detect extreme values in:

- annual_income
- loan_amount
- credit_score

### Formula

\[
Z = \frac{X-\mu}{\sigma}
\]

---

## IQR Method

Applied on:

- annual_income

### Formula

\[
IQR = Q3 - Q1
\]

Lower Bound:

\[
Q1 - 1.5 \times IQR
\]

Upper Bound:

\[
Q3 + 1.5 \times IQR
\]

---

## Capping (Clipping)

Applied using:

```python
Series.clip()
```

---

## Winsorization

Applied using:

```python
winsorize()
```

to preserve observations while limiting extreme values.

---

# 📅 Date Feature Extraction

Extracted features from:

```text
join_date
```

Generated:

- Year
- Month
- Day
- Weekday

---

# 🔤 Encoding Techniques

## Ordinal Encoding

Applied on:

```text
education_level
```

### Mapping

| Education Level | Encoded Value |
|-----------------|--------------|
| Primary | 1 |
| Secondary | 2 |
| Graduate | 3 |
| Post-Graduate | 4 |

---

## Label Encoding

Applied on:

```text
gender
```

---

## One Hot Encoding

Applied on:

- region
- loan_purpose

---

# ⚙️ Feature Engineering

Several new features were created to improve model performance.

### Income Group

Categorized annual income into:

- Low
- Medium
- High
- Very High

---

### Transaction Quantile

Created using:

```python
pd.qcut()
```

---

### Transaction Cluster

Created using:

```python
KMeans Clustering
```

---

### Debt-to-Income Ratio

```python
debt_income_ratio
```

Measures financial burden relative to income.

---

### Average Monthly Transactions

```python
avg_monthly_transactions
```

---

### Spending-Income Ratio

```python
spending_income_ratio
```

Represents spending behavior relative to earnings.

---

# 📏 Feature Scaling

Different scaling techniques were applied.

## StandardScaler

Applied on:

- annual_income
- loan_amount

---

## MinMaxScaler

Applied on:

- credit_score

---

## MaxAbsScaler

Applied on:

- transaction_count

---

## RobustScaler

Applied on:

- repayment_history

---

# 🔄 Feature Transformation

To improve distribution and reduce skewness:

## Log Transformation

```python
log_spending
```

---

## Reciprocal Transformation

```python
reciprocal_spending
```

---

## Square Root Transformation

```python
sqrt_spending
```

---

## Yeo-Johnson Transformation

Applied on:

- annual_income
- loan_amount

---

# 📁 Final Dataset

The cleaned and transformed dataset was exported as:

```text
final_cleaned_dataset.csv
```

This dataset is fully prepared for Machine Learning model development.

---

# 🔄 Project Workflow

```text
Data Collection
       ↓
Data Integration
       ↓
Exploratory Data Analysis
       ↓
Missing Value Treatment
       ↓
Outlier Treatment
       ↓
Encoding
       ↓
Feature Scaling
       ↓
Feature Transformation
       ↓
Feature Engineering
       ↓
Final Cleaned Dataset
```

---

# 🎓 Key Learning Outcomes

✔ Multi-Source Data Collection

✔ Data Integration Techniques

✔ Automated EDA using YData Profiling

✔ Missing Value Handling Methods

✔ Outlier Detection and Treatment

✔ Feature Encoding

✔ Feature Scaling

✔ Feature Transformation

✔ Feature Engineering

✔ ML-Ready Dataset Preparation

---

# 🚀 Conclusion

This project demonstrates an end-to-end Credit Risk Data Analysis and Preprocessing workflow. By integrating data from multiple sources and applying advanced preprocessing techniques, the dataset was transformed into a clean, structured, and machine-learning-ready format suitable for predictive modeling, credit scoring, and risk assessment.

---

## ⭐ Support

If you found this project useful, consider giving the repository a **Star ⭐** on GitHub.
