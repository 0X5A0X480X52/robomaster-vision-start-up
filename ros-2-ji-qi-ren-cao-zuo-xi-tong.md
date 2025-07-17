---
icon: robot-astromech
---

# Ros 2 机器人操作系统

## 为什么我们需要 ROS 2？

在 RoboMaster 视觉系统中，往往涉及多个传感器（如相机、IMU）、多个处理模块（如图像处理、目标识别、定位预测），以及与底层控制模块的数据交互。为了让这些模块解耦且协同运行，我们使用 **ROS 2（Robot Operating System 2）**，它是现代机器人软件开发的标准通信中间件，具有以下优点：

* **模块化架构**：各个功能单元作为节点（Node）独立运行，方便复用、替换和并行开发。
* **强大的通信机制**：支持发布/订阅、服务/响应、动作等通信模型，适用于传感器数据传输、状态同步与控制指令传递。
* **良好的跨平台性能**：相比 ROS 1，ROS 2 更加适合嵌入式设备、RTOS 和多线程程序。
* **社区与生态活跃**：提供众多可用组件，如导航、感知、仿真工具等。

在 RoboMaster 项目中，ROS 2 是贯穿整个软件架构的“神经中枢”。

***

## 目标：能够独立编写 ROS 2 节点和程序

需掌握如何使用 ROS 2 编写节点，实现模块之间的通信。基本技能包括：

1.  **创建功能包（package）**：

    ```bash
    ros2 pkg create --build-type ament_cmake my_vision_node
    ```

    或使用 Python：

    ```bash
    ros2 pkg create --build-type ament_python my_vision_node
    ```
2. **编写节点程序（C++/Python）**：
   * 创建发布者（Publisher）节点定期发送图像处理结果；
   * 创建订阅者（Subscriber）节点接收目标位置信息；
   * 使用服务（Service）实现图像分析请求-响应机制；
   * 使用参数（Parameter）动态调节识别阈值等参数；
   *   示例（Python）：

       ```python
       import rclpy
       from rclpy.node import Node
       from std_msgs.msg import String

       class VisionPublisher(Node):
           def __init__(self):
               super().__init__('vision_publisher')
               self.publisher_ = self.create_publisher(String, 'vision_topic', 10)
               self.timer = self.create_timer(0.5, self.timer_callback)

           def timer_callback(self):
               msg = String()
               msg.data = 'Detected armor plate'
               self.publisher_.publish(msg)
               self.get_logger().info(f'Publishing: {msg.data}')

       def main(args=None):
           rclpy.init(args=args)
           node = VisionPublisher()
           rclpy.spin(node)
           node.destroy_node()
           rclpy.shutdown()
       ```
3.  **编译与运行**：

    ```bash
    colcon build
    source install/setup.bash
    ros2 run my_vision_node vision_publisher
    ```
4. **基本调试工具**：
   * `ros2 topic list / echo / pub / hz`
   * `ros2 run rqt_graph rqt_graph`（可视化节点拓扑）

***

## 使用 Foxglove Studio 进行可视化 Debug

[Foxglove Studio](https://foxglove.dev/) 是一款强大的机器人数据可视化平台，兼容 ROS 2，适合用于调试视觉算法和系统状态。功能包括：

* **查看图像话题（Image）**：可视化摄像头发布的图像数据；
* **绘制时间线**：观察不同消息（目标坐标、预测轨迹、开火命令等）时间同步情况；
* **3D 视图**：可视化目标识别位置与姿态信息；
* **实时调试**：支持通过 WebSocket/rosbridge 连接 ROS 2 实例，或导入 `.mcap` 数据包回放历史记录。

使用步骤简述：

1. 安装 Foxglove Studio（支持 Windows/Mac/Linux）；
2.  ROS 2 环境中运行：

    ```bash
    ros2 launch rosbridge_server rosbridge_websocket_launch.xml
    ```
3. 打开 Foxglove Studio，选择“ROS 2 WebSocket”连接；
4. 订阅需要可视化的 topic，如 `/image_raw`, `/target_pose`, `/fire_command` 等；
5. 拖入合适的 Widget（Image、3D Panel、Plot 等）进行实时观察。

***

## 推荐学习资源

**官方文档**

* ROS 2 官方文档：[https://docs.ros.org/en/rolling/index.html](https://docs.ros.org/en/rolling/index.html)
* ROS 2 Tutorials（强烈推荐动手练习）：[https://docs.ros.org/en/rolling/Tutorials.html](https://docs.ros.org/en/rolling/Tutorials.html)

**中文资料**

* ROS2中文社区及入门教程：[https://fishros.org.cn/docs/ros2](https://fishros.org.cn/docs/ros2)[http://dev.ros2.fishros.com/](http://dev.ros2.fishros.com/)\
  （由国内 Fishbot 团队维护，内容完整易懂）

**视频课程**

* B站【鱼香ROS】动手学ROS2|ROS2基础入门到实践教程|小鱼带你手把手学习ROS2（BV号：BV1gr4y1Q7j5）
* Foxglove Studio 教程：[https://foxglove.dev/blog/](https://foxglove.dev/blog/)
