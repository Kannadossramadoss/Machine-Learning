# Chronic Kidney Disease Prediction

## 📌 Project Overview

Chronic Kidney Disease (CKD) is a serious medical condition that can progressively affect kidney function. Early identification of CKD can help support timely medical evaluation and intervention.

This project develops a **Machine Learning classification model** to predict whether a patient is likely to have Chronic Kidney Disease based on multiple clinical parameters.

The project evaluates several machine learning algorithms and uses **GridSearchCV with 5-fold cross-validation** to tune their hyperparameters and select the final model.

> **Disclaimer:** This project is intended for educational and machine-learning demonstration purposes. It is not a medical diagnostic system and should not be used to make clinical decisions.

---

## 🎯 Problem Statement

The hospital management team requires a predictive model that can classify patients based on clinical parameters and predict whether the patient has **Chronic Kidney Disease (CKD)**.

The objective is to:

* Analyze the CKD dataset.
* Perform appropriate data preprocessing.
* Convert categorical variables into numerical features.
* Train multiple machine learning classification algorithms.
* Tune model hyperparameters using GridSearchCV.
* Evaluate the models using appropriate classification metrics.
* Select the best-performing model.
* Export the final model for prediction on new patient data.

---

## 📊 Dataset Information

The dataset contains:

* **399 patient records**
* **25 columns**
* **24 input features**
* **1 target variable**

### Target Variable

`classification`

| Value | Meaning                   |
| ----- | ------------------------- |
| `yes` | Chronic Kidney Disease    |
| `no`  | No Chronic Kidney Disease |

### Target Distribution

| Class          | Records | Percentage |
| -------------- | ------: | ---------: |
| CKD (`yes`)    |     249 |     62.41% |
| Not CKD (`no`) |     150 |     37.59% |

---

## 🧬 Features

The dataset contains the following clinical parameters:

| Feature          | Description             |
| ---------------- | ----------------------- |
| `age`            | Patient age             |
| `bp`             | Blood pressure          |
| `sg`             | Specific gravity        |
| `al`             | Albumin                 |
| `su`             | Sugar                   |
| `rbc`            | Red blood cells         |
| `pc`             | Pus cell                |
| `pcc`            | Pus cell clumps         |
| `ba`             | Bacteria                |
| `bgr`            | Blood glucose random    |
| `bu`             | Blood urea              |
| `sc`             | Serum creatinine        |
| `sod`            | Sodium                  |
| `pot`            | Potassium               |
| `hrmo`           | Hemoglobin              |
| `pcv`            | Packed cell volume      |
| `wc`             | White blood cell count  |
| `rc`             | Red blood cell count    |
| `htn`            | Hypertension            |
| `dm`             | Diabetes mellitus       |
| `cad`            | Coronary artery disease |
| `appet`          | Appetite                |
| `pe`             | Pedal edema             |
| `ane`            | Anemia                  |
| `classification` | Target variable         |

---

## 🔍 Data Preprocessing

The following preprocessing steps were performed:

### 1. Missing Value Check

All columns were checked for missing values.

The dataset used for modelling contained **no missing values after preprocessing**.

### 2. Duplicate Check

Duplicate records were checked.

```text
Number of duplicate rows: 0
```

### 3. Categorical Variables

The dataset contains categorical/object columns such as:

* `sg`
* `rbc`
* `pc`
* `pcc`
* `ba`
* `htn`
* `dm`
* `cad`
* `appet`
* `pe`
* `ane`

These categorical variables were converted into numerical features using **One-Hot Encoding**.

The encoded dataset contains **27 features**.

### 4. Target Encoding

The target variable `classification` was converted into binary values:

```text
1 → CKD
0 → Not CKD
```

### 5. Train-Test Split

The dataset was divided into:

```text
Training data: 319 records
Testing data : 80 records
```

### 6. Feature Scaling

Feature scaling was applied where required.

For Logistic Regression, KNN and SVM, scaling is incorporated inside a Pipeline so that the scaler is fitted independently within each cross-validation fold.

---

## 🤖 Machine Learning Algorithms

The following classification algorithms were evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. K-Nearest Neighbors (KNN)
5. Support Vector Machine (SVM)
6. Gradient Boosting

---

## ⚙️ Hyperparameter Tuning

To improve model performance, **GridSearchCV** was used for hyperparameter optimization.

The models were evaluated using:

```text
5-fold Cross-Validation
```

The primary model-selection metric was:

### Recall

Recall was selected as the primary metric because, in a CKD screening context, missing a patient with CKD (false negative) is particularly important.

Secondary metrics considered were:

* F1 Score
* ROC-AUC
* Accuracy
* Precision

The model-selection ranking was:

```text
Recall
   ↓
F1 Score
   ↓
ROC-AUC
   ↓
Accuracy
```

---

## 📈 Model Evaluation Metrics

The following metrics were used to evaluate the models.

### Accuracy

