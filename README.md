# Biological Target Status Prediction using LightGBM

This project involves predicting the `Target_Status` (biological target status) using a LightGBM classifier. The model is trained on a biological dataset with various features such as drug and disease information. The model can classify the current status of a drug development project, helping researchers and stakeholders make more informed decisions.
After performing stratified K-fold cross-validation and fine-tuning the model, the final accuracy achieved is **99.12%**.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model](#model)
- [Requirements](#requirements)
- [Results](#results)
- [Contact](#contact)

## Introduction

In this project, we aim to predict the `Target_Status` using biological data such as drug identifiers, accession numbers, drug types, gene names, and other drug-related information. The LightGBM classifier is chosen for its efficiency and performance in handling large datasets and categorical variables.

The project includes the following steps:

1. Data Preprocessing
2. Stratified K-Fold Cross-Validation
3. Model Training and Fine-Tuning
4. Prediction on Test Data

## Dataset

The dataset consists of various features related to drug and target information. Some key columns include:

- `DRUGID`: Drug Identifier
- `Accession Number`: Biological accession number
- `DRUGTYPE`: Type of drug
- `TargetID`: Target Identifier
- `GENENAME`: Name of the gene associated with the target
- `BIOCLASS`: Biological classification
- `Target_Status`: The target variable, representing the biological target status (this is what the model aims to predict)

### Files:

- `train.csv`: Training data containing features and the target variable.
- `test.csv`: Test data on which predictions are made.

## Model

We use a **LightGBM Classifier** with GPU support to train the model. The key parameters of the model include:

- **boosting_type**: 'gbdt' (Gradient Boosting Decision Tree)
- **num_leaves**: 90
- **learning_rate**: 0.080
- **n_estimators**: 1000

We applied **Stratified K-Fold Cross-Validation** with 4 splits to ensure that the distribution of the target class remains consistent across training and validation sets. After each fold, the accuracy and F1 scores were calculated.

## Requirements

- Python 3.x
- Pandas
- scikit-learn
- LightGBM
- NumPy (optional, for advanced data manipulations)

Install dependencies using:

```bash
pip install -r requirements.txt
```bash

### Results

The model achieved an average accuracy of **99.12%** after fine-tuning. Here are the key results:

- **Average Validation Accuracy**: 99.12%
- **Average Validation F1 Score**: 99.125%

A detailed classification report and confusion matrix are also printed for each fold during cross-validation.

### Contact

For any questions or collaboration opportunities, feel free to reach out:

- **Name**: Team DJS-CSK
- **Email**: satyavrat.djsce@gmail.com
