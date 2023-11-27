# OnePlus 8T Horizon Kernel  

<div align="center">
<img src="https://blog.xzr.moe/usr/uploads/2023/06/239314569.png" alt="Horizon Kernel Logo"> 
</div>

**内核详细说明**：[LibXZR's Blog](https://blog.xzr.moe/archives/313/)  
**内核原作者：@libxzr**   
**内核原项目地址：[android_kernel_oneplus_sm8250](https://github.com/libxzr/android_kernel_oneplus_sm8250)**   

## 说明  
此仓库的源码**为fork后二次修改原作者@libxzr大佬**的产物。**目的为学习和自用**。  
此仓库内核和我自己写的简易编译脚本仅为OnePlus 8T设计。  
内核原始版本为v4.19.157。  

## 编译说明
+ 脚本说明
  > init_modules.sh：用于先同步基本的仓库子模块。
  > clean.sh：用于编译前和编译后清理仓库。
  > syncanykernel3.sh：同步AnyKernel3。
  > synckernelsu_all.sh：完全删除KernelSU代码并重新同步。
  > synckernelsu_stand.sh：更新KernelSU代码。
  > build_kernel_8t.sh：编译内核脚本。请按照情况自行修改交叉编译器路径。
+ 编译环境  
  > 系统：Ubuntu 20.04
  > Glibc版本：2.35
  > 交叉编译器：[Proton-Clang](https://github.com/kdrag0n/proton-clang)
+ 如何升级Glibc到2.35[谨慎操作！！]  
  > 先使用命令在软件源底部添加一个高版本的软件源。 ```sudo gedit /etc/apt/sources.list```  
  > 即此行：```deb http://mirrors.aliyun.com/ubuntu/ jammy main #添加该行到文件```
  > 更新软件源缓存：```sudo apt update```
  > 安装Glibc 2.35：```sudo apt install libc6```
  > 检查结果：```ldd --version```，显示出**ldd (Ubuntu GLIBC 2.35-0ubuntu3) 2.35**就是成功了。
  > 屏蔽高版本软件源：```sudo gedit /etc/apt/sources.list```
  > 然后注释掉它：```# deb http://mirrors.aliyun.com/ubuntu/ jammy main #注释该行到文件```
  > 更新软件源缓存：```sudo apt update```
  > 更新软件：```sudo apt update -y```
  


## 修改日志

2023.11.26：  
 > v1.0 Alpha
 > 1. 添加KernelSU支持。
 > 2. 增加submodules。
 > 3. 添加方便编译和调试的脚本。
  
2023.11.27：  
> v1.0 Beta
> 1. 上游内核到v4.19.160  
> 2. 切换编译器为[Proton-Clang](https://github.com/kdrag0n/proton-clang),适配Ubuntu 20.04。  