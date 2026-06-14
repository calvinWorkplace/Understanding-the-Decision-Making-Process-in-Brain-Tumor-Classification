<div align="center">

# 🧠 Understanding the Decision-Making Process in Brain Tumor Classification

[![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python)](https://python.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.18-orange?style=for-the-badge&logo=tensorflow)](https://tensorflow.org)
[![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red?style=for-the-badge&logo=keras)](https://keras.io)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter)](https://jupyter.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

> **Explainable AI meets Medical Imaging** — A comparative study of CNN-based deep learning models for brain tumor classification with interpretability analysis using Average Drop metrics.

</div>

---

## 🔬 Overview

Brain tumor classification is a critical task in medical imaging that demands both **high accuracy** and **interpretability**. This project investigates the decision-making process of five state-of-the-art Convolutional Neural Network (CNN) architectures applied to MRI brain scan classification.

The central goal is not just to classify tumors accurately, but to **understand why** the models make their predictions — a key requirement in medical AI systems where transparency can be life-saving.

### Key Highlights

- 🏆 Trained and evaluated **5 CNN architectures** on brain MRI data
- 📊 Used **Average Drop** as the primary explainability metric
- 🧪 Achieved **training accuracy up to ~99.98%** across models
- 📈 Comprehensive comparison of model interpretability vs performance

---

## 🗂️ Dataset

The dataset consists of brain MRI images organized into **training and validation splits**, with images resized to **200×200 pixels** for model input.

📥 **Source:** [Brain Tumor MRI Scans — Kaggle (rm1000)](https://www.kaggle.com/datasets/rm1000/brain-tumor-mri-scans)

| Split      | Samples |
|------------|---------|
| Training   | 5,717   |
| Validation | 1,311   |

The images represent various brain scan types used to detect the presence and characteristics of brain tumors.

---

## 🤖 Models

Five powerful CNN architectures were implemented using **Transfer Learning** with ImageNet pre-trained weights:

| Model            | Architecture Type  | Parameters |
|------------------|--------------------|------------|
| **VGG16**        | Sequential CNN     | ~138M      |
| **ResNet50**     | Residual Network   | ~25M       |
| **InceptionV3**  | Inception Modules  | ~23M       |
| **DenseNet121**  | Dense Connections  | ~8M        |
| **EfficientNetB3** | Compound Scaling | ~12M       |

All models were fine-tuned with:

- **Optimizer**: Adam with ReduceLROnPlateau scheduler
- **Loss**: Categorical Crossentropy
- **Epochs**: 50
- **Input Size**: 200×200×3

---

## 📊 Results

### Average Drop (Explainability Metric)

Average Drop measures how much the model's confidence **drops** when important regions are removed. A **lower Average Drop** indicates the model relies on more meaningful, focused regions for its predictions — making it more interpretable.

| Model              | Average Drop (%) | Interpretability   |
|--------------------|------------------|--------------------|
| **ResNet50**       | 40.11%           | ⭐⭐⭐⭐⭐ Best    |
| **EfficientNetB3** | 46.71%           | ⭐⭐⭐⭐           |
| **VGG16**          | 48.29%           | ⭐⭐⭐             |
| **DenseNet121**    | 62.07%           | ⭐⭐               |
| **InceptionV3**    | 70.52%           | ⭐                 |

> **ResNet50 achieved the lowest Average Drop (40.11%)**, making it the most interpretable model for brain tumor classification in this study.

---

## 📁 Project Structure

```
📦 Understanding-the-Decision-Making-Process-in-Brain-Tumor-Classification
├── 📂 Code/
│   ├── 🔧 PreProcessingData.ipynb      # Data loading, augmentation & preprocessing
│   ├── 🧠 VGG16.ipynb                  # VGG16 model training & evaluation
│   ├── 🧠 Resnet50.ipynb               # ResNet50 model training & evaluation
│   ├── 🧠 Inception_V3.ipynb           # InceptionV3 model training & evaluation
│   ├── 🧠 Densenet121.ipynb            # DenseNet121 model training & evaluation
│   ├── 🧠 EfficientNetB3.ipynb         # EfficientNetB3 model training & evaluation
│   └── 📊 AverageDrop.ipynb            # Explainability analysis & model comparison
├── 📄 Final Paper.pdf                   # Full research paper
└── 📝 README.md
```

---

## 🔍 Methodology

### Pipeline Overview

```
MRI Images → Preprocessing → Transfer Learning → Fine-tuning → Prediction → Explainability Analysis
```

1. **Data Preprocessing** — Images are loaded, resized to 200×200, normalized, and split into train/validation sets.
2. **Transfer Learning** — Pre-trained ImageNet weights are used as the backbone for each CNN architecture.
3. **Fine-tuning** — Models are trained with custom classification heads and optimized using the Adam optimizer with learning rate scheduling.
4. **Explainability Analysis** — The **Average Drop** metric is computed for each model to quantify interpretability. Lower values indicate the model is using more diagnostically relevant features.

### Average Drop Formula

$$\text{Average Drop} = \frac{1}{N} \sum_{i=1}^{N} \frac{\max(0,\ Y_i^c - O_i^c)}{Y_i^c} \times 100\%$$

Where:
- $Y_i^c$ = model confidence on the original image
- $O_i^c$ = model confidence after masking salient regions

---

## 📄 Paper

The full research paper is available in this repository:

📥 [**Download Final Paper (PDF)**](./Final%20Paper.pdf)

The paper covers:
- Literature review on brain tumor classification with deep learning
- Detailed methodology and experimental setup
- Statistical analysis of model performance
- Discussion on explainability in medical AI

---

## 🛠️ Technologies Used

| Technology          | Purpose                        |
|---------------------|--------------------------------|
| **TensorFlow 2.18** | Deep learning framework        |
| **Keras**           | High-level neural network API  |
| **OpenCV**          | Image preprocessing            |
| **NumPy**           | Numerical computations         |
| **Matplotlib**      | Visualization & plotting       |
| **Jupyter Notebook**| Interactive development        |

---

## 👤 Author

**calvinWorkplace**

[![GitHub](https://img.shields.io/badge/GitHub-calvinWorkplace-181717?style=flat-square&logo=github)](https://github.com/calvinWorkplace)

---

<div align="center">

*This project was developed as part of academic research in medical image analysis and explainable AI.*

⭐ **If you find this project helpful, please consider giving it a star!** ⭐

</div>
