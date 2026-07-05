# Kidney Dialysis Prediction ML Pipeline

Machine learning pipeline for predicting whether a patient may require dialysis from laboratory and demographic records.

The original work used private hospital data, so this public repository uses a synthetic dataset with the same general structure. The goal is to show the pipeline design, preprocessing, and evaluation approach without exposing patient data.

## Why this project matters

Medical datasets are rarely clean notebook examples. The useful work is in turning raw clinical records into a model-ready table while staying careful about privacy, missing values, class imbalance, and evaluation.

This project focuses on that workflow:

- translating and standardizing raw feature names
- removing columns with almost no usable signal
- reshaping lab records into patient-level rows
- encoding the dialysis target
- handling class imbalance
- comparing multiple classifiers with more than one metric

## Data

The real dataset is not included because it contains private medical records.

Included instead:

- `kidney_synthetic.xlsx`: safe synthetic data for running the notebook
- `SyntheticDataGEN.ipynb`: notebook used to generate the synthetic file

Important limitation: the synthetic data is only for code demonstration. It should not be used for medical conclusions, and its metrics should not be interpreted as clinical performance.

## Pipeline

1. Clean raw columns and remove unusable fields.
2. Transform lab-test rows into patient-level features.
3. Encode the target label.
4. Handle missing values and imbalanced classes.
5. Train Logistic Regression, Random Forest, and SVM models.
6. Compare accuracy, precision, recall, F1-score, and ROC behavior.

## Repository structure

| file | purpose |
| --- | --- |
| `finalproject.ipynb` | main pipeline notebook |
| `SyntheticDataGEN.ipynb` | synthetic data generation |
| `kidney_synthetic.xlsx` | safe demo dataset |
| `requirements.txt` | Python dependencies |

## Run it

```bash
pip install -r requirements.txt
jupyter notebook finalproject.ipynb
```

To regenerate the synthetic data, run:

```bash
jupyter notebook SyntheticDataGEN.ipynb
```

## What I learned

- how to document an ML project when the real dataset cannot be shared
- why privacy constraints affect portfolio design
- how imbalance changes model evaluation
- why preprocessing decisions matter as much as the classifier

## Disclaimer

This is an educational portfolio project. It is not a medical product and should not be used for diagnosis or treatment decisions.