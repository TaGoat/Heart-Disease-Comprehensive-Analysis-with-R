# Heart Disease Comprehensive Analysis

This project is a comprehensive data analytics and machine learning workflow designed to analyze and predict the presence of heart disease. It utilizes the UCI Heart Disease dataset to perform data cleaning, exploratory data analysis (EDA), statistical testing, and predictive modeling using R.

## 📌 Project Overview

The goal of this analysis is to identify key factors contributing to heart disease and build predictive models to classify patients. The workflow covers the entire data science pipeline:
* **Data Preprocessing:** Cleaning and transforming raw data into a usable format.
* **Exploratory Data Analysis (EDA):** Visualizing distributions and relationships between clinical variables.
* **Statistical Analysis:** Conducting Chi-Square and T-Tests to validate hypothesis.
* **Machine Learning:** Training and evaluating four different classification algorithms.

## 📂 Dataset

The data is sourced from the **UCI Machine Learning Repository** (Cleveland database).
* **Source URL:** `https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data`
* **Target Variable:** `target` (Binary classification: "Disease" vs "No_Disease").

### Key Features
The dataset includes 14 attributes:
* **Demographics:** Age, Sex.
* **Vitals:** Resting Blood Pressure (`trestbps`), Cholesterol (`chol`), Fasting Blood Sugar (`fbs`), Max Heart Rate (`thalach`).
* **Clinical:** Chest Pain Type (`cp`), Resting ECG (`restecg`), Exercise Induced Angina (`exang`), ST depression (`oldpeak`), Slope of ST segment (`slope`), Number of major vessels (`ca`), Thalassemia (`thal`).

## 🛠 Technologies & Libraries

The project is built using **R** and utilizes the following libraries for analysis and visualization:

* **Data Manipulation:** `tidyverse`, `dplyr`, `reshape2`
* **Visualization:** `ggplot2`, `corrplot`, `gridExtra`, `ggcorrplot`, `viridis`, `scales`, `plotly`, `GGally`
* **Machine Learning:** `caret`, `randomForest`, `e1071`, `rpart`, `class`, `MASS`
* **Model Visualization:** `rpart.plot`, `pROC`

## 📊 Analysis Workflow

### 1. Data Cleaning
* Missing values (`?`) are handled and removed.
* Categorical integers are recoded into meaningful factors (e.g., Sex: 0="Female", 1="Male"; Chest Pain: 0-3 types).
* The target variable is binarized into `0` (No Disease) and `1` (Disease).

### 2. Exploratory Data Analysis (EDA)
The project generates visualizations for:
* **Target Distribution:** Bar charts showing the balance of the dataset.
* **Demographics:** Histograms and density plots for Age vs. Disease.
* **Clinical Measures:** Box plots comparing Cholesterol, Max Heart Rate, and Resting BP across diagnosis classes.
* **Correlation:** A heatmap matrix to visualize relationships between numeric features.

### 3. Feature Engineering
New categorical features are derived to enhance model performance:
* `age_group`: Young, Middle, Senior, Elderly.
* `chol_category`: Desirable, Borderline High, High.
* `bp_category`: Normal, Elevated, High.

### 4. Machine Learning Models
The data is split into **80% training** and **20% testing** sets. 10-fold Cross-Validation is applied using the `caret` package.
The following models are trained and compared:
1.  **Logistic Regression**
2.  **Decision Tree** (visualized with `rpart.plot`)
3.  **Random Forest** (500 trees)
4.  **Support Vector Machine (SVM)** (Radial Kernel)

## 📈 Evaluation Metrics

Models are evaluated and compared based on:
* **Accuracy**
* **Sensitivity**
* **Specificity**
* **AUC (Area Under the Curve)**
* **ROC Curves** (Visual comparison of all models)

The project also outputs a **Feature Importance** plot derived from the Random Forest model to identify the most significant clinical predictors.

## 🚀 How to Run

1.  Ensure you have **R** and **RStudio** installed.
2.  Open the file `Heart-Diseases.Rmd`.
3.  The script includes an auto-installer function that will check for missing packages and install them automatically.
4.  Click the **Knit** button in RStudio to generate the full HTML report (`html_notebook`).

---