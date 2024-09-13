# Protein Abundance Prediction
## Project II: Protein Abundance Prediction
**Deadline:** June 10, 2024, 23:59

---

## Overview

### Data Description

The dataset pertains to pancreatic tissues, which contain various cell types, including alpha and beta cells, as well as cells related to blood supply and the immune system. Data are derived from multimodal single-cell RNA sequencing (scRNA-seq), which allows high-resolution study and differentiation of cell types.

The dataset includes two types of readings for each cell:
- **RNA Transcript Counts:** Expression levels of genes in each cell.
- **Protein Abundance:** Amount of surface protein CD361 in each cell.

The task is to predict the protein abundance based on gene expression data. This is crucial as many public datasets only provide RNA matrix data.

The data are sourced from human bone marrow donors, predominantly immune cells. Accurate identification of T lymphocytes using both data types could be foundational for developing targeted cancer therapies (e.g., CAR T cell therapy).

### Data Files

The dataset consists of the following CSV files:
- **X_train.csv:** RNA expression matrix for training. Rows represent cells, columns represent genes.
- **X_test.csv:** RNA expression matrix for testing.
- **y_train.csv:** Protein abundance for training cells corresponding to X_train.csv.

In this description, X_train.csv and y_train.csv will be referred to as training data, and X_test.csv as testing data.

### Submission Guidelines

Submit the following files on Moodle:
- **Report:** A Jupyter notebook (.ipynb) containing detailed solutions. Name your file as `[StudentID] report.ipynb` (e.g., 123456 report.ipynb).
- **Predictions:** A CSV file with predictions for the test data. Name your file as `[StudentID] prediction.csv` (e.g., 123456 prediction.csv).

Ensure the file names and contents match the required formats.

---

## Tasks

### 1. Exploration (7 points)

**(a)** Check the number of observations and variables in the training and testing data. Examine data types and perform necessary conversions. Verify data completeness.

**(b)** Analyze the empirical distribution of the target variable. Provide basic statistics and visualize the distribution with a histogram or density plot.

**(c)** Select the 250 features most correlated with the target variable. Compute correlations for these features and visualize the results with a heatmap.

**Note:** The subsequent analyses should use the full training dataset.

### 2. ElasticNet (7 points)

**(a)** Explain the ElasticNet model, including the parameters, objective function, and hyperparameters. Specify which hyperparameter values correspond to ridge regression and lasso.

**(b)** Define a hyperparameter grid with at least three values for each hyperparameter. Ensure the grid includes configurations for ridge regression and lasso. Use cross-validation to select the best hyperparameters, justifying the number of folds used.

**(c)** Report the training and validation errors of the ElasticNet model, averaged across all cross-validation folds.

### 3. Random Forests (8 points)

**(a)** Choose three hyperparameters for the Random Forest model. Define a 3D grid of hyperparameter combinations and use cross-validation to find the optimal values. Ensure the cross-validation split matches that used for ElasticNet.

**(b)** Summarize the cross-validation results for both ElasticNet and Random Forest models in a table. Compare the models and justify which performs better. Include a basic reference model that predicts the mean of the target variable.

### 4. Test Set Prediction (8 points)

**(a)** Develop a model of your choice to predict the target variable using the training data. Describe the model selection process and motivations in your report.

**(b)** Generate predictions for the test set and submit a CSV file with columns `Id` and `Expected`. Evaluate your model's performance using RMSE.

**Scoring Details:**
- **1 point:** For achieving a lower error than the reference model.
- **2 points:** For achieving a lower error than the ElasticNet model provided by the instructors.
- **5 points:** Bonus points based on the formula \( 12 \left\lfloor \frac{10Fb(e)}{3} \right\rfloor \), where \( e \) is the student's test error, and \( Fb \) is the empirical distribution function of errors from all submissions in the lab group.

---

## Notes

- Ensure all tasks are completed according to the instructions.
- Double-check file names and contents before submission.
- Late submissions will not be evaluated and will receive zero points.

Good luck with your project!
