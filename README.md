# ❤️ Heart Disease Prediction

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Neural%20Network-orange?logo=tensorflow)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> A machine learning project that compares multiple classification algorithms to predict the presence of heart disease in patients, identifying the most accurate model through systematic evaluation.

---

## 📌 Project Overview

Heart disease is one of the leading causes of death worldwide. Early and accurate prediction can significantly improve patient outcomes. This project builds and compares five machine learning models on clinical patient data to determine which algorithm best predicts heart disease.

**Models compared:**
- K-Nearest Neighbours (KNN)
- Support Vector Machine (SVM) with GridSearchCV tuning
- Random Forest Classifier
- Multi-Layer Perceptron (MLP / Neural Network via TensorFlow/Keras)
- Voting Classifier (ensemble of the above models)

---

## 📊 Dataset

**File:** `heart.csv`  
**Source:** [Kaggle Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)  
**Rows:** 918 patients | **Columns:** 12 features

| Feature | Description |
|---------|-------------|
| `Age` | Patient age |
| `Sex` | M = Male, F = Female |
| `ChestPainType` | Type of chest pain (ASY, ATA, NAP, TA) |
| `RestingBP` | Resting blood pressure (mm Hg) |
| `Cholesterol` | Serum cholesterol (mm/dl) |
| `FastingBS` | Fasting blood sugar > 120 mg/dl (1 = True) |
| `RestingECG` | Resting ECG results |
| `MaxHR` | Maximum heart rate achieved |
| `ExerciseAngina` | Exercise-induced angina (Y/N) |
| `Oldpeak` | ST depression induced by exercise |
| `ST_Slope` | Slope of peak exercise ST segment |
| `HeartDisease` | Target — 1 = Heart disease, 0 = Normal |

**Class balance:** ~55% positive (heart disease), ~45% negative — well balanced, no resampling required.

---

## 🔬 Methodology

### 1. Exploratory Data Analysis (EDA)
- Checked for missing values — none found
- Visualised class balance (pie chart)
- Analysed key feature relationships (cholesterol vs heart disease, etc.)
- Identified gender distribution: ~79% Male, ~21% Female

### 2. Data Preprocessing
- **Categorical encoding** — converted Sex, ChestPainType, RestingECG, ExerciseAngina, ST_Slope to numeric
- **Feature scaling** — applied MinMaxScaler to normalise all features to [0, 1]
- **Feature selection** — VarianceThreshold to remove zero-variance features
- **Train/test split** — standard 80/20 split

### 3. Model Training & Evaluation
Each model was trained on the training set and evaluated on the test set using:
- **Confusion Matrix** — visualises true/false positives and negatives
- **Recall Score** — prioritised because in medical diagnosis, false negatives (missing a sick patient) are more costly than false positives

### 4. Hyperparameter Tuning
- **SVM** — tuned using `GridSearchCV` to find optimal C and gamma parameters

### 5. Ensemble Model
- Combined the best-performing individual models into a **Voting Classifier** to improve robustness and reduce variance

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3.x** | Core language |
| **pandas / numpy** | Data manipulation |
| **matplotlib / seaborn** | Visualisation |
| **scikit-learn** | KNN, SVM, Random Forest, Voting Classifier, GridSearchCV |
| **TensorFlow / Keras** | MLP neural network |
| **Jupyter Notebook** | Development environment |

---

## ⚙️ How to Run

### Install dependencies
```bash
pip install -r requirements.txt
```

### Run the notebook
Open `heart_disease_prediction.ipynb` in Jupyter and run all cells top to bottom.

---

## 📁 Files

```
Heart-Disease-Prediction/
├── heart_disease_prediction.ipynb  ← Full ML pipeline
├── heart.csv                       ← Dataset
└── requirements.txt                ← Dependencies
```

---

## 💡 Key Findings

- Cholesterol alone is **not** a reliable predictor of heart disease (contrary to common expectation)
- The dataset is male-dominated (~79%), which may affect generalisation to female patients
- The ensemble Voting Classifier outperforms individual models by combining their strengths
- Recall was prioritised over accuracy — in clinical settings, missing a heart disease case is more dangerous than a false alarm

---

## 👤 Author

**Oluwatosin Eleja** — Data Analyst & Data Engineer

[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/Toludills)
