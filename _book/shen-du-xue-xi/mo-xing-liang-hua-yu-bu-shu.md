---
icon: folder-arrow-down
---

# 模型量化与部署

随着深度学习模型在 RoboMaster 视觉系统中的应用日益广泛，**模型的部署效率与运行性能**成为关键。为了能在嵌入式平台（如 Jetson Nano、TX2、树莓派）或上位机中高效运行训练好的模型，我们需要进行**模型量化与部署优化**。

***

## 什么是模型部署？

模型部署指的是：**将训练好的模型转化为在实际设备中可运行的格式，并嵌入到系统中执行推理任务**（如装甲板识别、角度预测等）。

部署目标通常包括：

* 加快模型推理速度；
* 减少内存和功耗；
* 适配低性能设备；
* 与实际工程系统集成（如 C++ 主控、ROS、Jetson、NVIDIA GPU 等）。

***

## 什么是模型量化？

**模型量化（Quantization）** 是一种模型压缩技术，将模型中使用的高精度数据（如 32 位浮点数）转换为低精度表示（如 8 位整数），以减小模型体积、加快运算速度。

**常见量化方式：**

| 类型         | 简介                   |
| ---------- | -------------------- |
| **静态量化**   | 在部署前通过校准数据集统一量化权重与激活 |
| **动态量化**   | 运行时动态量化部分参数（常用于 CPU） |
| **量化感知训练** | 在训练过程中考虑量化误差，精度最优    |

**优点：**

* 模型变小、速度更快；
* 更适合嵌入式设备或边缘部署；
* 对部分模型精度影响有限。

***

## 模型部署常用方式

**1. ONNX（Open Neural Network Exchange）**

* 用于不同框架间模型通用格式转换；
*   支持从 PyTorch 导出为 `.onnx` 格式：

    ```python
    torch.onnx.export(model, dummy_input, "model.onnx")
    ```

**2. TensorRT（NVIDIA 平台优化工具）**

* 针对 NVIDIA GPU/Jetson 的高性能推理引擎；
* 支持 ONNX 转换、量化、优化；
* 提供 C++ 与 Python API，部署在 Jetson Nano/Orin/TX2 等设备上。

**3. TFLite（TensorFlow Lite）**

* 面向移动端与嵌入式设备的轻量部署格式（安卓、树莓派）；
* 可量化为 INT8，部署于低功耗设备。

**4. OpenVINO（Intel 提供）**

* 优化模型在 Intel CPU/GPU/FPGA 上运行；
* 常用于工业边缘计算设备。

***

## 推荐学习资源

**文档资料**

* [PyTorch ONNX 官方指南](https://pytorch.org/docs/stable/onnx.html)
* [NVIDIA TensorRT 文档](https://docs.nvidia.com/deeplearning/tensorrt/)
* [TensorFlow Lite 教程](https://www.tensorflow.org/lite)

####
