---
icon: robot
---

# 机器学习

## 什么是机器学习？

**机器学习（Machine Learning, ML）** 是人工智能的重要分支，指的是让计算机**从数据中自动学习规律，并在未来做出预测或决策**，而无需显式编写具体规则。

在 RoboMaster 比赛中，机器学习可用于识别目标（如装甲板）、预测运动轨迹、判断敌方行为等。

***

## 机器学习的核心流程

机器学习通常包括以下步骤：

1. **数据采集与预处理**：收集图像、坐标、标签等数据，进行清洗与标准化；
2. **特征工程**：提取代表数据本质的特征；
3. **模型选择与训练**：选择合适算法，利用训练数据拟合模型；
4. **模型评估与调优**：使用测试集评估模型性能，调整参数；
5. **预测与部署**：将模型用于实际任务，如目标识别、路径预测等。

***

## 机器学习的主要任务类型

1. **监督学习（Supervised Learning）**

模型在“带标签”的数据上训练。

* **分类**（Classification）：判断样本属于哪个类别
  * 应用：识别图像中的装甲板颜色/类别；
* **回归**（Regression）：预测连续数值
  * 应用：预测敌方下一帧位置或角度；

常用算法：KNN、SVM、决策树、随机森林、线性回归、神经网络等。

2. **无监督学习（Unsupervised Learning）**

在没有标签的数据中发现数据结构或模式。

* **聚类**（Clustering）：将相似数据归为一类
  * 应用：分析对手策略模式、图像区域分割；
* **降维**（Dimensionality Reduction）：简化数据结构，保留关键信息
  * 应用：特征压缩、可视化；

常用算法：K-Means、DBSCAN、PCA（主成分分析）等。

3. **半监督学习 / 自监督学习**

结合少量标签数据与大量无标签数据训练模型，逐渐受到关注。

***

## 推荐学习资源

**入门书籍**

* **《统计学习方法》**（李航）：通俗清晰，适合零基础了解核心概念和算法原理；
* **《机器学习》**（周志华）：理论深入，适合进一步进阶学习；
* **《Python机器学习实战》**：代码丰富，实操性强，推荐结合项目练习。

**在线课程**

* **吴恩达《Machine Learning》课程（Coursera）**（英文/有中字幕）\
  链接：[https://www.coursera.org/learn/machine-learning](https://www.coursera.org/learn/machine-learning)\
  简明易懂，涵盖监督学习、无监督学习、过拟合、正则化等基础内容；
* **B站学习推荐**：
  * 搜索关键词 “机器学习 吴恩达 中文版”
  * 或“机器学习入门教程 Python实战”

&#x20;**实战平台**

* **Kaggle**（[https://www.kaggle.com/）：数据科学竞赛平台，适合找练习项目；](https://www.kaggle.com/%EF%BC%89%EF%BC%9A%E6%95%B0%E6%8D%AE%E7%A7%91%E5%AD%A6%E7%AB%9E%E8%B5%9B%E5%B9%B3%E5%8F%B0%EF%BC%8C%E9%80%82%E5%90%88%E6%89%BE%E7%BB%83%E4%B9%A0%E9%A1%B9%E7%9B%AE%EF%BC%9B)
* **Scikit-learn**（Python常用ML库）：提供众多经典算法和可视化工具；
* **Google Colab**：支持免费云端训练模型，适合初学者试验代码。
