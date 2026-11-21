# An Empirical Comparison of Multilayer Perceptron Based Test Case Prioritization in Continuous Integration Environments

## 1. Project Overview

This repository contains the implementation and experimental resources for the research paper titled:

**An Empirical Comparison of Multilayer Perceptron Based Test Case Prioritization in Continuous Integration Environments**

The study investigates the performance of a Multilayer Perceptron (MLP) classifier for Test Case Prioritization (TCP) in Continuous Integration (CI) regression testing environments.

The proposed experimental framework compares MLP with five conventional machine learning classifiers under consistent experimental conditions.

## 2. Machine Learning Models

Six machine learning classifiers are implemented and evaluated:

- Multilayer Perceptron (MLP)
- Random Forest (RF)
- Extreme Gradient Boosting (XGBoost)
- Logistic Regression (LR)
- Support Vector Machine (SVM)
- k-Nearest Neighbors (k-NN)

## 3. Datasets

The study uses four industrial software testing datasets:

| Dataset | Role in the study |
|---|---|
| ABB Robotics (`tcp.csv`) | Primary experimental dataset |
| IOFROL | Generalisation evaluation |
| PAINTCONTROL | Generalisation evaluation |
| Westermo Network Technologies | Generalisation evaluation |

The Westermo dataset was obtained from a collection containing nine system-specific files. The study used the first system dataset, as described in the manuscript.

Original dataset sources are acknowledged in the research paper. Dataset access information and any processed data that can legally be redistributed will be documented in this repository.

## 4. Data Preprocessing

The preprocessing workflow includes the data preparation and feature engineering procedures described in the manuscript, including:

- Handling missing values.
- Removing duplicate records.
- Encoding categorical variables.
- Removing irrelevant and zero-variance features.
- Applying logarithmic transformation to the Duration attribute.
- Feature scaling using StandardScaler.
- Stratified training and testing data partitioning.
- Handling class imbalance through class weighting.

Preprocessing is implemented to avoid data leakage by fitting transformations using training data.

## 5. Experimental Configuration

The primary ABB dataset is divided using a stratified 80:20 training and testing split.

Hyperparameter optimisation is performed using GridSearchCV with five-fold cross-validation.

The MLP configuration investigated includes variations in:

- Hidden-layer architecture.
- Activation functions.
- Learning rate.
- Batch size.
- Other relevant training parameters.

The selected MLP configuration reported in the study uses two hidden layers with 64 and 32 neurons, ReLU activation and a learning rate of 0.001.

## 6. Evaluation Metrics

The classifiers are evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Average Percentage of Faults Detected (APFD)

APFD is used to evaluate the effectiveness of the prioritised test execution order in detecting faults early.

## 7. Statistical Analysis

The study applies bootstrap-based statistical analysis using 1,000 iterations and pairwise Wilcoxon signed-rank testing to compare MLP against the baseline classifiers.

The statistical analysis is intended to assess the significance and effect sizes of observed differences in APFD performance.

## 8. Repository Organisation

The repository will contain the following implementation resources as they are uploaded:

```text
MLP-TCP-Comparative-Study/
│
├── README.md
├── data/
│   ├── original/
│   └── processed/
│
├── preprocessing/
│
├── models/
│   ├── mlp/
│   ├── random_forest/
│   ├── xgboost/
│   ├── logistic_regression/
│   ├── svm/
│   └── knn/
│
├── experiments/
│
├── evaluation/
│
├── statistical_analysis/
│
├── results/
│
└── requirements.txt
```

The directory structure will be updated to match the actual implementation files included in the repository.

## 9. Reproducibility

The repository is intended to support transparency and reproducibility of the experiments.

Researchers should consult the preprocessing scripts, model implementation files, experimental configurations and evaluation scripts when reproducing the results.

Software dependencies and version information will be provided in `requirements.txt`.

## 10. Citation

For questions concerning the implementation, please contact the corresponding author using the contact information provided in the research paper.
