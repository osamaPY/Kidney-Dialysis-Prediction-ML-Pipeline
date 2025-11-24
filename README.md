# Dialysis Prediction from Laboratory Tests

## Overview
This project builds a machine learning pipeline to predict if a patient requires dialysis based on laboratory tests and demographic data. The goal was to process raw hospital data and compare different classification models.

## Data Privacy and Synthetic Data
The original dataset used for this project comes from a hospital in Iran and contains private medical records. Due to privacy concerns, **the real data is not included in this repository.**

To demonstrate that the code works, I have included a **synthetic dataset** (`kidney_synthetic.xlsx`). I generated this data to mimic the structure and column names of the original files.

**Note:** Because the synthetic data is randomly generated, it does not reflect real medical correlations. Therefore, the accuracy and evaluation metrics in the notebook will be low. The actual model trained on the real private data performed significantly better.

## Repository Files
* `finalproject.ipynb`: The main notebook containing data cleaning, preprocessing, and modeling.
* `SyntheticDataGEN.ipynb`: The script used to generate the synthetic dataset.
* `kidney_synthetic.xlsx`: Safe dummy data for testing the code.
* `requirements.txt`: List of Python libraries required.

## Pipeline Steps
1. **Data Cleaning:** Translating column names from Persian to English and handling missing values (dropping columns with >99% missing data).
2. **Preprocessing:** Pivoting data so each row represents one patient and encoding the target variable.
3. **Imbalance Handling:** Using oversampling techniques to address the class imbalance between dialysis and non-dialysis patients.
4. **Modeling:** Training Logistic Regression, Random Forest, and SVM models.
5. **Evaluation:** Comparing models using Accuracy, Precision, Recall, F1-score, and ROC curves.

## How to Run
1. Install the required libraries:
   ```bash
   pip install -r requirements.txt

2. Open the main notebook:
   jupyter notebook finalproject.ipynb

(Optional) To generate new synthetic data, run SyntheticDataGEN.ipynb.


Disclaimer
This project is for educational purposes. The synthetic data should not be used to draw medical conclusions.
