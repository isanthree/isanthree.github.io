---
layout: post
title: 为windows配置GNU make环境
categories: 环境配置
description: 为windows配置GNU make环境
keywords: make, makefile
---

一、在windows环境下使用make命令出现下面的错误：

```sh
make : 无法将“make”项识别为 cmdlet、函数、脚本文件或可运行程序的名称。请检查名称的拼写，如果包括路径，请确保路径正确，然后再试一次。
所在位置 行:1 字符: 1
+ make
+ ~~~~
    + CategoryInfo          : ObjectNotFound: (make:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```



二、原因分析：

1. 未安装 make for windows；
2. 未正确配置环境变量;



三、解决办法：安装make for windows

下载路径：[Make for windows官网](http://gnuwin32.sourceforge.net/packages/make.htm) or [蓝奏云](https://wwa.lanzoui.com/i7XwOp8id3c)

> 官网下载，则选择Complete package, except sources版本，下载并安装



四、添加环境变量：（我的环境为 D:\Program Files (x86)\GnuWin32\bin）

右键我的电脑->属性->高级系统设置->高级->环境变量->系统变量->path

![](https://i.loli.net/2021/05/18/YcGlznhVuNDts12.png)



![](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/20210518140915.pn)

