---
description: 《C/C++从入门到放弃》
icon: copyright
---

# C/C++ 入门

在 RoboMaster 视觉组的技术实现中，C/C++ 占据着核心地位。它们凭借接近硬件的特性和高效的执行速度，成为机器人底层控制与高性能算法落地的关键工具。例如，在视觉算法的实时性要求极高的场景中，如步兵机器人的自瞄系统，需要在毫秒级时间内完成装甲板识别、弹道计算等一系列操作，C/C++ 编写的代码能直接操作内存、调用硬件接口，最大程度减少运行延迟，确保机器人在高速对抗中精准响应。同时，很多底层库（如 OpenCV 的核心模块、机器人控制系统的驱动库）都是用 C/C++ 开发的，掌握这两种语言能让开发者深入理解库的实现原理，便于进行二次开发和优化。​

C 和 C++ 既有联系又有区别。C 语言是面向过程的编程语言，语法简洁紧凑，专注于数据结构和算法的实现，适合开发操作系统、嵌入式系统等底层软件，在 RoboMaster 中常用于编写与硬件直接交互的驱动程序，如电机控制、传感器数据读取等。C++ 则在 C 语言的基础上引入了面向对象的思想，增加了类、继承、多态等特性，同时兼容 C 语言的语法，既可以进行底层开发，又能更高效地组织复杂的程序结构，比如在构建视觉算法的模块化框架时，用类封装图像采集、预处理、识别等功能，能提高代码的可维护性和复用性。

学习资料方面，C 语言推荐《C Primer Plus》，这本书循序渐进地讲解了 C 语言的基本语法、指针、数组、函数等核心内容，配有大量实例和练习题，适合零基础入门；视频课程可参考 B 站 “翁恺 C 语言程序设计”，老师讲解细致，结合实际案例帮助理解。C++ 则可以从《C++ Primer》入手，该书系统介绍了 C++ 的面向对象特性、标准库等内容，是公认的经典教材；对于想结合实践学习的人，推荐《C++ Primer Plus》，书中通过具体项目案例，引导读者掌握 C++ 在实际开发中的应用；视频资源可观看 B 站 “黑马程序员 C++ 教程”，涵盖从基础到进阶的知识点，适合边学边练。

以下是一些可供参考的学习资源：​

* **在线教程**：
  * ​C 语言官方文档（[https://www.iso](https://www.iso-9899.info/wiki/Main_Page)[-](https://www.iso-9899.info/wiki/Main_Page)[9899.info/](https://www.iso-9899.info/wiki/Main_Page)[wiki](https://www.iso-9899.info/wiki/Main_Page)[/Mai](https://www.iso-9899.info/wiki/Main_Page)[n\_Pa](https://www.iso-9899.info/wiki/Main_Page)[ge](https://www.iso-9899.info/wiki/Main_Page)）：涵盖 C 语言标准规范，是最权威的参考资料。
  * ​菜鸟教程 C 语言教程（[https://www.ru](https://www.runoob.com/cprogramming/c-tutorial.html)[noob](https://www.runoob.com/cprogramming/c-tutorial.html)[.com](https://www.runoob.com/cprogramming/c-tutorial.html)[/cp](https://www.runoob.com/cprogramming/c-tutorial.html)[rogr](https://www.runoob.com/cprogramming/c-tutorial.html)[ammi](https://www.runoob.com/cprogramming/c-tutorial.html)[ng/c](https://www.runoob.com/cprogramming/c-tutorial.html)[-tut](https://www.runoob.com/cprogramming/c-tutorial.html)[oria](https://www.runoob.com/cprogramming/c-tutorial.html)[l.htm](https://www.runoob.com/cprogramming/c-tutorial.html)[l](https://www.runoob.com/cprogramming/c-tutorial.html)）：以简洁的语言讲解 C 语言基础语法，搭配实例代码，适合零基础入门。​
  * [CPlusPlus.com](https://cplusplus.com/)（[https://www.cp](https://www.cplusplus.com/)[lusp](https://www.cplusplus.com/)[lus](https://www.cplusplus.com/)[.com/](https://www.cplusplus.com/)）：专注于 C++ 学习的在线平台，包含语法讲解、标准库说明及实例演示，能帮助快速掌握 C++ 核心知识。​
* **书籍**：
  * ​《C 程序设计语言（第 2 版）》：由 C 语言设计者编写，是 C 语言领域的经典教材，内容精炼且权威，适合深入理解 C 语言的设计思想。
  * ​《C++ Primer（第 5 版）》：系统讲解 C++ 的语法规则、面向对象特性及标准库，知识点全面且深入，是学习 C++ 的必备书籍。
  * ​《C 和指针》：聚焦 C 语言的指针特性，通过大量实例解析指针在内存操作、函数调用等场景的应用，帮助攻克 C 语言学习中的难点。
* **​视频课程**：
  * ​B 站 “浙江大学翁恺 C 语言” 课程（BV 号：BV1dr4y1n7vA）：由知名教授授课，注重基础概念的讲解与编程思维的培养，适合打牢 C 语言基础。
  * ​B 站 “黑马程序员 C++ 教程”（BV 号：BV1et411b73Z）：从 C++ 基础语法到 STL 标准库、面向对象编程，内容系统且贴近实战，适合零基础学习者循序渐进掌握 C++。​
  * 网易云课堂 “C++ 从入门到精通” 课程：结合案例讲解 C++ 在实际开发中的应用，包含项目实战环节，能帮助将理论知识转化为实践能力。
