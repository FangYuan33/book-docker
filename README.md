### [《开发者必备的 Docker 实践指南》](https://s.juejin.cn/ds/64XJAAn/)

### 1. Docker的技术实现
Docker 的实现，主要归结于三大技术：命名空间 ( Namespaces ) 、控制组 ( Control Groups ) 和联合文件系统 ( Union File System )

1. **Namespace**
通过Namespace可以创造出独立的进程运行空间，在这个空间中运行的进程完全感知不到外界系统中的其他进程，实现程序进程的隔离

2. **Control Groups**
主要做的是硬件资源的隔离和分配，通过CGroups我们可以指定任意一个环境对任意资源的占用率，对于很多分布式使用场景来说很有用
![img.png](img.png)
3. **Union File System**
Docker提供了对联合文件系统（Union File System）的改进，AUFS。它能将文件的更新挂载到老的文件之上，
而不去修改那些不更新的内容，这就意味着即使虚拟的文件系统被反复修改，也能保证对真实文件系统的空间占用保持一个较低水平。