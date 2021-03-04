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

## 容器运行时标准 （runtime spec)
1. Creating: 使用create命令创建容器，创建中。
2. Created: 创建成功还没有运行。
3. Running：容器的运行状态，里面的进程处于Up状态，正在执行用户设定的任务。
4. Stopped：容器运行或者运行出错，或者stop命令之后。容器处于暂停状态。容器信息保存在平台中，并没有完全被删除。

## 容器镜像标准(image spec)
+ 文件系统: 以layer保存的文件系统，每个layer保存了和上层之间变化的部分，layer应该保存那些文件，怎么表示增加，修改和删除文件等。
+ config文件: 保存文件系统的层级信息，以及容器的运行时需要的信息（比如环境变量，工作目录，命令参数，mount列表等)。
+ manifest文件：镜像的 config 文件索引，有哪些 layer，额外的 annotation 信息，manifest 文件中保存了很多和当前平台有关的信息。
+ index 文件：可选的文件，指向不同平台的 manifest 文件，这个文件能保证一个镜像可以跨平台使用，每个平台拥有不同的 manifest 文件，使用 index 作为索引。
