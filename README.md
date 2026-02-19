# Trash-Image-Classification-Using-SVM-and-Convolutional-Neural-Networks
In terms of methods, we compared the traditional machine learning schemes based on  artificial features and Support Vector Machine (SVM), and the deep learning models of Convolutional Neural Network  (CNN) and Residual Network (ResNet). 
这是一份根据您的论文内容整理的 GitHub 项目 `README.md` 文档模板。它涵盖了项目背景、数据集介绍、方法论对比、实验结果及结论。

---

# Trash Image Classification Using SVM and CNNs

## 📖 项目简介

随着全球城市化的加速，高效的自动垃圾分类是优化回收利用和应对环境挑战的关键 。本项目开发并评估了一个基于图像的垃圾分类系统，对比了基于人工特征的传统机器学习方案（SVM）与深度学习模型（CNN 和 ResNet-50）的性能 。

## 📊 数据集 (Garbage Classification Dataset V2)

本研究使用来自 Kaggle 的垃圾分类数据集 V2 ：

* 
**样本总量**：19,407 张图像 。


* 
**分类数量**：10 个类别（电池、生物垃圾、纸板、衣服、玻璃、金属、纸张、塑料、鞋子、垃圾） 。


* 
**挑战点**：复杂的背景、类内差异大、类间相似度高（如纸张与纸板） 。



## 🛠 方法论

### 1. 传统机器学习 (SVM)

利用 GPU 加算的特征提取器建立基准模型 ：

* **特征提取**：
* 
**多尺度 LBP**：通过三个半径（R=1, 2, 3）提取纹理信息，形成 768 维描述符 。


* 
**色彩优化 HOG**：直接在 RGB 通道上操作以保留色彩-纹理交互信息，捕捉边缘和轮廓 。




* 
**降维与分类**：使用 PCA 提取前 4096 个主成分，并配合 **RBF 核** 的 SVM 进行分类 。



### 2. 深度学习 (CNN & ResNet)

* 
**标准 CNN**：通过卷积、ReLU 激活和池化层自动学习层次化空间特征 。


* 
**ResNet-50**：采用残差学习（Residual Learning）解决深层网络中的退化问题，并通过迁移学习（Transfer Learning）进行微调 。



## 📈 实验结果

在 19,407 张图像的测试集上，各模型的准确率表现如下 ：

| 模型方案 | 准确率 (Accuracy) |
| --- | --- |
| **SVM + HOG + LBP** | 77.06% 

 |
| **标准 CNN** | 86.6% 

 |
| **ResNet-50** | <br>**96.4%** 

 |

### 核心结论

* 深度学习模型在准确性和泛化能力上显著优于传统 SVM 。


* ResNet-50 的残差结构有效提升了高层特征的学习能力，是处理复杂图像分类任务的首选方案 。



## 🚀 快速开始

1. **环境配置**：确保安装了 GPU 支持的深度学习框架（如 PyTorch）。
2. 
**数据准备**：从 Kaggle 下载数据集并按类别存放在子目录下 。


3. **模型训练**：
* 传统模型：运行 HOG/LBP 提取脚本后训练 SVM。
* 深度模型：使用较低的学习率对 ResNet-50 进行微调 。









---
