---
icon: arrows-rotate-reverse
---

# 坐标变换简介

在 RoboMaster 比赛和机器人视觉任务中，**坐标系变换**是一项核心技术，用于在不同参考系之间正确描述和计算物体的位置与姿态（位置 + 方向）。例如，摄像头捕捉到的装甲板位置需要从图像坐标系转换到机器人坐标系，进一步用于导航、控制与打击。

## 常见坐标系类型

1. **像素坐标系（Pixel Coordinate System）**
   * 以图像左上角为原点，单位为像素。
   * 用于图像处理任务，如目标检测输出的边界框位置。
2. **相机坐标系（Camera Coordinate System）**
   * 以相机光心为原点，Z 轴沿光轴方向，X、Y 轴定义依据右手系。
   * 用于描述相机视野中的物体三维位置。
3. **世界坐标系（World Coordinate System）**
   * 通常为比赛场地或机器人自身的参考坐标系。
   * 所有设备（相机、陀螺仪、目标）的位置需映射到此坐标系下统一描述。
4. **机械坐标系 / 云台坐标系**
   * 用于控制云台转向角度（pitch/yaw）。
   * 云台与相机安装存在一定旋转与平移偏移，需要通过坐标变换校正。

## 典型变换形式

坐标变换通常包含**旋转（Rotation）与平移（Translation）**，可使用如下数学工具表示：

* **齐次变换矩阵（Homogeneous Transformation Matrix）**：

$$
T = \begin{bmatrix} R & t \\ 0 & 1 \end{bmatrix}, \quad \text{其中 } R \in \mathbb{R}^{3\times3},\ t \in \mathbb{R}^3
$$

用于将一个坐标点从 A 坐标系变换到 B 坐标系：

$$
\mathbf{P}_B = T_{A \rightarrow B} \cdot \mathbf{P}_A
$$

* **欧拉角与四元数**：用于表示旋转关系，适用于三维姿态的描述。
  * **欧拉角（Euler Angles）**：使用绕固定坐标轴（如 X、Y、Z）旋转的三个角度（通常称为“roll-滚转”、“pitch-俯仰”、“yaw-偏航”）来表示物体的姿态。欧拉角直观易懂，但存在**万向节死锁（Gimbal Lock）**&#x7B49;问题，不适用于连续旋转场景。
  * **四元数（Quaternion）**：由一个实数部分和一个三维向量部分组成，能以更紧凑、连续、无奇异点的方式表示旋转，广泛应用于三维图形、机器人、SLAM 和视觉导航等领域。

## 坐标系变换应用场景

* **PNP 问题求解**：已知目标 3D 点与图像 2D 点，通过相机内参解算目标在相机坐标系下的位置。
* **目标跟踪与预测**：将图像帧中提取的目标位置变换为云台角度，实现闭环控制。
* **多传感器融合**：结合 IMU、激光雷达等传感器信息，需进行多坐标系间的数据融合。

## Python 和 C++ 中常用的坐标变换库

| 功能     | Python 库                            | C++ 库                   |
| ------ | ----------------------------------- | ----------------------- |
| 齐次变换   | `numpy` + `scipy.spatial.transform` | Eigen                   |
| PNP 解算 | `cv2.solvePnP` (OpenCV)             | `cv::solvePnP` (OpenCV) |
| 四元数计算  | `scipy.spatial.transform.Rotation`  | Eigen、Sophus            |
| TF 坐标树 | `tf` / `tf2_ros` (ROS)              | `tf2` (ROS)             |

