# Mini_Project-2026-
A deep learning–based melanoma screening model that addresses severe class imbalance in dermoscopic images to reduce missed melanoma cases using imbalance-aware training.


# Melanoma Detection from Dermoscopic Images using Deep Learning

## 📌 Overview
This project presents a **deep learning–based melanoma screening model** trained on dermoscopic skin lesion images.  
The primary focus is to **reduce missed melanoma cases (false negatives)** by explicitly addressing **class imbalance**, which is a major challenge in medical image analysis.

The system is intended as a **screening and decision-support tool**, not as a diagnostic system.

---

## 🎯 Problem Statement
Melanoma is a rare but life-threatening skin cancer.  
In real-world datasets such as HAM10000, melanoma samples are heavily underrepresented.  
Conventional CNNs often achieve high accuracy while failing to detect melanoma cases.

This project investigates:
- The effect of class imbalance on melanoma detection
- Strategies to improve melanoma sensitivity (recall)
- Trade-offs between accuracy and clinical safety

---

## 🗂 Dataset

### HAM10000 (Primary Dataset)
- ~10,000 dermoscopic images
- 7 original lesion classes
- Reformulated as **binary classification**:
  - Melanoma (`mel`) → label 1
  - All other lesions → label 0

Only image data is used to focus on visual feature learning.

---

## 🧠 Methodology

### 1️⃣ Preprocessing
- Image resizing and normalization
- Train / validation / test split
- Preservation of real-world class imbalance

### 2️⃣ Model Architecture
- **ResNet18** pretrained on ImageNet
- Final classification layer adapted for binary output

### 3️⃣ Class Imbalance Handling
- **Focal Loss** to emphasize hard melanoma samples
- GAN-generated melanoma images used only during training
- No synthetic data used in validation or testing

### 4️⃣ Training Strategy
- Transfer learning
- Adam optimizer
- GPU-accelerated training (PyTorch)

### 5️⃣ Evaluation Metrics
- Recall (Sensitivity) – primary metric
- Precision
- F1-score
- Confusion Matrix
- Accuracy (reported but not optimized for)

---

## 📊 Results (HAM10000 Test Set)

