# Dialysis Prediction from Laboratory Tests 🧪  
**Machine Learning Pipeline Using Confidential Hospital Data + Synthetic Data Generator**

---

## 📌 Project Overview

This project builds a complete **end-to-end machine learning pipeline** to predict whether a patient belongs to the **Dialysis (دياليز)** department based on routine laboratory tests and simple demographic information.

The **original data** used in this project was collected from a **hospital in Iran** and contains sensitive medical information.  
For privacy and ethical reasons:

### 🚫 **Real hospital data is NOT included in this repository.**

Instead, the repository includes a **synthetic dataset** that I generated to mimic the structure, ranges, and statistical patterns of the original data without exposing any private patient information.

---

## 🔒 **Why Synthetic Data?**

Because the real dataset contains confidential lab results and medical status, it cannot be published publicly.

To still demonstrate the full machine learning pipeline safely, I created a **custom synthetic data generator**:

### ✔ Preserves:
- Same column names  
- Same medical test ranges (approximate)  
- Similar distributions (age, gender, lab values)  
- Same format as the real dataset  

### ✖ Does *NOT* preserve:
- Real patient information  
- True correlations between tests  
- True patterns that determine dialysis status  

This means:

> **Synthetic data is ONLY for code demonstration. It does NOT reflect true medical performance.  
> The real model trained on real data performs differently (and better).**

Synthetic data is simply a safe placeholder that allows this project to be made public on GitHub.

---

## 🧠 Machine Learning Pipeline

The notebook (`finalproject.ipynb`) includes:

### **1️⃣ Data Loading & Confidentiality Handling**
- Select real or synthetic dataset via a switch.
- Synthetic dataset lives in the repo; real one stays local on my machine.

### **2️⃣ Cleaning & Preprocessing**
- Translate Persian column names → English  
- Pivot long lab records into per-patient rows  
- Handle missing values (drop only tests with ≥99% missing)  
- Convert dialysis ("دياليز") to binary class label

### **3️⃣ Train/Test Split**
- Stratified split to preserve class balance  

### **4️⃣ Class Imbalance Handling**
- Oversampling (random + SMOTE-like behavior)

### **5️⃣ Baseline Models**
- Logistic Regression  
- Random Forest  
- Support Vector Machine (SVM)

### **6️⃣ Hyperparameter Tuning**
- `RandomizedSearchCV`
- `GridSearchCV`
- Optimized for **ROC-AUC**

### **7️⃣ Evaluation**
- Accuracy, Precision, Recall, F1  
- Confusion matrices  
- ROC curves  
- Model comparison table  

### **8️⃣ Visualizations**
- PCA dimensionality reduction  
- Feature importance for interpretability  

---

## 📉 Results on Synthetic Data (Important!)

Synthetic data does **NOT** reflect the real relationship between lab values and dialysis status.

As a result:

### 👉 Accuracy, precision, recall, and AUC appear **low**.  
### 👉 This is expected and totally normal.

The real hospital dataset performs notably better but cannot be shared.

The goal of this repository is to demonstrate:
- the **ML pipeline**,  
- the **code quality**,  
- the **data engineering**,  
- and the **modeling process**,  
NOT to publish medically meaningful results.

---

## 📁 Repository Structure

Kidney-Dialysis-Prediction-ML-Pipeline/
│
├── finalproject.ipynb # Full ML pipeline notebook
├── SyntheticDataGEN.ipynb # Synthetic data generator notebook
├── kidney_synthetic.xlsx # Safe synthetic dataset
├── requirements.txt # Python dependencies
├── .gitignore # Ignore sensitive files
└── README.md # Project documentation



---

## 🧭 How to Run the Project

```bash
pip install -r requirements.txt
python SyntheticDataGEN.ipynb   # or open in Jupyter to regenerate synthetic data
jupyter notebook finalproject.ipynb


⚠️ Disclaimer

This project:

is educational,

is not a medical device,

should not be used for diagnosis,

and does not reflect true medical accuracy due to synthetic data limitations.

The true medical model is trained privately using real hospital data that cannot be published.




🙏 Acknowledgements

Thanks to the medical staff who enabled access to anonymized real data for academic use.
All sensitive information has been handled responsibly and never shared publicly.


---

# ✅ **Answer to your other question**

### **“Should I use `/data/kidneyTRUE.xlsx` or `kidneyTRUE.xlsx`?”**

Use this **ONLY if** you create a folder named `data` inside your GitHub repo:

/data/kidney_synthetic.xlsx



Then your code should be:

```python
path_true = "data/kidneyTRUE.xlsx"


