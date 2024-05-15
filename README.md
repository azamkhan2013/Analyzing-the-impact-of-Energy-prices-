# Comparative Study: Design and Application of a Machine Learning System for a Practical Problem

## Overview

This repository contains the code and findings from my project titled "Comparative Study: Design and Application of a Machine Learning System for a Practical Problem," completed as part of the CE802 Machine Learning course at the University of Essex. The study focuses on using various machine learning models to solve a practical problem related to predicting customer behavior in the context of energy bills.

## Table of Contents

- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Model Selection and Evaluation](#model-selection-and-evaluation)
- [Results and Discussion](#results-and-discussion)
- [Conclusion](#conclusion)
- [Usage](#usage)
- [Requirements](#requirements)
- [Acknowledgments](#acknowledgments)

## Introduction

This report discusses the performance of various machine learning models and identifies the best model to predict whether customers had problems paying their energy bills due to increasing prices.

## Problem Statement

The goal is to predict whether a customer belongs to the class of people who had problems paying their energy bills during the last few months (TRUE indicates problems with paying bills).

## Exploratory Data Analysis

### Data Enrichment Steps

1. **Eliminate Redundant Observations**: No duplicates were found in the dataset.
2. **Fix Missing Data**: Missing values were identified and replaced with the mean using SimpleImpute.
3. **Visualization of Missing Values**: Heatmaps indicated that all features were negatively correlated with the target variable.
4. **Encoding**: Target variable values were converted from boolean to binary (1 and 0).

### Splitting the Dataset

The data was split into training (80%) and testing (20%) sets using the `train_test_split` function with a random state for reproducibility.

## Model Selection and Evaluation

### Decision Trees

- **Parameters**: `max_leaf_nodes` and `random_state`.
- **Evaluation**: 
  - Score: 0.895
  - Precision: 0.887
  - Recall: 0.896
- **Visualization**: Decision tree plot, ROC curve, and confusion matrix.

### Random Forest

- **Hyperparameters**: Tuned using GridSearchCV with parameters such as `n_estimators`, `max_features`, `max_depth`, `min_samples_split`, `min_samples_leaf`, and `bootstrap`.
- **Optimal Parameters**: 
  ```python
  {
    'bootstrap': False,
    'max_depth': 4,
    'max_features': 'auto',
    'min_samples_leaf': 2,
    'min_samples_split': 5,
    'n_estimators': 822
  }

- **Evaluation**: 
  - Score: 0.825
  - Precision: 0.837
  - Recall: 0.794
 
### Conclusion
The Decision Tree model was the best performing model and was successfully used to predict the test dataset. For predicting variations in annual expenditure due to energy cost increases, the Linear Regression model was identified as the best, with an R-squared score of 0.715.
