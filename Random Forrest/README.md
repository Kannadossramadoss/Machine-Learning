# 🌲 Random Forest Regression – Startup Profit Prediction

An end-to-end Machine Learning project that predicts startup profit using the **Random Forest Regression** algorithm. This notebook demonstrates the complete ML workflow including data preprocessing, feature engineering, model training, hyperparameter tuning using GridSearchCV, model evaluation, and model serialization.

---

## 📌 Project Overview

This project uses the **50 Startups** dataset to predict the **Profit** of a startup based on its operational expenditures and location.

Random Forest is an ensemble learning algorithm that combines multiple Decision Trees to improve prediction accuracy and reduce overfitting.

---

## 🎯 Business Problem

Companies invest in multiple areas such as:

- R&D
- Administration
- Marketing

Management wants to estimate future profits based on these investments. Since the relationship between these variables is often non-linear, Random Forest provides a robust solution capable of modeling complex patterns.

---

## 📂 Project Structure

```
Project/
│
├── data/
│   └── 50_Startups.csv
│
├── models/
│   └── final_random_forest_model.sav
│
├── notebooks/
│   └── 1. Random Forest for Regression.ipynb
│   └── 2.Deployment-Phase-2.ipynb
│
└── README.md
```

---

## 📊 Dataset

The dataset contains startup investment information.

### Input Features

- R&D Spend
- Administration
- Marketing Spend
- State

### Target Variable

- Profit

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Pickle

---

## ⚙️ Machine Learning Workflow

### 1. Import Libraries

Load the required Python libraries.

### 2. Load Dataset

Read the startup dataset using Pandas.

### 3. Data Preprocessing

- Handle categorical variables
- Apply One-Hot Encoding to the **State** column
- Prepare feature matrix and target variable

### 4. Train-Test Split

Split the dataset into:

- Training Set (70%)
- Testing Set (30%)

using

```python
train_test_split(random_state=0)
```

---

### 5. Model Building

Create a **Random Forest Regressor**.

```python
RandomForestRegressor(random_state=0)
```

---

### 6. Hyperparameter Tuning

GridSearchCV is used to determine the best model.

Parameters searched:

| Parameter | Values |
|-----------|--------|
| criterion | squared_error, absolute_error, poisson |
| n_estimators | 10 to 48 (step = 2) |

Cross Validation:

- 5-Fold CV

Evaluation Metric:

- R² Score

---

### 7. Model Evaluation

The notebook compares all parameter combinations and selects the model with the highest average **R² Score**.

Important outputs include:

- Best Parameters
- Mean Cross Validation Score
- Rank of each model

---

### 8. Model Serialization

The best trained model is saved as:

```
final_random_forest_model.sav
```

using the Pickle library.

---

## 📈 Why Random Forest?

Random Forest offers several advantages:

- Handles non-linear relationships
- Reduces overfitting
- Robust to noisy data
- Works well with high-dimensional datasets
- Provides stable predictions

---

## ✅ Advantages

- High prediction accuracy
- Less prone to overfitting than Decision Trees
- Handles both numerical and categorical features
- Works well without extensive preprocessing
- Can estimate feature importance

---

## ❌ Limitations

- Slower to train than a single Decision Tree
- Larger model size
- Less interpretable
- Hyperparameter tuning can be computationally expensive

---

## 🚀 How to Run

### Clone the repository

```bash
git clone <repository-url>
```

### Install dependencies

```bash
pip install pandas numpy scikit-learn
```

### Run the notebook

```bash
jupyter notebook
```

Open:

```
Random_Forest.ipynb
```

Execute all cells.

---

## 📦 Output

The notebook generates:

- Trained Random Forest model
- Best hyperparameters
- Cross-validation results
- Saved model file (`.sav`)

---

## 📚 Learning Outcomes

This project demonstrates how to:

- Perform data preprocessing
- Encode categorical variables
- Split datasets for training and testing
- Build a Random Forest Regression model
- Perform hyperparameter tuning using GridSearchCV
- Evaluate model performance using R² Score
- Save trained models for deployment

---
