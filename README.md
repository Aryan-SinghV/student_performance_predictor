# Student Performance Predictor

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](#)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Latest-orange.svg)](#)
[![Pandas](https://img.shields.io/badge/pandas-Data%20Analysis-lightgrey.svg)](#)

*A machine learning project to predict secondary education outcomes based on demographic and academic features.*

</div>

---

## Overview
This project focuses on predicting student performance in secondary education using machine learning[cite: 4]. Specifically, it predicts whether a student will achieve a passing final grade in a Math course based on various demographic, social, and academic features[cite: 4, 5]. 

## Dataset
The dataset utilized is `student-mat.csv`, which contains information on students enrolled in a Math course[cite: 4, 5]. It includes 33 initial attributes covering student backgrounds, family details, study habits, health, absences, and previous grades[cite: 4, 5]. The target variable is `G3`, which represents the student's final grade[cite: 5].

<details>
<summary><strong>Click to expand: Key Dataset Attributes</strong></summary>
<br>

* **school**: Student's school (binary)[cite: 5]
* **sex**: Student's sex (binary)[cite: 5]
* **address**: Home address type (binary: Urban or Rural)[cite: 5]
* **Medu / Fedu**: Mother's and Father's education level[cite: 5]
* **Mjob / Fjob**: Mother's and Father's job[cite: 5]
* **studytime**: Weekly study time (numeric)[cite: 5]
* **absences**: Number of school absences[cite: 5]
* **G1 / G2**: First and second period grades[cite: 5]
* **G3**: Final grade (target variable)[cite: 5]

</details>

## Data Preprocessing
To prepare the dataset for the classifier, the following exploratory data analysis and preprocessing steps were performed[cite: 4]:

* **Target Variable Binarization**: The final grade (`G3`), which originally ranges from 0 to 20, was discretized[cite: 4, 5]. Using a 40% passing criterion, a threshold of 8 was established: grades of 8 or higher were classified as a pass (1), and grades below 8 as a fail (0)[cite: 4].
* **Missing Value Imputation**: The dataset was checked for missing values. Any missing numeric values were filled using the column's mean, while missing categorical values were filled using the column's mode[cite: 4].
* **Categorical Encoding**: 
  * Binary categorical variables were transformed using `LabelEncoder`[cite: 4].
  * Nominal categorical variables were converted using One-Hot Encoding via pandas' `get_dummies`[cite: 4].
* **Feature Scaling**: All numeric features (excluding the target variable `G3`) were standardized using `StandardScaler` to ensure uniform scaling across the dataset[cite: 4].

## Model Training
* **Data Split**: The processed dataset was split into a training set (80%) and a testing set (20%) using a random state of 42 for reproducibility[cite: 4].
* **Algorithm**: A Random Forest Classifier was trained on the data using 200 estimators (`n_estimators=200`) and a random state of 42[cite: 4].

## Results
The Random Forest model demonstrated strong predictive capabilities on the unseen test set[cite: 4]. 

### Accuracy: **88.61%**[cite: 4]

### Confusion Matrix
| Metric | Count | Description |
| :--- | :---: | :--- |
| **True Positives** | `53` | Correctly predicted pass[cite: 4] |
| **True Negatives** | `17` | Correctly predicted fail[cite: 4] |
| **False Positives** | `5` | Incorrectly predicted pass[cite: 4] |
| **False Negatives** | `4` | Incorrectly predicted fail[cite: 4] |

## Dependencies
The notebook requires the following Python libraries[cite: 4]:
* `numpy`[cite: 4]
* `pandas`[cite: 4]
* `seaborn`[cite: 4]
* `matplotlib`[cite: 4]
* `scikit-learn`[cite: 4]

---
<div align="center">
  <i>Generated for the Student Performance Predictor repository.</i>
</div>
