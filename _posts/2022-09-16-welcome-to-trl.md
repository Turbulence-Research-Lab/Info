---
title:  "入组须知"
# image : "/assets/images/post/post-1.jpg"
author: "Admin"
date: 2022-09-15 11:12:58 +0600
description : "须知要求"
tags: [须知]
---
欢迎加入清华大学湍流实验室，该部分内容将主要概述清华大学实验室信息资源使用指南。

## 云盘服务
- 同学请用邮箱自行在官网激活
[https://cloud.tsinghua.edu.cn/](https://cloud.tsinghua.edu.cn/)

- **桌面同步盘下载链接**
[https://www.seafile.com/download/](https://www.seafile.com/download/)

- **云盘第一条，新入组的同学切勿使用挂载盘**
![](/info/media/imag/post-2022-09-16-welcome/fig1.png)

- 加入群组请联系组内云盘管理员，群组内包含讨论报告、组会报告、学位论文和一些学习资料等。

## 组内Github群组
为了方便管理实验室经常使用的程序，特建立了Github群组[https://github.com/Turbulence-Research-Lab](https://github.com/Turbulence-Research-Lab)，包括了一些常用的组内程序、程序编写规范、前后处理程序、开源库的组内调用规范及API等相关内容。
- 加入Github群组需要提供Github账号或关联邮箱，并联系组内代码资源管理员进行添加，才能查看相关内容。



## 组内代码开发与书写规范
目前正在整合组内相关代码，计划在五年内(2023-2027)建成组内共享的代码库。方便组内同学与老师在此基础上开展更加深入、具有挑战和具有创造力的基础前沿科学研究。

研发进展：
1. 初步建立C++代码规范，具体参见[https://github.com/Turbulence-Research-Lab/code_specification](https://github.com/Turbulence-Research-Lab/code_specification)。
2. 初步完成基于HDF5开源库的流场存储格式，包括c++并行/串行、 fortran串行版本，方便跨平台、跨语言读写数据(支持matlab, python, julia语言)，具体参见[https://github.com/Turbulence-Research-Lab/trlpkg](https://github.com/Turbulence-Research-Lab/trlpkg).
3. 正在开发pencil型MPI转置和快速傅里叶变换的C++库

开发建议：
1. 祖传代码90%以上均为Fortran语言编写，尽管Fortran面向过程，语法简单，编译器优化程度高，程序员无需过多关注程序书写质量。但从长远来看，未来需要解决复杂问题，因此使用Fortran语言去完成复杂问题的难度较大，可维护性也比较堪忧。因此，如果你有重新开发代码的需求，我们不推荐也不建议首先使用Fortran语言。我们更建议你使用C++11以上的规范进行代码编写，并使用组内推荐的开源库和组内代码库，并尽可能遵循固定的代码规范和注释规范。当然，如果你没有重新开发代码的需求，我们更建议你不要轻易改动原来的Fortran程序，如果你所使用的代码已经有对应的C++版本，我们更鼓励你在C++版本上进行改进和完善。
2. 如果有志向投入到程序开发，请联系组内代码资源管理员。

未完待续。。。。。。