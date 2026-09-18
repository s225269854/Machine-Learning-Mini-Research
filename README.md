# SIT720 11.1HD – Machine Learning Research

## Project Overview

This project reproduces and extends the machine-learning methodology presented in:

**Bhagat, M., Sharma, A. and Agarwal, P.,  
"An Efficient Stacking-Based Ensemble Technique for Early Heart Attack Prediction."**

The original study compares six machine-learning classifiers and combines them using a stacking ensemble for heart-disease prediction.

The project is divided into two main stages:

1. Reproduction of the published machine-learning methodology.
2. Investigation of duplicate-related train-test overlap and development of a more rigorous nested cross-validation framework.

## Dataset

The project uses the Heart Disease Dataset containing:

- 1,025 observations
- 13 predictor variables
- 1 binary target variable

The dataset is located at:
`data/heart.csv`

Initial analysis identified 723 duplicate observations, leaving 302 unique observations.

## Machine-Learning Models

The following classifiers are implemented:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Naive Bayes
- K-Nearest Neighbours
- Stacking Ensemble

## Experimental Design

### Experiment 1 – Reproduction

The original 1,025 observations are retained to reproduce the published experiment. A stratified 80:20 train-test split and five-fold stacking procedure are used.

### Experiment 2 – Deduplicated Evaluation

Exact duplicate observations are removed, leaving 302 unique records. The models are re-evaluated using the same 80:20 split strategy to investigate the effect of duplicate-related overlap.

### Experiment 3 – Proposed Framework

A nested repeated stratified cross-validation framework is used to provide a more rigorous estimate of model generalisation.

The outer evaluation uses 5-fold stratified cross-validation repeated 5 times, producing 25 evaluation folds. Hyperparameter optimisation for Random Forest and XGBoost is performed within the inner cross-validation procedure.

## Project Structure

    data/
        heart.csv

    notebook/
        SIT720_11.1HD.ipynb
        SIT720_11.1HD_notebook.pdf

    README.md
    requirements.txt


## Installation

Python 3.x is required.

Install the required Python packages using:
   ` pip install -r requirements.txt`

## Running the Notebook

1. Download or clone this repository.
2. Keep the original folder structure unchanged.
3. Install the required dependencies.
4. Open the notebook located in the notebook folder.
5. Run all cells sequentially from top to bottom.

The notebook loads the dataset using:
`../data/heart.csv`

Hence the data and notebook folders should remain in the same project directory.


## Reproducibility

A fixed random state of `225269854` is used where applicable.

The notebook contains the complete preprocessing, model training, hyperparameter optimisation, evaluation and comparison procedures required to reproduce the reported results.

## GenAI Acknowledgement

Generative AI was used to assist with planning, debugging, reviewing code, interpreting outputs and improving written explanations. All code was executed and outputs were reviewed and verified by the author.
