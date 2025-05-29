# Titanic Survival Prediction

This project uses machine learning to predict passenger survival on the Titanic based on various features such as passenger class, sex, age, fare, and family details.

## Project Overview

The goal is to build models that predict whether a passenger survived the Titanic disaster. The dataset contains demographic and travel-related information.

## Dataset

- Source: [Kaggle Titanic Dataset](https://www.kaggle.com/competitions/titanic/data)
- Training data contains features like `Pclass`, `Sex`, `Age`, `Fare`, `SibSp`, `Parch`, `Embarked`, etc., with the target variable `Survived`.
- Test data is used for final predictions.

## Competition Details

This project was developed as part of the [Kaggle Titanic Machine Learning Competition](https://www.kaggle.com/competitions/titanic).

- **Final Score:** 0.77990 (Accuracy Score)

This experience helped me apply machine learning techniques on a real-world dataset and improve my skills in data preprocessing, feature engineering, model selection, and evaluation.

## Steps in the Project

### 1. Data Cleaning & Missing Value Imputation
- Filled missing values in `Age` using median.
- Filled missing values in `Fare` (test data) using median.
- Filled missing values in `Embarked` (train data) with the most frequent port.

### 2. Feature Engineering
- Created `FamilySize` = `SibSp` + `Parch` + 1
- Created binary feature `IsAlone` indicating if passenger was alone.
- Extracted `Title` from passenger names (e.g., Mr, Mrs, Miss).
- Binned `Age` into categories: Child, Teen, Adult, MiddleAge, Senior.
- Binned `Fare` into quartiles with labels: Low, Medium, High, Very_High.

### 3. Feature Selection
- Dropped unnecessary columns: `Ticket`, `Cabin`, `Name`, `SibSp`, `Parch`, `Age`, and `Fare` after binning.
- Selected categorical and numerical features for modeling.

### 4. Data Preprocessing
- Used `ColumnTransformer` to:
  - Scale numerical features (`FamilySize`, `IsAlone`) with `StandardScaler`.
  - One-hot encode categorical features (`Sex`, `Title`, `AgeBin`, `FareBin`, `Embarked`, `Pclass`).

### 5. Model Training & Evaluation
- Split data into training and validation sets.
- Trained multiple models:
  - Logistic Regression
  - Random Forest
  - Gradient Boosting
  - Support Vector Machine
  - Decision Tree
  - K-Nearest Neighbors
  - Naive Bayes
  - Extra Trees Classifier
- Evaluated models using precision, recall, F1-score, and accuracy.
- Selected the best-performing model based on F1-score and balanced metrics.

### 6. Hyperparameter Tuning
- Performed GridSearchCV on selected models (e.g., Random Forest) to optimize hyperparameters.

### 7. Final Predictions
- Applied the full preprocessing and model pipeline to the test dataset.
- Produced survival predictions for submission.


