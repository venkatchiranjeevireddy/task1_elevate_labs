# 🚢 Titanic Dataset Preprocessing & Feature Engineering

This project focuses on cleaning, transforming, and preparing the Titanic dataset from Kaggle for machine learning tasks. The main goal was to handle missing data, extract useful features, and make the dataset ready for further modeling.

---

## 📌 Objective

The objective of this project was **not** to build a predictive model, but rather to focus on solid **data preprocessing and feature engineering** techniques. These are foundational steps required before any machine learning model can be trained effectively.

---

## 📂 Dataset Description

The dataset contains records of passengers aboard the Titanic, including the following features:

- `PassengerId`: Unique passenger ID
- `Survived`: 0 = No, 1 = Yes (target column)
- `Pclass`: Ticket class (1st, 2nd, 3rd)
- `Name`: Full name (includes titles)
- `Sex`: Gender
- `Age`: Age of the passenger
- `SibSp`: Number of siblings/spouses aboard
- `Parch`: Number of parents/children aboard
- `Ticket`: Ticket number
- `Fare`: Amount paid
- `Cabin`: Cabin number
- `Embarked`: Port of embarkation

---

## 🔧 Preprocessing Steps

We applied the following steps to clean and enhance the dataset:

### 1. **Handling Missing Values**
- `Age`: Filled using the median age.
- `Embarked`: Filled using the most frequent value.
- `Cabin`: Dropped entirely due to many missing values.

### 2. **Encoding Categorical Variables**
- `Sex`: Encoded as binary (0 for female, 1 for male).
- `Embarked`: Converted into three separate binary columns:
  - `Embarked_S`, `Embarked_C`, `Embarked_Q`

### 3. **Feature Engineering**
- `Title`: Extracted from the `Name` field and grouped into major categories: Mr, Miss, Mrs, Master, Rare.
- `FamilySize`: Created by adding `SibSp + Parch + 1`.
- `IsAlone`: A binary flag indicating if the passenger was traveling alone.
- `TicketPrefix`: Extracted any prefix from the `Ticket` field (e.g. PC, STON/O2) and encoded numerically.

### 4. **Feature Scaling**
- Standardized the following columns using `StandardScaler`:
  - `Age`, `Fare`, `SibSp`, `Parch`, `FamilySize`

### 5. **Outlier Removal**
- Used the Interquartile Range (IQR) method to detect and remove extreme outliers from the dataset.

---

## 📊 Exploratory Analysis

Basic visualizations were used to understand patterns and distributions:
- Count plots for categorical features
- Boxplots to detect outliers
- Correlation heatmap to explore feature relationships

