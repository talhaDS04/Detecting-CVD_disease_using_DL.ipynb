# ❤️ CVD Detection using DL

A comprehensive Deep Learning project for predicting heart disease using **ECG signals** and **clinical tabular data**. This project explores multiple approaches including **CNN**, **CNN-LSTM Hybrid Networks**, **Multi-Modal Fusion**, and **SHAP Explainability** for interpretable AI in healthcare.

---

## 📌 Project Overview

Heart disease is one of the leading causes of death worldwide. Early and accurate prediction can assist doctors in providing better treatment and preventive care.

This project implements a complete Deep Learning pipeline:

- ECG signal processing and visualization
- Heartbeat segmentation and labeling
- Binary classification (Normal vs Abnormal heartbeat)
- CNN-based feature extraction
- CNN-LSTM hybrid architecture
- Model optimization with callbacks
- Clinical data integration using Multi-Modal Fusion
- Explainable AI using SHAP

---

## 📂 Dataset

### 1. MIT-BIH Arrhythmia Database (ECG)

ECG signals are downloaded using the `wfdb` Python package.

Features:
- Raw ECG waveform records
- Annotation files
- Heartbeat labels
- R-peak positions

---

### 2. Cleveland Heart Disease Dataset

Clinical attributes include:

- Age
- Sex
- Chest pain type
- Resting blood pressure
- Cholesterol level
- Fasting blood sugar
- Resting ECG results
- Maximum heart rate
- Exercise-induced angina
- ST depression
- Slope
- Number of vessels
- Thalassemia

---

# ⚙️ Project Pipeline

## Phase 1: Environment Setup & Data Download

- Install required libraries
- Download MIT-BIH ECG database
- Inspect records and annotations

---

## Phase 2: ECG Visualization

- Load ECG records
- Plot ECG signals
- Visualize annotation points

---

## Phase 3: ECG Preprocessing

- Extract R-peaks
- Create heartbeat segments
- Convert labels into binary classes:

```
0 → Normal
1 → Abnormal
```

- Normalize ECG signals
- Reshape data for Deep Learning models
- Split into training and testing sets

---

## Phase 4: CNN Model

A 1D Convolutional Neural Network is used for automatic ECG feature extraction.

Architecture:

```
Input ECG (300 × 1)
        ↓
Conv1D (32 Filters)
        ↓
MaxPooling
        ↓
Conv1D (64 Filters)
        ↓
MaxPooling
        ↓
Flatten
        ↓
Dense Layer
        ↓
Dropout
        ↓
Sigmoid Output
```

---

## Phase 5: CNN + LSTM Hybrid Model

The CNN-LSTM model combines:

- CNN → Spatial feature extraction
- LSTM → Temporal pattern learning

Architecture:

```
ECG Signal
     ↓
CNN Layers
     ↓
LSTM Layer
     ↓
Dense Layers
     ↓
Binary Prediction
```

---

## Phase 6: Model Improvement & Evaluation

Optimization techniques:

- EarlyStopping
- ReduceLROnPlateau

Evaluation Metrics:

- Accuracy
- Classification Report
- Confusion Matrix
- ROC Curve
- ROC-AUC Score

---

## Phase 7: Multi-Modal Fusion Model

The project combines two different sources of medical information:

### ECG Branch

```
ECG → CNN → LSTM
```

### Clinical Data Branch

```
Patient Features → Dense Neural Network
```

### Fusion

Both feature vectors are merged using a concatenation layer.

```
ECG Features
       \
        → Fusion Layer → Dense Layers → Prediction
       /
Clinical Features
```

This approach allows the model to learn from both physiological signals and patient information.

---

## Phase 8: Explainable AI using SHAP

To understand the model's decisions, SHAP (SHapley Additive exPlanations) is implemented.

Generated explanations:

- Feature importance
- SHAP Summary Plot
- Force Plot for individual predictions

---

## 🛠 Technologies Used

### Programming Language

- Python

### Deep Learning Framework

- TensorFlow
- Keras

### Data Processing

- NumPy
- Pandas
- Scikit-learn

### ECG Processing

- WFDB

### Visualization

- Matplotlib
- Seaborn

### Explainability

- SHAP

---

## 📁 Project Structure

```
Heart-Disease-Prediction/
│
├── Heart_Disease_Prediction.ipynb
├── README.md
├── MIT-BIH ECG Dataset(availaible online)
├── Cleveland Heart Disease Dataset

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Heart-Disease-Prediction.git
```

### 2. Install Dependencies

```bash
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn wfdb shap
```

### 3. Open Jupyter Notebook

```bash
jupyter notebook
```

### 4. Run the Notebook

Execute all cells in sequence to reproduce the complete workflow.

---

## 🔬 Future Improvements

Possible extensions:

- Use larger ECG datasets
- Apply Transformer-based architectures
- Perform hyperparameter optimization
- Deploy the model using Flask or FastAPI
- Create a real-time heart disease prediction application

---

## 👨‍💻 Author

**Muhammad Talha**

Data Scientist | Machine Learning Engineer | Deep Learning Enthusiast

---

## ⭐ Acknowledgements

- MIT-BIH Arrhythmia Database
- Cleveland Heart Disease Dataset
- TensorFlow & Keras Community
- SHAP Explainability Library

---

## 📜 License

This project is developed for educational and research purposes.
