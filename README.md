# SERLiteNet_Baseline
# SERLiteNet: A Lightweight Residual Depthwise Convolutional Neural Network with Multi-Level Acoustic Feature Fusion for Speech Emotion Recognition

<p align="center">

<img src="Images/proposed_lightsernet_architecture.png" width="900">

</p>

---

## Overview

SERLiteNet is a lightweight deep learning framework for **Speech Emotion Recognition (SER)** based on **Residual Depthwise Separable Convolutional Neural Networks** and **Multi-Level Acoustic Feature Fusion**.

The proposed framework combines complementary acoustic representations with a computationally efficient CNN architecture to achieve competitive speech emotion recognition performance while maintaining a very small model size suitable for future embedded AI applications.

---

## Key Features

- Lightweight CNN architecture
- Residual Depthwise Separable Convolutions
- Multi-Level Acoustic Feature Fusion
- Channel-wise Early Feature Fusion
- MFCC
- Delta MFCC
- Delta–Delta MFCC
- Mel Spectrogram
- Global Average Pooling
- Only **128,296 parameters**
- 8 Emotion Classes

---

# Repository Structure

```text
SERLiteNet_Baseline/

│
├── SERLiteNet_Baseline.ipynb
├── emotion_recognition_model.keras
├── emotion_recognition_model.h5
│
├── Images/
│   ├── proposed_lightsernet_architecture.png
│   ├── audio_preprocessing_pipeline.png
│   ├── multi_level_acoustic_features.png
│   ├── feature_comparison.png
│   ├── training_accuracy_curve.png
│   ├── training_loss_curve.png
│   ├── confusion_matrix.png
│
└── README.md
```

---

# Proposed SERLiteNet

The proposed SERLiteNet consists of:

- Audio Signal Preprocessing
- Multi-Level Acoustic Feature Extraction
- Channel-wise Early Feature Fusion
- Lightweight Residual CNN
- Softmax Emotion Classifier

The extracted acoustic features include

- MFCC
- Delta MFCC
- Delta–Delta MFCC
- Mel Spectrogram

These complementary feature maps are stacked to form a **40 × 63 × 4** input tensor.

---

# Audio Preprocessing

<p align="center">
<img src="Images/audio_preprocessing_pipeline.png" width="900">
</p>

The speech preprocessing pipeline consists of

- Signal Normalization
- Silence Removal
- Pre-emphasis Filtering

---

# Multi-Level Acoustic Feature Extraction

<p align="center">
<img src="Images/multi_level_acoustic_features.png" width="900">
</p>

Four complementary acoustic representations are extracted:

- MFCC
- Delta MFCC
- Delta–Delta MFCC
- Mel Spectrogram

These representations are fused through channel-wise early feature fusion before being passed to SERLiteNet.

---

# Example Feature Representations

<p align="center">
<img src="Images/feature_comparison.png" width="900">
</p>

The figure illustrates representative multi-level acoustic features extracted from different emotional speech samples.

---

# Model Architecture

| Item | Value |
|------|------:|
| Input Tensor | 40 × 63 × 4 |
| Conv Block 1 | 32 Filters |
| Conv Block 2 | 64 Filters |
| Conv Block 3 | 128 Filters |
| Dense Layer | 64 Neurons |
| Output Classes | 8 |

---

# Model Complexity

| Metric | Value |
|------|------:|
| Total Parameters | **128,296** |
| Trainable Parameters | **126,952** |
| Non-trainable Parameters | **1,344** |

---

# Dataset

This implementation uses the **RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)** dataset.

Emotion classes

- Neutral
- Calm
- Happy
- Sad
- Angry
- Fear
- Disgust
- Surprise

Dataset:

https://zenodo.org/record/1188976

---
https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio

# Training Strategy

The final training pipeline incorporates

- Dataset-Level Feature Normalization
- Class Weighting
- Adam Optimizer
- Early Stopping
- ReduceLROnPlateau
- Model Checkpointing

---



# Performance

| Metric | Value |
|------|------:|
| Test Accuracy | **67.36%** |
| Precision (Weighted) | **0.67** |
| Recall (Weighted) | **0.66** |
| F1-score (Weighted) | **0.65** |

---

# Classification Report

| Emotion | Precision | Recall | F1-score |
|----------|----------:|--------:|---------:|
| Angry | 0.69 | 0.71 | 0.70 |
| Calm | 0.76 | 0.82 | 0.78 |
| Disgust | 0.89 | 0.82 | 0.85 |
| Fear | 0.47 | 0.69 | 0.56 |
| Happy | 0.57 | 0.41 | 0.48 |
| Neutral | 0.58 | 0.74 | 0.65 |
| Sad | 0.62 | 0.47 | 0.54 |
| Surprise | 0.71 | 0.64 | 0.68 |

---

# Ablation Study

| Experiment | Test Accuracy (%) |
|------------|------------------:|
| Baseline SERLiteNet | 14.24 |
| + Dataset-Level Feature Normalization | 26.40 |
| + Class Weighting | **67.36** |

These experiments demonstrate that proper feature normalization and class weighting substantially improve the performance of lightweight speech emotion recognition networks.

---

# Requirements

```bash
pip install tensorflow
pip install librosa
pip install numpy
pip install pandas
pip install matplotlib
pip install scikit-learn
pip install opencv-python
```

---

# Running the Notebook

Execute the notebook sequentially:

1. Import Libraries
2. Dataset Loading
3. Audio Preprocessing
4. Multi-Level Feature Extraction
5. Feature Tensor Construction
6. SERLiteNet Architecture
7. Model Training
8. Performance Evaluation

---

# Future Work

Future research will focus on

- Audio data augmentation
- Attention mechanisms
- Self-supervised acoustic representation learning
- Multimodal emotion recognition

The proposed SERLiteNet serves as the baseline architecture for future improvements in robust speech emotion recognition.

---

# Citation

If you use this repository in your research, please cite

```bibtex
@article{SERLiteNet2026,
  title={SERLiteNet: A Lightweight Residual Depthwise Convolutional Neural Network with Multi-Level Acoustic Feature Fusion for Speech Emotion Recognition},
  author={Your Name},
  journal={Under Review},
  year={2026}
}


## Author

**Ahtisham Urooj**

P.hD. Systems and Control Engineering

King Fahd University of Petroleum and Minerals (KFUPM)

Saudi Arabia
