---
layout: post
title: 【vscode】intellisense 模式 msvc-x64 与编译器路径不兼容
categories: [环境配置,vscode]
description: 记录配置vscode编译c++时遇到的一个问题
keywords: cpp, vscode
---





看一下问题：intellisense 模式 msvc-x64 与编译器路径不兼容。

![image-20210516000345240](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516000401.png)

接下来看一下解决办法：

![](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516000500.png)

我们只需要将此处的 msvc 改为 gcc 即可：

![](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516000641.png)



