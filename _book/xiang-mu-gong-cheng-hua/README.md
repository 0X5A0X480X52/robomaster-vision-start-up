---
icon: hammer-brush
---

# 项目工程化

在 RoboMaster 视觉组的项目开发中，工程化能力是保障代码质量、提升协作效率的核心，需重点学习以下内容：

* **重点必须掌握**：
  * **代码版本控制**：掌握 Git 的基础操作（克隆、提交、分支管理、合并），理解团队协作中的分支策略（主分支、开发分支、功能分支的划分），学会通过 Pull Request 进行代码审查与合并，避免代码冲突。学习资料推荐《Git Pro》（中文版），配合 Git 官方文档（[https://git-scm.co](https://git-scm.com/doc)[m/d](https://git-scm.com/doc)[oc](https://git-scm.com/doc)）；视频可参考 B 站 “Git 实战教程：从入门到团队协作”。
  * **使用 CMake 构建 C/C++ 复杂项目**：掌握 CMake 的基本语法和项目构建流程，学会编写 CMakeLists.txt 管理多模块项目，配置第三方库依赖和编译选项，实现跨平台构建。学习资料推荐《CMake Cookbook》，配合 CMake 官方教程（[https://cmake.or](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[g/cm](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[ake](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[/hel](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[p/l](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[a](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[tes](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[t/g](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[uide](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[/tut](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[ori](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[al/i](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[nde](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[x.ht](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)[ml](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)）。
  * **硬件适配与部署**：了解交叉编译基础，确保代码在嵌入式设备（如 Jetson 系列、miniPC）上运行，掌握驱动适配逻辑和一键部署脚本编写。
* **推荐掌握：**
  * **项目结构设计**：学习按功能模块（如图像采集、目标识别、数据传输等）规划目录结构，明确头文件与源文件的分工，确保项目架构清晰，便于维护和扩展。
  * **文档规范**：掌握项目核心文档的编写要求，包括 README（项目说明、环境依赖、部署步骤）、接口文档（函数参数与返回值说明）、代码注释规范。学习资料可参考 Google 的《代码风格指南》中关于文档的部分，结合《编写可读代码的艺术》。
  * **测试与调试**：学习单元测试（如 Google Test 框架）和集成测试方法，掌握调试工具（GDB、VS Code 调试功能）的使用，提升代码稳定性。推荐《Google 测试框架入门指南》，配合 GDB 官方文档（[https://www.gnu](https://www.gnu.org/software/gdb/documentation/)[.org/](https://www.gnu.org/software/gdb/documentation/)[soft](https://www.gnu.org/software/gdb/documentation/)[ware](https://www.gnu.org/software/gdb/documentation/)[/gdb](https://www.gnu.org/software/gdb/documentation/)[/do](https://www.gnu.org/software/gdb/documentation/)[cume](https://www.gnu.org/software/gdb/documentation/)[ntat](https://www.gnu.org/software/gdb/documentation/)[ion/](https://www.gnu.org/software/gdb/documentation/)）。
  * **设计模式与复用**：学习常用设计模式的应用场景，掌握代码复用技巧（封装通用模块、接口设计），提升代码的可维护性和扩展性。推荐《设计模式：可复用面向对象软件的基础》，结合 GitHub 上设计模式示例代码库（[https://github.com](https://github.com/faif/python-patterns)[/fa](https://github.com/faif/python-patterns)[if/](https://github.com/faif/python-patterns)[pyt](https://github.com/faif/python-patterns)[hon-](https://github.com/faif/python-patterns)[pat](https://github.com/faif/python-patterns)[tern](https://github.com/faif/python-patterns)[s](https://github.com/faif/python-patterns)）。