Measures the percentage of correctly classified patients.

### Precision

Measures how many patients predicted as CKD were actually CKD cases.

### Recall

Measures how many actual CKD cases were correctly identified.

### F1 Score

Provides a balance between Precision and Recall.

### ROC-AUC

Measures the model's ability to distinguish between CKD and non-CKD cases across classification thresholds.

---

## 🏆 Final Model

After hyperparameter tuning and cross-validation, the **Tuned Random Forest** model was selected as the final model.

### Final Test Results

| Metric    |       Score |
| --------- | ----------: |
| Accuracy  |  **98.75%** |
| Precision | **100.00%** |
| Recall    |  **98.00%** |
| F1 Score  |  **98.99%** |
| ROC-AUC   |  **99.93%** |

### Confusion Matrix

```text
[[30  0]
 [ 1 49]]
```

The confusion matrix indicates:

|                    | Predicted Not CKD | Predicted CKD |
| ------------------ | ----------------: | ------------: |
| **Actual Not CKD** |                30 |             0 |
| **Actual CKD**     |                 1 |            49 |

Therefore:

* True Negatives (TN) = 30
* False Positives (FP) = 0
* False Negatives (FN) = 1
* True Positives (TP) = 49

The model correctly identified **49 out of 50 CKD cases** in the test dataset.

---

## 💡 Why Random Forest Was Selected

The Tuned Random Forest model was selected based on the cross-validation model-selection criteria, with **Recall as the primary metric**.

The model also demonstrated excellent test-set performance:

* Very high Recall of **98%**
* Precision of **100%**
* F1 Score of **98.99%**
* ROC-AUC of **99.93%**
* Only **1 false-negative prediction**
* **0 false-positive predictions**

This combination makes the tuned Random Forest the selected model for this project.

---

## 💾 Model Export

The final trained model is exported using Joblib.

Example:

```python
joblib.dump(
    final_model,
    "../models/final_ckd_model_gridsearch.pkl"
)
```

The feature-column order is also saved:

```python
joblib.dump(
    X_encoded.columns.tolist(),
    "../models/ckd_feature_columns.pkl"
)
```

This allows the same feature structure to be used during deployment.

---

## 🚀 Prediction / Deployment

The exported model can be loaded using:

```python
loaded_model = joblib.load(
    "../models/final_ckd_model_gridsearch.pkl"
)
```

The saved feature columns can be loaded using:

```python
loaded_feature_columns = joblib.load(
    "../models/ckd_feature_columns.pkl"
)
```

A new patient's clinical information can then be transformed using the same encoding structure and passed to the trained model for prediction.

Example output:

```text
===================================
       CKD PREDICTION RESULT
===================================
Prediction: CKD
===================================
```

---

## 📁 Project Structure

Recommended project structure:

```text
Chronic-Kidney-Disease-Prediction/
│
├── data/
│   └── chronic_kidney_disease.csv
│
├── notebooks/
│   └── CKD_Prediction_Updated_GridSearch_Final.ipynb
│
├── models/
│   ├── final_ckd_model_gridsearch.pkl
│   └── ckd_feature_columns.pkl
│
├── README.md
│
└── requirements.txt
```

---

## 🛠️ Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

---

## 📦 Installation

Clone the repository and install the required Python packages.

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open the CKD prediction notebook and run the cells sequentially.

---

## 🔄 Machine Learning Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Missing Value Check
   ↓
Duplicate Check
   ↓
Exploratory Data Analysis
   ↓
Categorical Encoding
   ↓
Target Encoding
   ↓
Train-Test Split
   ↓
Feature Scaling / Pipelines
   ↓
Baseline Models
   ↓
GridSearchCV
   ↓
5-Fold Cross-Validation
   ↓
Model Comparison
   ↓
Final Model Selection
   ↓
Test Set Evaluation
   ↓
Model Export
   ↓
Deployment / Prediction
```

---

## ⚠️ Limitations

Although the model achieved very high performance on the available test dataset, the dataset contains only **399 records**.

Therefore:

* The results may not generalize to all patient populations.
* Test-set performance should not be interpreted as clinical accuracy.
* Independent external validation is required.
* The model should not be used as a substitute for professional medical diagnosis.

---

## 🔮 Future Improvements

Possible future enhancements include:

* Testing the model on an independent CKD dataset.
* Performing external validation.
* Applying more extensive feature engineering.
* Evaluating additional algorithms.
* Using probability calibration.
* Performing explainability using SHAP or similar techniques.
* Building a web interface using Streamlit or Flask.
* Adding automated model monitoring.
* Evaluating performance across different patient subgroups.

---

## 👤 Project Objective

The primary objective of this project is to demonstrate how machine learning can be applied to structured clinical data to develop a predictive classification model for Chronic Kidney Disease.

The project demonstrates the complete machine-learning workflow from **data preprocessing and model training through hyperparameter tuning, evaluation, model selection, and deployment**.
