# ViTPhishFusion: Multimodal Phishing Website Detection

A multimodal phishing website detection system that combines **Vision Transformer (ViT)** screenshot embeddings with **URL intelligence features** to identify fraudulent websites. The model leverages both visual and lexical cues to detect sophisticated phishing attacks that often evade traditional blacklist and rule-based approaches.

---

## Overview

Phishing websites increasingly mimic legitimate websites using realistic layouts, logos, and branding. Traditional URL-based detection systems often fail to identify these visually deceptive attacks.

**ViTPhishFusion** addresses this challenge by fusing:

* Visual features extracted from website screenshots using Vision Transformers (ViT)
* Engineered lexical features extracted from URLs

This multimodal approach enables robust detection of phishing websites by analyzing both how a website looks and how its URL is structured.

---

## Key Features

* Vision Transformer (ViT) based screenshot analysis
* URL lexical feature engineering
* Multimodal feature fusion architecture
* Custom dataset of 6,000 websites
* Real-world phishing and legitimate samples
* Robust detection of visually deceptive phishing attacks
* Scalable architecture for future deployment

---

## Dataset

A custom dataset was created consisting of:

| Category            | Samples |
| ------------------- | ------- |
| Phishing Websites   | 3,000   |
| Legitimate Websites | 3,000   |
| Total Samples       | 6,000   |

Each sample contains:

* Website Screenshot
* Website URL
* Binary Label (Phishing / Legitimate)

---

## URL Features Extracted

The following handcrafted lexical features are extracted:

* URL Length
* Number of Dots
* Number of Hyphens
* Number of Digits
* Number of '@' Symbols
* HTTPS Presence
* IP Address Detection
* Suspicious Keyword Detection

All features are standardized using StandardScaler before training.

---

## 🏗️ Model Architecture

### Step 1: Image Processing

* Resize screenshots to 224 × 224
* Normalize pixel values
* Extract embeddings using pretrained ViT

### Step 2: URL Feature Engineering

* Extract lexical URL features
* Normalize features

### Step 3: Feature Fusion

* Concatenate ViT embeddings with URL features

### Step 4: Classification

* Fully Connected Layers
* ReLU Activation
* Dropout Regularization
* Sigmoid Output Layer

---

## 📈 Results

| Metric   | Score |
| -------- | ----- |
| Accuracy | 80%   |
| Recall   | 85%   |
| F1 Score | 0.80  |

The high recall demonstrates strong capability in identifying phishing websites while minimizing undetected threats.

---

## 🛠️ Tech Stack

### Machine Learning

* PyTorch
* Hugging Face Transformers
* Scikit-Learn

### Data Processing

* Pandas
* NumPy

### Computer Vision

* Vision Transformer (ViT)
* PIL
* OpenCV

### Visualization

* Matplotlib
* Seaborn

---

## Training

```bash
python train.py
```

---

## Inference

```bash
python predict.py
```

Input:

* Website Screenshot
* URL

Output:

* Phishing
* Legitimate

---

## Future Enhancements

* Knowledge Distillation
* Lightweight Student Models
* Browser Extension Integration
* Real-Time Detection API
* Streamlit Deployment
* Explainable AI Dashboard
* Fine-Tuning of ViT Backbone
* Larger Multimodal Dataset

---

## Authors

* Siddhi Jadhav
Information Technology

National Institute of Technology Kurukshetra

---

## License

This project is intended for educational and research purposes.
