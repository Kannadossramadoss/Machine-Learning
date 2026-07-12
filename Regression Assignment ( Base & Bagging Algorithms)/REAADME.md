# 🏥 Medical Insurance Cost Prediction using Machine Learning

An end-to-end Machine Learning project that predicts **medical insurance charges** based on an individual's demographic and lifestyle information. This project compares multiple regression algorithms, performs hyperparameter tuning, and identifies the best-performing model using evaluation metrics.

---

## 📌 Project Overview

Healthcare insurance costs are influenced by multiple factors such as age, BMI, smoking habits, and region. Accurately predicting insurance charges helps insurance companies estimate premiums and enables customers to understand the factors affecting their medical expenses.

This project develops and compares several regression models to predict insurance charges using the **Medical Insurance Dataset**.

---

## 🎯 Problem Statement

Insurance providers need an accurate method to estimate the medical charges for customers before issuing policies.

The objective of this project is to build a Machine Learning model that predicts **medical insurance charges** based on customer information.

---

## 📂 Project Structure

```
Medical-Insurance-Cost-Prediction/
│
├── data/
│   └── insurance_pre.csv
│
├── notebooks/
│   └── Medical_Insurance_Prediction.ipynb
│
├── models/
│   └── final_model.sav
│
└── README.md
```

---

## 📊 Dataset

The dataset contains **1,338 customer records** with the following features.

| Feature | Description |
|----------|-------------|
| age | Age of the customer |
| sex | Gender |
| bmi | Body Mass Index |
| children | Number of dependent children |
| smoker | Smoking status |
| region | Residential region |
| charges | Medical insurance cost (Target Variable) |

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Pickle

---

## ⚙️ Machine Learning Workflow

### 1. Data Loading

- Load the dataset
- Inspect data types
- Check dataset dimensions

---

### 2. Exploratory Data Analysis (EDA)

- Dataset overview
- Missing value analysis
- Duplicate record detection
- Statistical summary

---

### 3. Data Preprocessing

- Remove duplicate records
- Encode categorical variables
- Prepare input and target variables

---

### 4. Train-Test Split

The dataset is divided into:

- **Training Set (70%)**
- **Testing Set (30%)**

using:

```python
train_test_split(random_state=0)
```

---

### 5. Machine Learning Models

The following regression algorithms are implemented and compared:

- Multiple Linear Regression
- Support Vector Regression (SVR)
- Decision Tree Regressor
- Random Forest Regressor

---

### 6. Hyperparameter Tuning

Hyperparameter optimization is performed using **GridSearchCV** to identify the best model configuration.

Benefits include:

- Better generalization
- Improved prediction accuracy
- Reduced overfitting

---

### 7. Model Evaluation

Models are evaluated using:

- R² Score
- Training Performance
- Testing Performance
- Cross-validation results

The best-performing model is selected based on its predictive performance.

---

### 8. Model Serialization

The final trained model is saved using the Pickle library for future predictions.

```python
final_model.sav
```

---

## 📈 Models Compared

| Model | Purpose |
|--------|----------|
| Multiple Linear Regression | Baseline regression model |
| Support Vector Regression | Captures complex nonlinear relationships |
| Decision Tree Regressor | Tree-based prediction model |
| Random Forest Regressor | Ensemble learning for improved accuracy |

---

## 🚀 Features of This Project

- Complete data preprocessing pipeline
- Duplicate record removal
- Categorical feature encoding
- Multiple regression model comparison
- Hyperparameter tuning using GridSearchCV
- Performance evaluation using R² Score
- Model serialization for deployment

---

## ▶️ How to Run

### Clone the repository

```bash
git clone <repository-url>
```

### Install dependencies

```bash
pip install pandas numpy matplotlib scikit-learn
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook and execute all cells.

---

## 📦 Output

The project generates:

- Cleaned dataset
- Trained regression models
- Model comparison results
- Best-performing model
- Serialized model (`final_model.sav`) for deployment

---

## 📚 Learning Outcomes

This project demonstrates how to:

- Perform Exploratory Data Analysis (EDA)
- Clean and preprocess structured data
- Encode categorical variables
- Train multiple regression algorithms
- Tune hyperparameters using GridSearchCV
- Compare machine learning models
- Evaluate regression performance
- Save trained models for production use

---

## 🔮 Future Improvements

- Feature importance analysis
- SHAP explainability
- Advanced ensemble models (XGBoost, LightGBM, CatBoost)
- Model deployment using Flask or FastAPI
- Interactive prediction web application
- Experiment tracking using MLflow

---
