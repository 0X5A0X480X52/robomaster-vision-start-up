---
icon: hammer
---

# Makefile与CMake

在 RoboMaster 视觉组中，我们常使用 C/C++ 编写图像处理、通信、硬件控制等模块。为了高效管理这些源文件及其依赖关系，**构建系统（Build System）** 就显得尤为重要，其中最常见的工具就是 **Makefile 与 CMake**。

***

## Makefile：传统的自动构建工具

**什么是 Makefile？**

**Makefile** 是一个用于指导 `make` 工具如何编译工程文件的脚本，定义了编译规则、依赖关系与构建方式。

**结构示例：**

```make
# 编译器
CC = g++
CFLAGS = -Wall -g

# 源文件与目标文件
SRC = main.cpp camera.cpp detect.cpp
OBJ = $(SRC:.cpp=.o)
TARGET = vision_app

# 默认构建目标
$(TARGET): $(OBJ)
	$(CC) $(OBJ) -o $(TARGET)

# 清除构建文件
clean:
	rm -f $(OBJ) $(TARGET)
```

**优点：**

* 简洁、灵活，适合小型工程；
* 可完全控制每一步构建流程。

**局限：**

* 跨平台困难，Windows/Linux 语法略有差异；
* 难以管理大型项目，手动写依赖繁琐。

***

## CMake：现代化的跨平台构建系统

**什么是 CMake？**

**CMake** 是一种高级的、跨平台的构建系统生成器。它能根据 `CMakeLists.txt` 文件**自动生成对应平台的 Makefile 或 Visual Studio 工程文件**。

**为什么用 CMake？**

* 跨平台（Linux、Windows、macOS）；
* 自动处理依赖关系；
* 支持大型工程模块组织；
* 与 ROS、OpenCV、Eigen 等库无缝集成；
* 可以生成 Makefile、Ninja、Visual Studio 工程等多种后端构建脚本。

**示例：简单的 CMakeLists.txt**

```cmake
cmake_minimum_required(VERSION 3.10)
project(vision_app)

# 使用 C++17
set(CMAKE_CXX_STANDARD 17)

# 查找依赖库（如 OpenCV）
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# 添加源文件
add_executable(vision_app main.cpp camera.cpp detect.cpp)

# 链接库
target_link_libraries(vision_app ${OpenCV_LIBS})
```

构建流程：

```bash
mkdir build
cd build
cmake ..
make
```

***

## Makefile vs. CMake

| 比较维度   | Makefile | CMake                  |
| ------ | -------- | ---------------------- |
| 跨平台    | 否（手动处理）  | ✅ 自动生成不同平台构建系统         |
| 适合项目规模 | 小型项目     | 中大型项目，模块化、可扩展          |
| 易用性    | 需要手写依赖关系 | 自动依赖管理，结构清晰            |
| 主流支持   | ✅ 被支持    | ✅ 被支持，ROS、OpenCV 等广泛使用 |

***

## 推荐学习资源

&#x20;**文档教程**

* [CMake 官方文档](https://cmake.org/documentation/)
* [Makefile 教程（廖雪峰）](https://www.liaoxuefeng.com/wiki/897692888725344)
