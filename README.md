# 🧠 CIFAR-10 Image Classification using PyTorch

![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

A deep learning project implementing a Convolutional Neural Network (CNN) from scratch in PyTorch to classify images from the CIFAR-10 dataset. 

---

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Dataset](#-dataset)
- [Model Architecture](#-model-architecture)
- [Training Details](#-training-details)
- [Results](#-results)
- [Installation & Usage](#-installation--usage)
- [Future Improvements](#-future-improvements)

---

## 🚀 Project Overview
This repository contains a complete pipeline for training and evaluating a custom CNN on the CIFAR-10 dataset. The model successfully learns to extract spatial hierarchies of features from 32x32 color images and categorizes them into one of ten mutually exclusive classes.

---

## 📊 Dataset
The **CIFAR-10** dataset consists of 60,000 32x32 color images in 10 classes, with 6,000 images per class. 
- **Training Set:** 50,000 images
- **Testing Set:** 10,000 images

**Preprocessing applied:**
- Conversion to PyTorch Tensors.
- Normalization to a range of `[-1, 1]` using a mean and standard deviation of `(0.5, 0.5, 0.5)` for all three RGB channels.

---

## 🏗️ Model Architecture
The network is built using standard CNN principles, consisting of three convolutional blocks followed by a fully connected classifier.

| Layer Type | Parameters | Activation | Output Shape |
| :--- | :--- | :--- | :--- |
| **Input** | RGB Image | - | `3 x 32 x 32` |
| **Conv2D + MaxPool** | Filters: 32, Kernel: 3x3, Padding: 1 | ReLU | `32 x 16 x 16` |
| **Conv2D + MaxPool** | Filters: 64, Kernel: 3x3, Padding: 1 | ReLU | `64 x 8 x 8` |
| **Conv2D + MaxPool** | Filters: 128, Kernel: 3x3, Padding: 1 | ReLU | `128 x 4 x 4` |
| **Flatten** | - | - | `2048` |
| **Linear (Dense)** | Units: 256 | ReLU | `256` |
| **Linear (Output)** | Units: 10 | - | `10` |

---

## ⚙️ Training Details
- **Loss Function:** Cross-Entropy Loss (`nn.CrossEntropyLoss`)
- **Optimizer:** Adam (`optim.Adam`)
- **Batch Size:** 64
- **Epochs:** 10

During training, the loss smoothly converges from **0.75** down to **0.11**, indicating successful learning and feature extraction.

---

## 📈 Results
After 10 epochs of training, the model achieves the following performance on the unseen test set:

- **Test Accuracy:** **74.71%**

---

## 🛠️ Installation & Usage

### Prerequisites
Ensure you have Python installed, along with the required machine learning libraries.

```bash
pip install torch torchvision jupyter
