# 进程、线程和应用程序域

## 1. 进程
进程(Process)是操作系统中的一个基本概念，它包含着一个运行程序所需要的资源。进程之间是相对独立的，一个进程无法直接访问另 一个进程的数据（除非利用分布式计算方式），一个进程运行的失败也不会影响其他进程的运行，操作系统就是利用进程把工作划分为多个独立的区域的。进程可以理解为一个程序的基本边界。

操作系统分配资源的最小单位是进程，进程之间是相互隔离的，即每个进程有属于自己的数据段、程序段、进程控制块。

## 2. 线程
线程(Thread)是任务调度的最小单位。一个线程是一个进程里面的代码执行流，每个线程都有自己的专有寄存器(栈指针、程序计数器等)，但代码区是共享的。

## 3. 应用程序域
应用程序域(App Domain)提供安全而通用的处理单元，公共语言运行库可使用它来提供应用程序之间的隔离。我们可以单个进程中运行几个应用程序域，而不会造成进程间调用或进程间切换等方面的额外开销。在一个进程内运行多个应用程序的能力显著增强了服务器的可伸缩性。

应用程序域允许我们在一个应用程序中出现的错误不会影响其他应用程序。能够在不停止整个进程的情况下停止单个应用程序。应用程序域形成了托管代码的隔离、卸载和安全边界。

![进程线程和应用程序域的关系](../img/multithreading/ptd.jpg)