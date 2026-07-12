# 🚀 Medical Insurance Cost Prediction using Boosting Algorithms

An end-to-end Machine Learning project that predicts **medical insurance charges** using customer demographic and lifestyle information. This project implements and compares three powerful boosting algorithms—**AdaBoost**, **XGBoost**, and **LightGBM**—to identify the best-performing model for regression tasks.

---

# 📖 Project Overview

Medical insurance premiums depend on several factors such as age, BMI, smoking habits, and family size. Estimating these costs accurately helps insurance providers determine fair premiums and enables customers to better understand the factors influencing their insurance expenses.

This project demonstrates a complete Machine Learning workflow, including:

- Data preprocessing
- Exploratory Data Analysis (EDA)
- Feature engineering
- Model training
- Performance evaluation
- Comparison of boosting algorithms

---

# 🎯 Problem Statement

Predict the **medical insurance charges** for an individual using demographic and lifestyle information.

The project compares three state-of-the-art boosting algorithms to determine which provides the most accurate predictions.

---

# 📂 Project Structure

```text
Medical-Insurance-Boosting/
│
├── data/
│   └── insurance_pre.csv
│
├── notebooks/
│   └── Boosting_Algorithms.ipynb
│
├── README.md
│
└── requirements.txt
```

---

# 📊 Dataset

The dataset contains **1,338 customer records**.

| Feature | Description |
|----------|-------------|
| Age | Age of the customer |
| Sex | Gender |
| BMI | Body Mass Index |
| Children | Number of dependent children |
| Smoker | Smoking status |
| Region | Residential region |
| Charges | Medical insurance cost (Target Variable) |

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- LightGBM

---

# 🔄 Machine Learning Workflow

## 1. Data Loading

- Load the insurance dataset
- Inspect the data structure

---

## 2. Exploratory Data Analysis (EDA)

- Dataset overview
- Missing value check
- Duplicate record analysis
- Statistical summary

---

## 3. Data Preprocessing

- Remove duplicate records
- Encode categorical variables
- Prepare input features and target variable

---

## 4. Train-Test Split

Split the dataset into training and testing sets.

```python
train_test_split(test_size=0.2, random_state=42)
```

---

## 5. Model Training

The following boosting algorithms are implemented:

### ✅ AdaBoost Regressor

- Uses Decision Trees as weak learners
- Sequentially improves prediction errors

### ✅ XGBoost Regressor

- Optimized Gradient Boosting implementation
- Fast and highly accurate
- Regularization helps prevent overfitting

### ✅ LightGBM Regressor

- Histogram-based Gradient Boosting
- Leaf-wise tree growth
- Optimized for speed and memory efficiency

---

## 6. Model Evaluation

Models are evaluated using:

- R² Score
- Prediction accuracy comparison

The best-performing boosting algorithm is selected based on the evaluation results.

---

# 📈 Algorithms Compared

| Algorithm | Description |
|-----------|-------------|
| AdaBoost | Sequential ensemble learning using weak learners |
| XGBoost | Regularized gradient boosting with high predictive power |
| LightGBM | Fast, memory-efficient gradient boosting framework |

---

# 🌟 Why Boosting Algorithms?

Boosting combines multiple weak learners to create a strong predictive model.

Benefits include:

- Higher prediction accuracy
- Reduced bias
- Better handling of nonlinear relationships
- Improved generalization on unseen data

---

# ✅ Advantages

### AdaBoost

- Easy to understand
- Improves weak learners
- Effective for small to medium datasets

### XGBoost

- Excellent predictive performance
- Built-in regularization
- Handles missing values efficiently
- Highly optimized for speed

### LightGBM

- Very fast training
- Low memory consumption
- Scales well to large datasets
- Excellent for high-dimensional data

---

# ❌ Limitations

### AdaBoost

- Sensitive to noisy data and outliers
- May underperform on complex datasets

### XGBoost

- More hyperparameters to tune
- Longer training time compared to LightGBM

### LightGBM

- Can overfit on very small datasets
- Leaf-wise growth requires careful parameter tuning

---

# ▶️ How to Run

## Clone the repository

```bash
git clone <repository-url>
```

## Install dependencies

```bash
pip install pandas numpy matplotlib scikit-learn xgboost lightgbm
```

## Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Boosting_Algorithms.ipynb
```

Run all cells sequentially.

---

# 📦 Project Output

The notebook provides:

- Cleaned dataset
- Trained AdaBoost model
- Trained XGBoost model
- Trained LightGBM model
- Model performance comparison
- Best-performing boosting algorithm

---

# 📚 Learning Outcomes

This project demonstrates how to:

- Perform Exploratory Data Analysis (EDA)
- Preprocess structured datasets
- Encode categorical variables
- Build regression models using boosting techniques
- Compare multiple ensemble learning algorithms
- Evaluate regression performance using R² Score
- Select the most suitable boosting algorithm for prediction tasks

---

# 🚀 Future Improvements

- Hyperparameter tuning using GridSearchCV or RandomizedSearchCV
- Feature importance visualization
- SHAP model explainability
- Cross-validation analysis
- Model deployment using Flask or FastAPI
- MLflow experiment tracking

---

# 👨‍💻 Author

**Kannadoss**

**Module Lead – RPA | Machine Learning Enthusiast**

### Skills

- Python
- Machine Learning
- Data Science

---

# ⭐ Support

If you found this project useful, consider giving the repository a **Star ⭐**.

Your support helps improve and maintain future Machine Learning projects.
