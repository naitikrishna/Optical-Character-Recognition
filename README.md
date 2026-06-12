# Optical-Character-Recognition

A machine learning–based optical character recognition (OCR) project implemented in Python. This repository contains:

- `ML_OCR.ipynb`: Jupyter Notebook demonstrating data loading, preprocessing, model training, and evaluation for OCR tasks.
- `samples1000.zip`: A dataset of 1,000 labeled character images used for training and testing.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Pipeline](#pipeline)
4. [Models](#models)
5. [Results](#results)
6. [Prerequisites](#prerequisites)
7. [Project Structure](#project-structure)


---

## Project Overview

This project implements a simple OCR system using classical machine learning techniques. The goal is to classify individual character images into their corresponding labels (e.g., letters A–Z).

Key steps covered in the notebook:

- Loading and inspecting the `samples1000` dataset
- Preprocessing: resizing, normalization, and train-test split
- Feature extraction using pixel intensity or simple descriptors
- Model training (e.g., Support Vector Machine, Random Forest)
- Evaluation metrics: accuracy, confusion matrix, classification report

## Dataset

The dataset is provided in `samples1000.zip`. It contains:
| Property | Value |
|----------|-------|
| Source images | 1,000 combined CAPTCHA images |
| Total samples | **5,000** individual character images |
| Classes | 26 (a–z) |
| Samples per class | ~163–199 (well balanced) |
| Train / Test split | 80% / 20% |
 
Each image filename encodes its label — e.g., `pfaqep.png` contains letters `p`, `f`, `a`, `q`, `e`, `p` in order.

## Pipeline
 
```
Raw CAPTCHA Image
      ↓
Split into 5 character images
      ↓
Image Preprocessing
      ↓
HOG Feature Extraction
      ↓
Train ML Classifier (LR / SVM / RF)
      ↓
Predict Character Label

```
## Models
 
### Classical ML (with HOG features)
 
| Model | Accuracy |
|-------|----------|
| Logistic Regression | 74.6% |
| Support Vector Machine (linear) | 77.5% |
| Random Forest (100 estimators) | 72.9% |
 
**Best Model: SVM** — tuned via `GridSearchCV`

## Results
 
- **Best accuracy: ~80%+ (SVM with poly kernel)**
- Common misclassifications:
  - `h` confused with `b`
  - `x` confused with `f` or `i`
  - `t` confused with `c`, `f`, or `l`
  - `v` confused with `f`
  - `d` confused with `a`


## Prerequisites

- Python 3.9+
- **pip** — comes with Python
- Google Colab



## Project Structure

```text
ML_OCR/
├── ML_OCR.ipynb        # Main notebook
├── samples1000.zip     # Zipped dataset
├── samples1000/        # Unzipped data directory
└── README.md           # Project README
```

