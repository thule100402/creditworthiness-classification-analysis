# Creditworthiness Classification & Analysis

## Overview

This project investigates creditworthiness prediction using machine learning techniques applied to banking customer data.

The analysis combines:

- Self-Organising Maps (SOM) for unsupervised exploration
- Multilayer Perceptron (MLP) Neural Networks for supervised classification

The objective is to classify customers into credit risk tiers and predict ratings for previously unassessed clients.

---

## Business Problem

Banks must evaluate the likelihood that customers will repay financial obligations while balancing lending opportunities against default risk.

Many customers within the dataset have not yet received a credit assessment. This project develops a machine learning framework capable of:

1. Understanding the structure of existing credit classes
2. Predicting ratings for unassessed customers

Credit ratings are defined as:

| Rating | Risk Level |
|----------|----------|
| A | Low Risk |
| B | Medium Risk |
| C | High Risk |

---

## Dataset

The dataset contains:

- Demographic information
- Employment indicators
- Credit history variables
- Third-party credit bureau scores
- 12 months of account balance history

### Features

- 46 predictor variables
- 1 target variable (`credit_rating`)

Target values:

| Value | Rating |
|---------|---------|
| 1 | A |
| 2 | B |
| 3 | C |
| 0 | Unknown |

---

## Methodology

### 1. Correlation Analysis

Pearson correlation was used to identify the most influential features associated with credit ratings.

Top predictors included:

- Functionary status
- FI3O credit score
- Overdrawn account history
- Previous credit refusals
- Average account balance

### 2. Self-Organising Map (SOM)

Configuration:

- 10 × 10 Hexagonal Grid
- 100 Training Iterations
- Standardised Features

Objectives:

- Visualise customer clusters
- Assess class separability
- Identify regions of mixed risk profiles

### 3. Multilayer Perceptron (MLP)

Architecture:

45 Inputs → 5 Hidden Neurons → 3 Outputs

Parameters:

- Learning Rate: 0.01
- Maximum Iterations: 250
- 50/50 Train-Test Split

---

## Results

### SOM Findings

- 100 total nodes
- 24 pure nodes
- 76 mixed nodes

The SOM revealed significant overlap between credit classes, indicating that risk categories are not cleanly separated in feature space.

### MLP Performance

| Metric | Training | Testing |
|----------|----------|----------|
| Accuracy | 74.1% | 52.6% |

Class B achieved the strongest performance while Classes A and C experienced substantial confusion.

---

## Key Findings

- Creditworthiness exists on a continuum rather than as distinct groups.
- Functionary status and external credit scores were among the strongest predictors.
- Significant overlap between classes makes classification challenging.
- The current neural network exhibits signs of overfitting.

---

## Future Improvements

Potential enhancements include:

- SMOTE for class balancing
- Cross-validation
- Hyperparameter tuning
- Larger neural network architectures
- XGBoost and Random Forest benchmarking
- Feature engineering from balance history
- Probability calibration for deployment

---

## Technologies

- R
- kohonen
- RSNNS
- ggplot2

---

## Repository Structure

```text
src/        → analysis scripts
data/       → raw and processed datasets
results/    → generated outputs
report/     → final report
docs/       → supporting documentation
```

---

## Author

Ngo Minh Thu Le
INFO911 – Data Mining and Knowledge Discovery
University of Wollongong
2025
