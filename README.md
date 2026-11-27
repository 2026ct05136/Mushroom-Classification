# Mushroom Classification — Machine Learning Assignment

## 1. Problem Statement
Build and compare classifiers that predict whether a mushroom is edible or poisonous from its physical characteristics. This is a binary classification problem. Target `class`: `e` = edible (0), `p` = poisonous (1).

## 2. Dataset Description
- Dataset: Mushroom
- Source: UCI Machine Learning Repository
- Dataset page: https://archive.ics.uci.edu/dataset/73/mushroom
- Data file: https://archive.ics.uci.edu/ml/machine-learning-databases/mushroom/agaricus-lepiota.data
- Original instances: 8,124; input features: 22 categorical features
- Target: `class`
- Missing values are represented by `?` in the source (notably `stalk_root`).
- Class distribution was examined in the notebook.

The dataset meets the assignment's minimum feature and instance requirements and supports missing-value preprocessing.

## 3. GitHub Repository
https://github.com/2026ct05136/Mushroom-Classification

The repository should contain source code/notebook, `requirements.txt`, this README, `test_data.csv`, `model_results.csv`, and saved model files in `model/`.

## 4. Preprocessing and Experimental Setup
1. Load the UCI dataset.
2. Replace `?` with `NaN` and remove duplicate rows.
3. Separate target from features; encode edible as 0 and poisonous as 1.
4. Split data 80:20 using `random_state=42` and stratification.
5. Impute categorical missing values using the most frequent value, one-hot encode with unknown categories ignored, and apply standard scaling.
6. Fit preprocessing and classifier pipeline on training data, then evaluate on the held-out test data.

The preprocessing is included in each saved pipeline.

## 5. Models and Evaluation
Models: Logistic Regression; Decision Tree; K-Nearest Neighbors (`n_neighbors=5`); Gaussian Naive Bayes; Random Forest (`n_estimators=100`).

Metrics: Accuracy, AUC, Precision, Recall, F1-score, and Matthews Correlation Coefficient (MCC).

### Comparison Table
Values transcribed from the notebook's displayed test results, rounded to four decimals.

| Model | Accuracy | AUC | Precision | Recall | F1 | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 |
| Decision Tree | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 |
| KNN | 0.9988 | 1.0000 | 1.0000 | 0.9974 | 0.9987 | 0.9975 |
| Gaussian Naive Bayes | 0.9526 | 0.9963 | 0.9124 | 0.9974 | 0.9530 | 0.9091 |
| Random Forest | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 |

### Observations
- Logistic Regression achieved perfect metrics on this test split.
- Decision Tree achieved perfect metrics on this test split.
- KNN performed very strongly; recall was slightly below 1.
- Gaussian Naive Bayes had high AUC and recall, but lower precision and accuracy than the other models.
- Random Forest achieved perfect metrics on this test split.

### Overall Winner
By F1-score, Logistic Regression, Decision Tree, and Random Forest are tied at 1.0000; there is no single unique winner by this metric.

**Caution:** These are results on one test split, not a guarantee on new data. This academic classification experiment must not be used to decide whether wild mushrooms are safe to eat.

## 6. Visualization
The notebook includes a bar chart comparing the six evaluation metrics across the five models. Include it in the final PDF.

## 7. Execution Instructions
1. Open `mushroom_classification.ipynb` in Colab or Jupyter.
2. Install dependencies from `requirements.txt` if required.
3. Run notebook cells in order.
4. The notebook loads and preprocesses data, trains/evaluates models, plots metric comparisons, and exports test data/results.
5. Trained pipelines are saved as `.joblib` files in `model/`.

## 8. Repository Structure
```text
Mushroom-Classification/
├── mushroom_classification.ipynb
├── README.md
├── requirements.txt
├── test_data.csv
├── model_results.csv
└── model/
    ├── decision_tree.joblib
    ├── logistic_regression.joblib
    ├── random_forest.joblib
    ├── knn.joblib
    └── naive_bayes.joblib
```

## 9. BITS Virtual Lab Screenshot
Include the screenshot of assignment execution on BITS Virtual Lab in the final single-PDF submission, as required.

---
Review this README, personalize the observations in your own words, confirm the repository contains the listed files, and include the README content in your final PDF.
