# Student Focus Drop-Off Prediction using Machine Learning

## Project Overview

Student disengagement is a major challenge for online learning platforms. Learners often gradually reduce their activity before completely dropping out of a course.

This project develops an end-to-end Machine Learning pipeline that predicts whether a student is likely to disengage within the next 7 days using behavioral learning activity data. The project covers the complete ML lifecycle, including data generation, exploratory data analysis, data preprocessing, feature engineering, model training, hyperparameter tuning, evaluation, and failure analysis.

---

## Problem Statement

Predict whether a student will become inactive in the next 7 days based on recent engagement behavior.

### Target Variable

| Value | Meaning                |
| ----- | ---------------------- |
| 0     | Student remains active |
| 1     | Student drops off      |

---

## Project Workflow

```text
Data Generation
      ↓
Exploratory Data Analysis
      ↓
Data Cleaning
      ↓
Data Preprocessing
      ↓
Feature Engineering
      ↓
Model Training
      ↓
Hyperparameter Tuning
      ↓
Model Evaluation
      ↓
Failure Analysis
```

---

## Dataset

A synthetic dataset was generated to simulate realistic student engagement behavior in an online learning environment.

### Features

* videos_watched_14d
* avg_watch_pct
* avg_session_minutes
* login_days_14d
* assignments_submitted
* avg_submission_delay
* quiz_score_avg
* quiz_score_trend
* forum_activity
* last_active_days_ago

### Target

* drop_off

---

## Notebooks

### 1_data_genration.ipynb

Dataset generation notebook.

Tasks:

* Create synthetic student engagement data
* Generate behavioral features
* Simulate disengagement labels
* Export dataset

Output:

* student_focus_dropoff.csv

---

### 2_eda.ipynb

Exploratory Data Analysis.

Tasks:

* Dataset inspection
* Statistical summaries
* Distribution analysis
* Class balance analysis
* Visualization of behavioral patterns

---

### 3_data_clearning.ipynb

Data cleaning and validation.

Tasks:

* Missing value checks
* Duplicate detection
* Range validation
* Data type verification
* Data quality assessment

Output:

* student_focus_dropoff_cleaned.csv

---

### 4_data_processing.ipynb

Data preprocessing pipeline.

Tasks:

* Train-test split
* One-hot encoding
* Feature scaling
* Scikit-learn preprocessing pipeline

---

### 5_engineering.ipynb

Feature engineering.

Created Features:

* videos_per_login
* assignment_delay_flag
* low_session_quality
* inactive_risk
* low_quiz_score

Output:

* student_focus_dropoff_engineered.csv

---

### 6_pipeline.ipynb

Model development and evaluation.

Tasks:

* Logistic Regression baseline
* Gradient Boosting model
* Hyperparameter tuning using GridSearchCV
* Model evaluation
* Failure analysis
* Model persistence

Outputs:

* best_student_dropoff_model.pkl
* final_student_dropoff_model.pkl

---

## Machine Learning Pipeline

### Data Preprocessing

Numerical Features:

* StandardScaler

Categorical Features:

* OneHotEncoder

Train-Test Split:

* 80% Training
* 20% Testing
* Stratified sampling

---

## Models Used

### Baseline Model

* Logistic Regression

### Advanced Model

* Gradient Boosting Classifier

### Hyperparameter Tuning

GridSearchCV with Stratified K-Fold Cross Validation

Optimized Parameters:

* n_estimators
* learning_rate
* max_depth

Optimization Metric:

* Recall

Reason:
Missing a disengaged student is more costly than incorrectly flagging an active student.

---

## Evaluation Metrics

The following metrics were used:

* Recall
* Precision
* F1 Score
* Confusion Matrix
* ROC Curve
* Precision-Recall Curve

---

## Failure Analysis

A structured failure analysis was conducted to understand model limitations.

### Identified Failure Cases

#### Cold-Start Students

Students with limited historical activity data.

#### Weekend-Only Learners

Students who study irregularly and exhibit non-standard engagement patterns.

#### High Performers with Low Engagement

Students with strong quiz performance but declining activity.

#### Hidden Engagement Decline

Students whose activity decreases gradually while remaining above predefined thresholds.

---

## Key Insights

* Engagement frequency is a strong predictor of future inactivity.
* Recent activity has significant influence on predictions.
* Behavioral patterns are more informative than individual performance metrics.
* Ensemble models outperform linear models for disengagement prediction.

---

## Files Included

```text
.
├── 1_data_genration.ipynb
├── 2_eda.ipynb
├── 3_data_clearning.ipynb
├── 4_data_processing.ipynb
├── 5_engineering.ipynb
├── 6_pipeline.ipynb
├── README.md
├── best_student_dropoff_model.pkl
├── final_student_dropoff_model.pkl
├── student_focus_dropoff.csv
├── student_focus_dropoff_cleaned.csv
└── student_focus_dropoff_engineered.csv
```

---

## Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn
* Joblib

---

## Resume Highlights

* Built a binary classification model to predict student disengagement 7 days in advance using behavioral activity data.
* Developed an end-to-end machine learning pipeline in Python with recall optimization for early intervention.
* Conducted comprehensive failure analysis identifying edge cases including cold-start problems, weekend-only learners, and high-performing low-engagement students.
* Visualized behavioral trends and model performance using Matplotlib and Seaborn to support interpretable predictions.

---

## Future Improvements

* Time-series feature engineering
* LSTM-based engagement prediction
* Personalized student baselines
* Automated retraining pipeline
* Model monitoring and drift detection

---



Machine Learning | Data Analytics | Generative AI
