---
icon: fire
---

# CUDA与pytorch

## CUDA：让程序“跑在显卡上”的加速引擎

### **什么是 CUDA？**

**CUDA（Compute Unified Device Architecture）** 是 NVIDIA 提供的 **通用 GPU 并行计算平台**。它允许开发者用 C/C++、Python 等语言，**直接调用显卡资源进行大规模并行计算**。

### **为什么要用 CUDA？**

* **加速深度学习训练**：大多数深度学习模型参数众多，训练过程计算量极大。借助 CUDA 可以让神经网络在显卡上运行，速度提升数十倍。
* **支持主流深度学习框架**：如 PyTorch、TensorFlow 都可以自动调用 CUDA 来实现 GPU 加速。

### **注意事项：**

* CUDA 只能在 **NVIDIA 显卡** 上运行；
* 使用 CUDA 需要配套安装 **NVIDIA 驱动 + CUDA Toolkit + cuDNN**；
* PyTorch 等框架通常提供 **预编译好的 CUDA 版本**，建议通过 `conda` 安装对应版本以避免配置问题。

***

## PyTorch：深度学习的强大框架

### **什么是 PyTorch？**

**PyTorch** 是一个由 Facebook AI 研究院（FAIR）开发的**开源深度学习框架**，具有以下特点：

* 使用 **动态图机制**，调试灵活，语法贴近 Python；
* 支持 **自动求导**，适合研究与原型开发；
* 社区活跃，文档齐全，支持大多数深度学习任务（图像、文本、时间序列等）；
* 与 **CUDA 深度集成**，支持 GPU 加速训练和推理。

**示例：简单的 PyTorch 神经网络训练框架**

```python
import torch
import torch.nn as nn
import torch.optim as optim

# 定义模型
class Net(nn.Module):
    def __init__(self):
        super().__init__()
        self.fc = nn.Linear(10, 2)

    def forward(self, x):
        return self.fc(x)

model = Net().cuda()

# 假设有数据和标签
inputs = torch.randn(32, 10).cuda()
labels = torch.randint(0, 2, (32,)).cuda()

# 损失函数与优化器
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters())

# 训练一步
outputs = model(inputs)
loss = criterion(outputs, labels)
loss.backward()
optimizer.step()
```

### PyTorch 在 RoboMaster 中的应用

* **目标检测模型训练**：如训练 YOLO、Faster R-CNN 等识别装甲板；
* **图像分类模型训练**：如识别能量机关符号类别；
* **轨迹预测/策略学习**：结合时间序列数据、RNN/Transformer 模型；
* **部署到嵌入式设备**：模型训练后可转换为 ONNX 或 TensorRT 格式部署到 Jetson 平台。

***

## 推荐学习资源

**官方文档：**

* [PyTorch 中文官网](https://pytorch.apachecn.org/)
* [PyTorch 官方教程](https://pytorch.org/tutorials/)

**学习视频：**

* B站：搜索“李沐 PyTorch”，推荐结合《动手学深度学习》一起食用。

**实战项目平台：**

* Kaggle / Colab（免费 GPU）
* HuggingFace、Ultralytics（YOLO 系列开源项目）
* Jetson Nano / Xavier：可部署轻量模型至边缘设备
