---
layout: post
title: MingGW64 各版本区别及安装说明
categories: cpp
description: Windows 系统下安装配置 MinGW-w64 开发环境
keywords: cpp, MingGW
---



# MinGW、MinGW-w64 简介

MinGW（全称为 Minimalist GNU for Windows），它实际上是将经典的开源 C 语言编译器 GCC 移植到了 Windows 平台下，并且包含了 Win32 API ，因此可以将源代码编译为可在 Windows 中运行的可执行程序。而且还可以使用一些 Windows 平台不具备的，但是 Linux 平台具备的开发工具和 API 函数。用一句话来概括就是：MinGW 就是 GCC 的 Windows 版本 ；

MinGW-w64 原本是 MinGW 项目的分支，后来成为独立发展得项目，由于仅有 MinGW-w64 被 GCC 官方所支持, 而 MinGW 早已停止更新, 因此推荐使用 MinGW-w64；

MinGW-w64 与 MinGW 的区别在于 MinGW 只能编译生成 32 位可执行程序，而 MinGW-w64 则可以编译生成 64 位或 32 位可执行程序。

# 下载地址

官网：<https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/>

![image-20210804110316854](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804110316854.png)

本人下载的是：![image-20210804105950570](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804105950570.png)

**PS：不建议在线安装，即使用 exe 文件安装；建议下载离线的压缩包，解压安装，添加环境变量即可。**

# MinGW 各版本参数说明

MinGW 可以适应不同系统开发环境，因此有几大参数需要进行选择： Version、Architecture、Threads、Exception

- Version：指的是你选择的 GCC 编译器的版本，我选择的是当前最新版本 8.1.0，一般建议选择最新的版本；

- Architecture：指的是你的电脑的系统类型，i686 表示的是 32 位的系统类型，x86_64 表示的是 64 位的系统类型；

- Threads：指的是线程模型，posix 或 win32

  - POSIX（Portable Operating System Interface，可移植操作系统接口），是 UNIX 系统的一个 API 设计标准，很多类 UNIX 系统也在支持兼容这个标准，如 Linux 操作系统。如果在 Windows 下开发 Linux 应用程序，则选择 posix；
  - Win32，是 Windows 系统下一个 API 设计标准，如果开发 Windows 平台下的应用程序，就需要选择 Win32；

- Exception：指的是异常处理模型。i686 系统架构有两种选择：dwarf 和 sjlj；x86_64 系统架构也有两种选择：seh 和 sjlj。

  > 这里说一下 sjlj，seh，dwarf 三者的区别：
  >
  > 在C++中有 try..throw..catch，当它执行这种结构时，它需要保存现场还原现场，而 sjlj，seh，dwarf 正是实现这类过程的三种方式。
  >
  > - sjlj 全称是 SetJump / LongJump，前者设还原点，后者跳到还原点。可用于 32 位或者 64 位系统。
  >
  > - seh（Structured Exception Handling，结构化异常处理）是 Borland 公司的，微软买了其专利使用权，它利用了 FS 段寄存器，将还原点压入栈，收到异常时再弹出。相较而言，sjlj 是 C 标准库就有的东西，seh 在 2014 年前是有专利的，从性能上说 seh 比 sjlj 快。只用于64位系统。
  >
  > - dwarf 只支持32位系统 – 没有永久的运行时间开销 – 需要整个调用堆栈被启用，这意味着exception不能被抛出，例如Windows系统DLL。
  >
  > 综上所述：
  >
  > 【x86_64 64位】
  >
  > 1、seh 是新发明的，而 sjlj 则是古老的。只用于64位系统。
  >
  > 2、seh 性能比较好，但不支持 32位。 sjlj 稳定性好，支持 32位和64位。
  >
  > 因此，x86_64 系统架构的推荐使用 seh 的异常处理模型。
  >
  > 【i686 32位】
  >
  > 1、dwarf 只支持 32 位，而 sjlj 支持 32 位或64 位，但是 dwarf 的性能要优于 sjlj。
  >
  > 因此，i686 系统架构的推荐使用 dwarf 的异常处理模型。
  >
  > 【参考】<https://wiki.qt.io/MinGW-64-bit>

# 解压安装

1、下载：[x86_64-8.1.0-release-posix-seh-rt_v6-rev0.7z](https://udomain.dl.sourceforge.net/project/mingw-w64/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/8.1.0/threads-posix/seh/x86_64-8.1.0-release-posix-seh-rt_v6-rev0.7z)

2、解压到 D 盘的程序文件目录：

![image-20210804112031816](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804112031816.png)

3、添加环境变量

![image-20210804112346518](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804112346518.png)

# 测试

在 cmd 中进行命令测试：`gcc -v` 和 `g++ -v`

出现如下效果图说明安装成功：

![image-20210804112751790](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804112751790.png)

![image-20210804112849565](https://codechina.csdn.net/qq_29856169/gallery/-/raw/master/pic/image-20210804112849565.png)

