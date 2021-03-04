# ContainerTechnology

## 什么是容器技术？
Reference: https://zhuanlan.zhihu.com/p/39155341

为了解决应用程序在不同操作系统之间移植，降低对操作系统和环境的依赖。只关注应用程序。

container主要由Namespace和Cgroup两大机制来保证实现。

+ Namespace: 隔离，使应用程序和操作系统隔离。
+ Cgroup: 负责资源管理控制，比如进程组使用CPU/MEM的限制，进程组的优先级控制，进程组的挂起和恢复等。

## 容器技术的特点
+ 轻量级： 只需打包必要的Bin/Lib.
+ 秒级部署: 根据镜像的不同，容器的部署大概在毫秒与秒之间。
+ 易于移植: 一次构建，随处部署。
+ 弹性伸缩：Kubernetes, Swan, Mesos开源，方便，好使的容器管理平台，有着非常强大的弹性管理。

## 容器运行时标准
1. Creating: 使用create命令创建容器，创建中。
2. Created: 创建成功还没有运行。
3. Running：容器的运行状态，里面的进程处于Up状态，正在执行用户设定的任务。
4. Stopped：容器运行或者运行出错，或者stop命令之后。容器处于暂停状态。容器信息保存在平台中，并没有完全被删除。
