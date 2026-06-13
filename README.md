# PhishVision-KD

A multimodal phishing website detection framework that combines computer vision, natural language processing, and knowledge distillation to identify fraudulent websites from webpage screenshots and URLs.

The project benchmarks three advanced architectures:

* Knowledge-Distilled Multimodal Ensemble
* CLIP + DistilBERT + URL Features
* Vision Transformer (ViT) + URL Features

using a custom dataset of 6,000 phishing and legitimate websites.

---

## Motivation

Modern phishing websites closely imitate legitimate websites through visual spoofing, brand impersonation, and URL manipulation.

Traditional blacklist-based systems often fail against these attacks.

This project explores whether multimodal deep learning can effectively detect phishing websites by jointly analyzing:

* Website screenshots
* URL semantics
* URL lexical characteristics

---

## Dataset

Custom dataset built from scratch:

| Category            | Samples |
| ------------------- | ------- |
| Phishing Websites   | 3,000   |
| Legitimate Websites | 3,000   |
| Total               | 6,000   |

Each sample contains:

* Webpage Screenshot
* Website URL
* Binary Label

Dataset designed using active phishing campaigns and verified legitimate websites.

---

## Models Evaluated

### 1. Knowledge-Distilled Multimodal Ensemble

Teacher Ensemble:

* TinyCNN
* MobileNetV3-Small
* URL-MLP

Student Network:

* Lightweight CNN
* URL Feature Encoder
* Distillation-based Learning

Advantages:

* Resource-efficient
* Fast inference
* Real-time deployment ready

---

### 2. CLIP + DistilBERT + URL Features

Multimodal architecture combining:

* CLIP Visual Encoder
* DistilBERT URL Encoder
* Engineered URL Features

Captures:

* Visual webpage patterns
* URL semantics
* Structural phishing indicators

---

### 3. ViTPhishFusion

Hybrid model combining:

* Vision Transformer (ViT)
* URL Lexical Features

Designed to capture:

* Layout inconsistencies
* Brand impersonation
* Visual spoofing patterns

---

## Results

| Model             | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| ----------------- | -------- | --------- | ------ | -------- | ------- |
| KD Multimodal     | 90.27%   | 0.797     | 0.893  | 0.843    | 0.855   |
| CLIP + DistilBERT | 95.21%   | 0.943     | 0.902  | 0.911    | 0.934   |
| ViT Fusion        | 80.93%   | 0.80      | 0.82   | 0.81     | 0.78    |

The CLIP-BERT model achieved the strongest overall performance, while the distilled model provided the best trade-off between efficiency and accuracy.

---

## Key Contributions

* Built a custom phishing dataset with 6,000 websites.
* Benchmarked three state-of-the-art multimodal architectures.
* Implemented ensemble knowledge distillation for lightweight deployment.
* Combined screenshot analysis with URL intelligence.
* Developed a Streamlit-based real-time phishing detection interface.
* Achieved up to 95.21% accuracy on phishing website detection.

---

## Tech Stack

* Python
* PyTorch
* Hugging Face Transformers
* CLIP
* DistilBERT
* Vision Transformer (ViT)
* MobileNetV3
* Scikit-Learn
* Pandas
* NumPy
* Streamlit

---

## Future Work

* Browser Extension
* Real-Time API Deployment
* Explainable AI Dashboard
* Advanced Teacher Ensembles
* Lightweight Edge Deployment
* Zero-Day Phishing Detection Enhancement

---

## Authors

* Siddhi Jadhav
Information Technology

National Institute of Technology Kurukshetra
