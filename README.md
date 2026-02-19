# Trash-Image-Classification-Using-SVM-and-Convolutional-Neural-Networks
In terms of methods, we compared the traditional machine learning schemes based on  artificial features and Support Vector Machine (SVM), and the deep learning models of Convolutional Neural Network  (CNN) and Residual Network (ResNet). 
这是一份根据您的论文内容整理的 GitHub 项目 `README.md` 文档模板。它涵盖了项目背景、数据集介绍、方法论对比、实验结果及结论。

---

Here is the `README.md` for your GitHub project, written in English based on your paper.

---

# Trash Image Classification Using SVM and Convolutional Neural Networks

This project implements and compares traditional machine learning and deep learning approaches for automated waste classification. It evaluates the performance of **SVM (with HOG & LBP features)**, a **Standard CNN**, and **ResNet-50** on a large-scale garbage dataset.

## 📖 Introduction

Efficient automatic waste classification is essential for optimizing recycling and addressing environmental challenges. This study develops an image-based classification system to categorize residential and commercial waste into 10 distinct classes. We specifically address challenges like inter-class similarity (e.g., paper vs. cardboard) and cluttered backgrounds using both handcrafted feature engineering and deep hierarchical learning.

## 📊 Dataset

The project uses the **Garbage Classification Dataset (V2)** from Kaggle:

* 
**Total Images**: 19,407.


* 
**Categories**: 10 classes including Battery, Biological, Glass, Cardboard, Clothes, Metal, Paper, Plastic, Shoes, and Trash.


* 
**Data Split**: 64% Training, 16% Validation, and 20% Testing.



## 🛠 Methodology

### 1. Traditional Machine Learning (SVM)

A robust baseline using handcrafted features:

* **Feature Extraction**:
* 
**Multi-Scale LBP**: Captures texture at radii , resulting in a 768-dimensional descriptor.


* 
**Color-Optimized HOG**: Operates directly on RGB channels to preserve color-texture interactions for better structural capture.




* 
**Processing**: High-dimensional features (10,000+) are compressed using **PCA** to the top 4,096 principal components.


* 
**Classifier**: SVM with a **Radial Basis Function (RBF) kernel**.



### 2. Deep Learning (CNN & ResNet)

* 
**Standard CNN**: A custom architecture utilizing sequential convolution, ReLU activation, and max-pooling layers to learn spatial hierarchies automatically.


* 
**ResNet-50**: Utilizes **Transfer Learning** and residual blocks with skip connections to mitigate performance degradation in deep networks.



## 📈 Results

The experimental results demonstrate that deep learning significantly outperforms traditional methods.

| Method | Accuracy |
| --- | --- |
| **SVM + HOG + LBP** | 77.06% |
| **Standard CNN** | 86.60% |
| **ResNet-50** | **96.40%** |

* 
**Conclusion**: While handcrafted features provide a solid baseline (77.06%), the ResNet-50 model achieves the highest accuracy (96.40%) by effectively learning high-level representations for complex waste images.



## 🚀 How to Run

1. 
**Preprocessing**: Input images are resized and normalized.


2. 
**SVM Pipeline**: Run the GPU-accelerated HOG/LBP extractors followed by PCA and SVM training.


3. 
**Deep Learning**: Fine-tune the ResNet-50 model using a small learning rate for stable convergence.













---
