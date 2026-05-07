# ♻️ Garbage Classification Using Deep Learning (MobileNetV2)

## 📌 Project Overview
This project is a deep learning-based image classification system designed to automatically categorize garbage into 10 different classes. It uses transfer learning with **MobileNetV2** to achieve high accuracy while keeping the model lightweight and efficient.

The goal is to support smart waste management systems by reducing manual sorting and improving recycling efficiency.

---

## 🧠 Problem Statement
Manual waste sorting is:
- Time-consuming  
- Error-prone  
- Expensive at large scale  

This project solves the problem by building an AI model that can automatically classify garbage images into predefined categories.

---

## 🗂️ Dataset
- Source: Kaggle (Garbage Classification V2)
- Link: https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2  
- Classes (10):
  - battery  
  - biological  
  - cardboard  
  - clothes  
  - glass  
  - metal  
  - paper  
  - plastic  
  - shoes  
  - trash  

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Image resizing: 224 × 224
- Normalization: pixel values scaled (1/255)
- Train/Validation split: 80% / 20%

### 2. Model Architecture
- Base Model: MobileNetV2 (pretrained on ImageNet)
- Transfer Learning: Frozen base layers
- Custom Layers:
  - Global Average Pooling
  - Dense layer (128 neurons, ReLU)
  - Dropout layers (0.4, 0.3)
  - Output layer (Softmax, 10 classes)

### 3. Training Configuration
- Optimizer: Adam  
- Loss Function: Categorical Crossentropy  
- Batch Size: 32  
- Epochs: 5  
- Callbacks:
  - EarlyStopping  
  - ModelCheckpoint  

---

## 📊 Results
- Validation Accuracy: ~92.7%
- Strong generalization across all 10 classes
- Low overfitting due to dropout + early stopping

### 📈 Visualizations
- Accuracy vs Epochs graph  
- Loss vs Epochs graph  
- Confusion Matrix  
- Sample predictions (True vs Predicted)

---

## 🖼️ Model Prediction Example
The model can take an input image and predict its category such as:
- Plastic
- Glass
- Metal
- Paper
- Biological waste

---

## 🚀 How to Run the Project

### 1. Install dependencies
```bash
pip install tensorflow keras numpy matplotlib seaborn scikit-learn

2. Download dataset
kaggle datasets download -d sumn2u/garbage-classification-v2

3. Run training

Run the notebook or Python script containing the model training pipeline.

4. Load saved model
from tensorflow.keras.models import load_model
model = load_model('best_model.keras')

📌 Technologies Used
Python 🐍
TensorFlow / Keras 🤖
MobileNetV2 🧠
NumPy / Pandas 📊
Matplotlib / Seaborn 📈
Scikit-learn 🔬

📌 Future Improvements
Deploy model as a web app (Flask / Streamlit)
Improve accuracy using fine-tuning
Add real-time camera classification
Expand dataset for better generalization
