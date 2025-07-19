# 🧠 Breast Cancer Cell Classification using Deep Learning

This project focuses on classifying **benign** and **malignant** breast cancer cells using deep learning models trained on an **augmented dataset** of microscopic images. We employed state-of-the-art CNN architectures like MobileNetV2, InceptionV3, and DenseNet121 to detect cancerous patterns efficiently.

---

## 📁 Dataset Overview

The dataset consists of microscopic images categorized into two folders:
- `B` — Benign cells
- `M` — Malignant cells

The dataset was augmented and then split into three sets:
- `Train` — 70%
- `Validation` — 15%
- `Test` — 15%

### 🔁 Data Augmentation Techniques Used
To increase data diversity and reduce overfitting:
- ✅ Rotation
- ✅ Horizontal Flip
- ✅ Vertical Flip
- ✅ Grayscale conversion *(in selective runs)*
- ❌ Cropping & Tilting were avoided due to loss of critical cell features

---

## 🧪 Models Used

| Model         | Optimizer | Learning Rate | Input Size | Pretrained |
|---------------|-----------|----------------|------------|------------|
| MobileNetV2   | Adam      | 0.0001         | 224×224    | Yes (ImageNet) |
| InceptionV3   | RMSprop   | 0.00001        | 299×299    | Yes (ImageNet) |
| DenseNet121   | Adam      | 0.0001         | 224×224    | Yes (ImageNet) |

Each model was fine-tuned on our custom dataset after replacing the top classifier layers with new dense layers suitable for binary classification.

---

## ⚙️ Training Configuration

- **Epochs**: 10  
- **Batch Size**: 32  
- **Loss Function**: Binary Crossentropy  
- **Metrics**: Accuracy, Precision, Recall, F1-score  
- **Augmented Data**: Yes  
- **Early Stopping**: Optional, based on validation loss

---

## 📊 Evaluation

Each model was evaluated using:
- Accuracy on test set (15%)
- Classification Report (Precision, Recall, F1-score)
- Confusion Matrix
- Epoch-wise training vs validation loss/accuracy plots

Additionally, inference was performed on randomly selected test images from:
split_data/test/B/
split_data/test/M/

---

## 💾 Model Checkpoints

Trained model weights were saved in `.keras` format. For example:
breast_cancer_inception2.keras
(DenseNet model was saved using .h5)

These can be used to directly load the model for future inference.

---


