---
layout: post
title: "深度学习入门：从感知机到CNN"
date: 2026-02-15 14:30:00 +0800
categories: [深度学习]
tags: [深度学习, 计算机视觉, PyTorch]
excerpt: "从感知机出发，逐步构建卷积神经网络，理解深度学习的基本原理。"
image: /assets/images/covers/cover.jpg
---

## 引言

深度学习是机器学习的一个分支，通过多层神经网络自动学习数据的层次化特征表示<cite>[1]</cite>。本文从最简单的感知机模型出发，逐步构建对卷积神经网络（CNN）的理解。

---

## 感知机

感知机是神经网络的基本单元。给定输入向量 $x \in \mathbb{R}^n$，权重 $w$，偏置 $b$，输出为：

$$
y = \sigma\left(\sum_{i=1}^{n} w_i x_i + b\right)
$$

其中 $\sigma$ 是激活函数。

---

## CNN 架构

现代 CNN 由卷积层、池化层和全连接层堆叠而成<cite>[2]</cite>：

```mermaid
graph LR
    A[输入图像] --> B[卷积层<br/>特征提取]
    B --> C[池化层<br/>降采样]
    C --> D[全连接层<br/>分类输出]
    style A fill:#1a237e,stroke:#4299e1,color:#e8edf5
    style B fill:#1b2d3a,stroke:#667eea,color:#e8edf5
    style C fill:#1b2d3a,stroke:#667eea,color:#e8edf5
    style D fill:#1a2a1a,stroke:#48bb78,color:#e8edf5
```

---

## PyTorch 实现

```python
import torch
import torch.nn as nn

class SimpleCNN(nn.Module):
    def __init__(self):
        super().__init__()
        self.conv = nn.Conv2d(1, 32, 3)   # 卷积层
        self.fc = nn.Linear(32 * 26 * 26, 10)  # 全连接层

    def forward(self, x):
        x = torch.relu(self.conv(x))
        x = x.view(x.size(0), -1)
        return self.fc(x)
```

---

## 总结

从感知机到 CNN，深度学习的核心思想是层次化特征学习。PyTorch 提供了简洁的 API 来构建和训练这些模型。

---

## 参考文献

1. *Deep Learning.* Goodfellow I, Bengio Y, Courville A. MIT Press, 2016.  
   <https://www.deeplearningbook.org>
2. *ImageNet Classification with Deep Convolutional Neural Networks.* Krizhevsky A, Sutskever I, Hinton G. NeurIPS, 2012.  
   <https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks>
{: .references }
