# Docker

#### 定义

📦 **容器技术的一种具体实现**

> **容器技术**：通过**运行环境（运行时依赖）**隔离应用程序
>
> **虚拟机技术**：通过**操作系统**隔离应用程序
>
> 💎 **容器技术优势**：
>
> - **屏蔽操作系统环境差异，表现一致**
>
>   - 货物：应用程序
>
>   - 集装箱：运行时依赖
>
>   - 港口：操作系统
>
>     **程序的表现只和集装箱（容器）有关系，和集装箱放在哪个港口（操作系统）没有关系**。
>
> - **轻量级，占用资源少**
>
>   虚拟机本身操作系统占用内存大（G），容器技术只需要数 M 空间，从而实现同规格硬件上容器的大量部署。
>
> - **启动速度快**
>
>   虚拟机本身操作系统启动缓慢（Min），容器几乎瞬间启动，容器技术为**打包服务栈**提供了一种更加高效的方式。
>
> - **快速部署**
>
>   一方面得益于启动速度快，另一方面得益于表现一致。

#### 工作机制

> **CS 架构（client-server 模式）**：
>
> **docker client（client）** 负责处理用户输入的指令（如 docker build/docker run）
>
> **docker demon（server）** 接收 client 端指令，执行所对应的具体操作

1. **概念**

   - **dockerfile**：指定所需程序与依赖配置（image 源码）
   - **image**：可执行程序
   - **container**：运行起来的进程

2. **命令**

   - **docker build**：编译 dockerfile

     docker client 接受请求转发给 docker demon，docker demon 根据 dockerfile 创建 image。

     ![docker build](https://pic3.zhimg.com/80/v2-f16577a98471b4c4b5b1af1036882caa_720w.jpg)

   - **docker run**：运行程序

     docker client 接受请求转发给 docker demon，docker demon 找到具体 image，加载至内存开始执行，所运行起来的进程即为 container。

     ![docker run](https://pic4.zhimg.com/80/v2-672b29e2d53d2ab044269b026c6bc473_720w.jpg)

   - **docker pull**：下载 image

     docker client 接受请求转发给 docker demon，docker demon 向 docker registry 发送 image 下载请求，下载后存放在本地。

     <img src="https://pic3.zhimg.com/80/v2-dac570abcf7e1776cc266a60c4b19e5e_720w.jpg" alt="docker pull" style="zoom:120%;" />





