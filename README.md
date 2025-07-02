# Congenital Heart Disease Detection Using Deep Learning on ECG Signals

This project focuses on the detection of **Congenital Heart Disease (CHD)** using **Electrocardiogram (ECG)** data and **deep learning techniques**, particularly **1D Convolutional Neural Networks** such as ResNet-18 and ResNet-50, along with LSTM-based models.

## 📌 Problem Statement

Congenital Heart Disease is a structural defect in the heart present from birth. ECG signals contain patterns that can help detect these abnormalities. Manual ECG interpretation is prone to error and fatigue, so this project automates the detection of CHD using deep learning techniques on raw multichannel ECG signals.

## 🧠 Models Implemented

- ✅ **ResNet-18 (1D)** — Trained using **SGD** and **Adam** optimizers
- ✅ **ResNet-50 (1D)** — Higher-depth residual network
- ✅ **LSTM** — Sequence model for temporal ECG signal processing

## ⚙️ Dataset

- Input: 9-lead ECG signals, length 1000 per sample → shape `(1000, 9)`
- Total test samples: 3398 (3019 Non-CHD, 379 CHD)
- Dataset split into train/validation/test sets
- Labels: `0 = Normal`, `1 = CHD`

## 🏗️ Model Architecture

All models process 1D ECG signals:

- **ResNet-18/50 (1D)**:  
  - 1D residual blocks with BatchNorm + ReLU
  - Global Average Pooling
  - Fully Connected Layers with Dropout
- **LSTM**:  
  - Stacked LSTM layers
  - Dense output with Softmax

## 📊 Evaluation Metrics

The models are evaluated using the following:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

---

## 📈 Results Summary

### 🔹 ResNet-18 (1D) — **SGD Optimizer**
- ✅ **Test Accuracy**: `98.85%`
- ✅ **Test Loss**: `0.0311`
Precision: 0.96 (CHD)
Recall: 0.93 (CHD)
F1-Score: 0.95 (CHD)



### 🔹 ResNet-18 (1D) — **Adam Optimizer**
- ✅ **Test Accuracy**: `98.79%`
- ✅ **Test Loss**: `0.0349`

Precision: 0.97 (CHD)
Recall: 0.92 (CHD)
F1-Score: 0.94 (CHD)



### 🔹 ResNet-50 (1D)
- ✅ **Test Accuracy**: `98.00%`

Precision: 0.96 (CHD)
Recall: 0.89 (CHD)
F1-Score: 0.92 (CHD)



### 🔹 LSTM
- ⚠️ **Test Accuracy**: `92.00%`

Precision: 0.70 (CHD)
Recall: 0.43 (CHD)
F1-Score: 0.53 (CHD)



> LSTM underperformed on recall and F1-score for CHD detection, indicating difficulty in capturing key temporal dependencies in this setup.

---

## 📁 Project Structure

chd-ecg-detection/
├── models/ # ResNet & LSTM architectures
├── data/ # Data loaders or preprocessing scripts
├── notebooks/ # Training, testing, and visualization notebooks
├── results/ # Metrics, classification reports, plots
├── utils/ # Helper functions and tools
├── README.md
└── requirements.txt # Dependencies list

## 🚀 How to Run

```bash
git clone https://github.com/yourusername/chd-ecg-detection.git
cd chd-ecg-detection
pip install -r requirements.txt
Run model training or inference from the provided notebooks or training scripts.

🔍 Future Scope
Explore Transformer-based models for better sequential modeling

Include Grad-CAM or SHAP for interpretability

Extend to other cardiac conditions (e.g., Arrhythmia, Myocardial Infarction)

👩‍💻 Author
Arya M
