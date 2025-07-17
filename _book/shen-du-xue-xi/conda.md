---
icon: c
---

# conda

## 什么是 Conda？

**Conda** 是一个**跨平台的包管理和环境管理工具**，支持 Python、C++ 等多种语言的依赖管理。它最初由 Anaconda 公司推出，常用于科学计算、数据分析和人工智能项目的环境构建。

Conda 能帮助开发者轻松解决“包冲突”、“依赖混乱”等问题，是部署 RoboMaster 视觉模块和深度学习模型时非常重要的工具。

***

## Conda 的主要功能

**1. 虚拟环境管理**

* 通过 Conda 可以为不同项目创建独立的 Python 环境，互不干扰。
* 每个环境可指定 Python 版本，避免系统环境混乱。

常用命令示例：

```bash
conda create -n rm_vision python=3.10
conda activate rm_vision
conda deactivate
conda remove -n rm_vision --all
```

**2. 包管理与安装依赖**

Conda 可以安装、更新、卸载各种科学计算与机器学习相关库（如 OpenCV、PyTorch、Numpy 等），自动处理依赖关系。

示例：

```bash
conda install opencv
conda install pytorch torchvision torchaudio -c pytorch
```

也可以使用 `pip` 与 Conda 混合使用（推荐先使用 Conda 安装大库）。

***

## 推荐学习资源

* 官方文档：
  * [https://docs.conda.io/](https://docs.conda.io/)
* 入门教程：
  * B 站搜索 “conda 虚拟环境配置”、“conda vs pip” 等关键词；
  * 菜鸟教程：[https://www.runoob.com/python-qt/anaconda-tutorial.html](https://www.runoob.com/python-qt/anaconda-tutorial.html)

