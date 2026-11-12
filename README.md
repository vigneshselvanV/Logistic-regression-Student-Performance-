# Student Performance Prediction using Logistic Regression

A beginner-friendly Machine Learning project that predicts whether a student will **Pass or Fail** using the UCI Student Performance dataset and Logistic Regression.

## Project Overview

This project uses student demographic, family, school, and academic information to classify a student's final result.

The target is created from the final Portuguese subject grade (`G3`):

- **Pass (`1`)**: `G3 >= 10`
- **Fail (`0`)**: `G3 < 10`

The notebook uses a Logistic Regression model from Scikit-learn.

## Dataset

- **Dataset:** Student Performance
- **Source:** UCI Machine Learning Repository
- **Link:** https://archive.ics.uci.edu/dataset/320/student+performance
- **File used:** `student-por.csv` (Portuguese language subject)
- **Dataset size:** 649 rows and 33 original columns

Download the dataset from the UCI page and place `student-por.csv` in the same folder as the notebook.

The CSV file uses semicolons as separators, so the notebook loads it with `sep=";"`.

## Technologies and Libraries

- Python
- Pandas — data loading and preparation
- Matplotlib — plotting
- Seaborn — confusion matrix visualization
- Scikit-learn — data splitting, scaling, Logistic Regression, and evaluation
- Jupyter Notebook

## Project Workflow

1. Import the required Python libraries.
2. Load `student-por.csv`.
3. Create a Pass/Fail target using the final grade (`G3`).
4. Separate the input features (`X`) and target (`y`).
5. Convert categorical text columns into numeric columns using `pd.get_dummies()`.
6. Split the data into training and testing sets (80% / 20%).
7. Standardize the features using `StandardScaler`.
8. Create and train a Logistic Regression model.
9. Predict results for the test set.
10. Evaluate the model using accuracy, a classification report, and a confusion matrix.

## Model Results

Results recorded in the notebook's current run:

| Metric | Result |
|---|---:|
| Test samples | 130 |
| Correct predictions | 118 |
| Incorrect predictions | 12 |
| Accuracy | **90.77%** |

### Confusion Matrix

Rows represent the actual result; columns represent the predicted result.

| Actual / Predicted | Fail | Pass |
|---|---:|---:|
| Fail | 13 | 7 |
| Pass | 5 | 105 |

### Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| Fail | 0.72 | 0.65 | 0.68 | 20 |
| Pass | 0.94 | 0.95 | 0.95 | 110 |

The model performs better at identifying Pass students than Fail students. Accuracy alone does not tell the whole story, especially because the test set contains many more Pass cases than Fail cases.

*These are the results from one train/test split. Your results may differ if the data or model settings change.*

## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
cd YOUR-REPOSITORY
```

Replace the URL and folder name with your GitHub repository details.

### 2. Install the libraries

```bash
pip install pandas matplotlib seaborn scikit-learn jupyter
```

### 3. Download the dataset

Download `student-por.csv` from the [UCI Student Performance dataset page](https://archive.ics.uci.edu/dataset/320/student+performance) and place it beside the notebook.

### 4. Open the notebook

```bash
jupyter notebook Logistic_Regression.ipynb
```

Run the notebook cells from top to bottom.

## Important Note About the Prediction

This project includes `G1` and `G2` (earlier period grades) among its input features while predicting the final grade (`G3`). Therefore, it is a prediction made with earlier academic results available. It is **not** an early-year prediction made before any exams.

This is an educational project, not a tool for making high-stakes decisions about students. Predictions should not be used as the only basis for judging a student's ability or future performance.

## Repository Structure

```text
student-performance-prediction/
├── Logistic_Regression.ipynb
├── student-por.csv          # Download separately; do not commit unless permitted
└── README.md
```

## What I Learned

- The basics of Logistic Regression for classification.
- How to load and explore a dataset with Pandas.
- How to convert categorical data into numbers using one-hot encoding.
- Why we split data into training and testing sets.
- How `StandardScaler` standardizes features.
- How to evaluate a classification model using accuracy, precision, recall, F1-score, and a confusion matrix.

## Acknowledgements

Dataset: [UCI Machine Learning Repository — Student Performance](https://archive.ics.uci.edu/dataset/320/student+performance).

Created as a learning project while studying Machine Learning and Scikit-learn.
