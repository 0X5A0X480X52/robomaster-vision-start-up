---
icon: head-side-goggles
---

# OpenCV简介

## 什么是 OpenCV？

**OpenCV（Open Source Computer Vision Library）** 是一个开源的、跨平台的计算机视觉和图像处理库，由 Intel 于 2000 年发起，目前已广泛应用于学术研究、工业开发和机器人竞赛中。

在 RoboMaster 比赛中，OpenCV 是最常用的图像处理工具，配合 C++ 或 Python 编程语言，可以快速实现图像采集、处理、目标检测、特征提取等任务。

***

## OpenCV 的主要功能模块

* **图像处理**：滤波、边缘检测、形态学操作、直方图处理等；
* **几何变换**：旋转、缩放、仿射变换、透视变换；
* **特征提取与匹配**：SIFT、ORB、FAST 等；
* **摄像头操作**：图像/视频读取、实时视频流处理；
* **相机标定与三维重建**：畸变矫正、姿态估计、投影模型；
* **GUI工具**：图像显示、轨迹条调参、鼠标交互等。

大部分传统的计算机视觉算法都可借助OpenCV提供的功能模块实现。

***

## OpenCV 的优点

* **开源免费**，文档丰富；
* **跨平台支持**（Windows、Linux、macOS、Raspberry Pi）；
* **接口语言多样**：支持 C++, Python, Java 等；
* **高性能**：大量函数使用底层 SIMD 优化，可用于实时处理任务。

***

## 推荐学习资源

**官方资料**

* [OpenCV 官方文档（英文）](https://docs.opencv.org/master/)
* [OpenCV-Python 教程](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html)

有能力的可以直接尝试阅读官方的OpenCV教程（英文）。

**中文学习资料**

* 《OpenCV 4 应用开发：入门进阶与工程化实践》：适合初学者系统入门，含大量实例代码；
* 哔哩哔哩视频教程：BV1YnELzfEFZ 等
* 菜鸟教程：[https://www.runoob.com/opencv/opencv-tutorial.html](https://www.runoob.com/opencv/opencv-tutorial.html)
* CSDN博客与知乎专栏：搜索 "OpenCV 入门"等关键词，社区资源丰富。

**建议学习路线**

1. 学会使用摄像头读取图像并显示；
2. 掌握图像预处理方法（灰度化、滤波、边缘检测）；
3. 学会基本几何变换与图像操作；
4. 进阶学习特征提取、轮廓分析、颜色分割；

比较推荐先通过python版本的opencv了解其各个模块的基本功能，再在实际开发时通过C/C++版本的opencv提高运行速度与效率。

***

OpenCV 是实现 RoboMaster 视觉任务的基础工具，理解其使用方式和背后的视觉原理，是你成长为一名视觉开发者的第一步。
