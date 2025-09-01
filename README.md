# Predicting Introverts vs Extroverts

## Project Overview
This project uses a deep neural network to classify individuals as **Introverts** or **Extroverts** based on behavioral and demographic data. The goal was to explore deep learning model training and achieve high accuracy in a Kaggle competition.

**Dataset:** [Kaggle Playground Series S5E7](https://www.kaggle.com/competitions/playground-series-s5e7/data)

**Task:** Binary classification (Introvert vs Extrovert)

---

## Data Preprocessing
- Dropped `id` column.
- Imputed missing values:
  - Numerical: median
  - Categorical: most frequent
- Encoded categorical variables using `LabelEncoder`.
- Scaled numerical features using `StandardScaler`.

---

## Model Architecture
- **Input layer:** matching the number of features
- **Hidden layers:**  
  - Layer 1: 128 units, ReLU activation  
  - Layer 2: 64 units, ReLU activation  
- **BatchNormalization** after each hidden layer  
- **Dropout:** 0.3 to prevent overfitting  
- **Output layer:** Softmax for binary classification  

**Optimizer:** Adam  
**Loss function:** Sparse Categorical Crossentropy  
**Metrics:** Accuracy, F1-score  

**Cross-validation:** Stratified 5-Fold CV  
**Callbacks:** EarlyStopping, ReduceLROnPlateau

---

## Training Results
- **CV Accuracy:** ~96.9%  
- **CV F1-score:** ~96.9%  
- **Public Kaggle Score:** 0.9733  

**Observations:**  
- Model converged without severe overfitting.  
- Ensemble predictions improved robustness on the test set.

---

## Plots
- Training vs Validation Accuracy per fold  
- Training vs Validation Loss per fold  

*Plots available in the `notebooks` folder.*

---

## Key Takeaways
- Proper preprocessing and feature encoding are crucial for neural networks.  
- BatchNormalization and Dropout help stabilize training and improve generalization.  
- Cross-validation ensures model performance is consistent.

---

## Files
- `train.csv` / `test.csv` – Dataset  
- `main.ipynb` – Complete project notebook  
- `submission.csv` – Kaggle submission
