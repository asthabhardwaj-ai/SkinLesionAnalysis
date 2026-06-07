# Skin Lesion Analysis for Detection of Multiple Skin Infections using Deep Learning

##  Overview

This project presents an AI-powered healthcare solution for automated skin infection detection using Deep Learning and Transfer Learning techniques. The proposed system classifies skin lesion images into three major infection categories (Bacterial, Fungal, and Viral) and further identifies their specific subtypes using a Hierarchical Ensemble CNN architecture.

The goal is to assist dermatologists and healthcare professionals in early diagnosis, reducing dependence on costly diagnostic procedures such as biopsies, skin cultures, and blood tests.

---

##  Problem Statement

Skin diseases affect millions of people worldwide and early diagnosis is crucial for effective treatment. Manual diagnosis can be time-consuming and subjective.

This project aims to:

* Explore Deep Learning techniques for skin disease classification.
* Develop a Transfer Learning-based model for skin lesion analysis.
* Design a Hierarchical Ensemble CNN model capable of detecting:

  * Bacterial infections
  * Fungal infections
  * Viral infections
* Further classify infections into specific disease subtypes.

---

##  Dataset

### Total Dataset Size

* Total Images: **56,658**
* Total Classes: **7**

### Disease Categories

#### Bacterial Infections

* Cellulitis (8,079 images)
* Impetigo (8,148 images)

#### Fungal Infections

* Athlete Foot (Tinea Pedis) (8,054 images)
* Nail Fungus (8,083 images)
* Ringworm (8,129 images)

#### Viral Infections

* Chickenpox (8,083 images)
* Shingles (8,082 images)

---

##  Research Methodology

### Data Acquisition

* Collection of skin lesion images
* Data cleaning
* Removal of blurred and corrupted images

### Preprocessing

* Image resizing
* Image normalization
* Standardized color formatting

### Dataset Split

* Training Set: 70% (39,660 images)
* Validation Set: 15% (8,499 images)
* Test Set: 15% (8,499 images)

---

##  Model Architecture

### Stage 1: Coarse Classification

A confidence-weighted ensemble model combines:

* Baseline CNN
* MobileNetV2

Using Soft Voting:

Prediction = Σ(Class Probability × Confidence Weight)

Weights:

* Baseline CNN = 0.4
* MobileNetV2 = 0.6

Output Categories:

* Bacterial
* Fungal
* Viral

---

### Stage 2: Fine-Grained Classification

Based on Stage-1 prediction, specialized MobileNetV2 models classify the infection subtype.

#### Bacterial

* Cellulitis
* Impetigo

#### Fungal

* Athlete Foot
* Nail Fungus
* Ringworm

#### Viral

* Chickenpox
* Shingles

---

## 🚀 Existing Models Evaluated

| Model          | Accuracy |
| -------------- | -------- |
| Baseline CNN   | 100%     |
| EfficientNetB0 | 43%      |
| ResNet50       | 51%      |
| MobileNetV2    | 100%     |

### Findings

* EfficientNetB0 and ResNet50 performed poorly on the collected dataset.
* Baseline CNN and MobileNetV2 demonstrated superior performance and were selected for ensemble learning.

---

## 📊 Results

### Stage 1 Results

Classification of:

* Bacterial
* Fungal
* Viral

Performance:

* Accuracy: ~100%
* Precision: 1.00
* Recall: 1.00
* F1-Score: 1.00

### Stage 2 Results

Classification of all seven disease classes.

Performance:

* Accuracy: ~99.99%
* Precision: 1.00
* Recall: 1.00
* F1-Score: 1.00

---

## 🛠️ Technology Stack

### Programming Language

* Python

### Deep Learning Frameworks

* TensorFlow
* Keras

### Libraries

* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-Learn

### Models Used

* Custom CNN
* MobileNetV2
* Ensemble Soft Voting Classifier

---

## Project Structure

```text
Skin-Lesion-Detection/
│
├── dataset/
│   ├── bacterial/
│   ├── fungal/
│   └── viral/
│
├── preprocessing/
│   └── image_preprocessing.py
│
├── models/
│   ├── baseline_cnn.py
│   ├── mobilenetv2.py
│   └── ensemble_model.py
│
├── training/
│   └── train.py
│
├── evaluation/
│   ├── confusion_matrix.py
│   └── classification_report.py
│
├── notebooks/
│
├── results/
│
├── requirements.txt
│
└── README.md
```

---

##  Installation

```bash
git clone https://github.com/yourusername/Skin-Lesion-Detection.git

cd Skin-Lesion-Detection

pip install -r requirements.txt
```

---

## ▶️ Training

```bash
python train.py
```

---

## Evaluation

```bash
python evaluate.py
```

Metrics Used:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

---

##  Future Work

* Support additional dermatological diseases.
* Integrate Explainable AI (XAI) using Grad-CAM.
* Deploy as a cloud-based web application.
* Mobile application for real-time diagnosis.
* Integration with Electronic Health Records (EHR).

---

##  Author

**Astha Bhardwaj**

AI/ML Engineer | Generative AI | Agentic AI | Healthcare AI

* B.Tech (Computer Science)
* M.Tech (AI/ML), BITS Pilani
* Full Stack Developer & AI Researcher

---

##  License

This project is licensed under the MIT License.

---

##  Acknowledgements

* BITS Pilani WILP Program
* TensorFlow Community
* Open-Source Deep Learning Research Community

If you find this project useful, please give it a ⭐ on GitHub.
