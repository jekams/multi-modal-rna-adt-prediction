# multi-modal-rna-adt-prediction
Machine-learning research project using paired RNA and ADT single-cell multi-modal data to predict protein expression and compare predictive modeling approaches.
# Multi-Modal RNA-to-Protein Prediction Using Machine Learning

# Overview

This project investigates the use of machine-learning methods to predict protein-level measurements from RNA expression data using paired single-cell multi-modal datasets. The analysis uses RNA expression and antibody-derived tag (ADT) measurements to investigate predictive relationships between transcriptomic and protein-level information.

The project was conducted as part of graduate-level Data Science and Analytics coursework and provided hands-on experience applying predictive analytics, regression modeling, dimensional representation, model comparison, and hyperparameter optimization to complex biomedical data.

# Research Objective

The objective of this project was to investigate whether information contained in RNA expression profiles could be used to predict corresponding ADT protein measurements.

The prediction problem can be represented as:

**RNA expression data → Machine-learning model → Predicted ADT/protein expression**

The project therefore focuses on learning relationships between two complementary biological data modalities.

# Dataset

The analysis uses paired RNA and ADT datasets.

**RNA data:** transcriptomic expression measurements
**ADT data:** antibody-derived tag measurements representing protein-level information

The project used 4,000 observations for model development and internal evaluation, with 3,000 observations used for training and 1,000 observations used for testing/model comparison.

The original datasets are not included in this repository where their redistribution may be restricted. Users should obtain the authorized datasets separately before reproducing the analysis.

# Methodology

The analysis followed several stages:

1. Imported RNA and ADT datasets using Python, Pandas, and NumPy.
2. Constructed training and validation subsets while maintaining correspondence between the RNA and ADT observations.
3. Established Ordinary Least Squares linear regression as a baseline predictive model.
4. Evaluated Non-negative Matrix Factorization (NMF) as an alternative representation and prediction approach.
5. Compared multiple regression algorithms.
6. Evaluated models using Mean Squared Error (MSE) and Pearson correlation.
7. Identified strong-performing models for further optimization.
8. Performed hyperparameter tuning for Support Vector Regression (SVR) using an RBF kernel.
9. Trained the selected model using the available training data.
10. Generated predictions for the final evaluation dataset.

# Models Evaluated

The project compared the following approaches:

* Linear Regression
* Non-negative Matrix Factorization
* LightGBM
* XGBoost
* Bayesian Ridge
* Ridge Regression
* Lasso Regression
* Support Vector Regression
* Elastic Net
* K-Nearest Neighbors Regression
* Decision Tree Regression
* Gradient Boosting Regression
* AdaBoost Regression

# Model Evaluation

Model performance was evaluated using:

# Mean Squared Error (MSE)

MSE measures the average squared difference between observed and predicted values, with larger errors receiving greater penalty.

# Pearson Correlation

Pearson correlation was used to measure the strength of the linear association between the predicted and observed ADT measurements.

#Results

The comparative analysis demonstrated substantial differences in predictive performance among the evaluated algorithms.

| Model             |   MSE | Pearson Correlation |
| ----------------- | ----: | ------------------: |
| LightGBM          | 0.125 |           **0.853** |
| Gradient Boosting | 0.130 |               0.846 |
| SVR               | 0.142 |               0.833 |
| XGBoost           | 0.142 |               0.831 |
| Bayesian Ridge    | 0.153 |               0.816 |
| Ridge             | 0.171 |               0.798 |
| AdaBoost          | 0.192 |               0.795 |
| KNN Regression    | 0.271 |               0.707 |
| Decision Tree     | 0.284 |               0.694 |
| Elastic Net       | 0.377 |               0.472 |
| Lasso             | 0.424 |               0.311 |

LightGBM produced the strongest Pearson correlation among the initial models evaluated, with a correlation of approximately 0.853 and an MSE of approximately 0.125.

Support Vector Regression was subsequently investigated because it provided strong predictive performance with comparatively lower computational time than some boosting approaches. Hyperparameter tuning was performed using an RBF kernel, with the best evaluated configuration producing a Pearson correlation of approximately 0.850.

## Key Findings

The analysis demonstrated that:

* RNA expression contains predictive information associated with ADT measurements.
* Different machine-learning approaches produced substantially different predictive performance.
* Tree-based boosting methods performed strongly on the evaluated dataset.
* Support Vector Regression provided a competitive alternative and benefited from hyperparameter optimization.
* Model selection should consider both predictive performance and computational efficiency.

## Technical Skills Demonstrated

This project demonstrates practical experience with:

**Programming**

* Python
* NumPy
* Pandas

**Machine Learning**

* Regression
* Support Vector Regression
* Gradient Boosting
* XGBoost
* LightGBM
* Regularization
* K-Nearest Neighbors
* Decision Trees
* Matrix Factorization

**Model Evaluation**

* Pearson correlation
* Mean Squared Error
* Model comparison
* Hyperparameter tuning

**Biomedical Data Science**

* Multi-modal data
* RNA expression data
* Protein/ADT measurements
* High-dimensional biological datasets
* Predictive modeling

# Research Relevance

This project provided practical experience applying machine-learning and predictive analytics to complex biomedical data. By investigating relationships between transcriptomic and protein-level measurements, the project demonstrated how computational methods can extract predictive information from complementary biological data modalities.

The experience contributes to my broader interest in developing data-driven predictive models for healthcare and biomedical applications, including the use of complex clinical and operational datasets to support improved healthcare decision-making.

# Reproducibility

The repository contains the analytical workflow, modeling methodology, and evaluation procedures used in the project.

Because the original dataset may be subject to course, competition, licensing, or redistribution restrictions, the raw RNA and ADT datasets are not included. Researchers attempting to reproduce the analysis should obtain the dataset through its authorized source.

# Author

**Jesse Maina**

M.S. Data Science and Analytics
Machine Learning | Predictive Analytics | Biomedical Data Science | Healthcare Analytics
