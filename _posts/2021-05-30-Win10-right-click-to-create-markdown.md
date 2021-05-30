---
layout: post
title: win10 配置右键新建 markdown 文件
categories: [环境配置]
description: win10 配置右键新建 markdown 文件
keywords: windows, typora, markdown
---

本文介绍了如何在Windows操作系统中添加右键创建.md文件的方法。

1. 打开注册表

   CMD+R，打开运行对话框；输入regedit，打开注册表编辑器

2. 修改注册表

   在`计算机>HKEY_CLASSES_ROOT`右键查找，输入`Typora`，勾选项，取消勾选值和数据

   ![](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/20210530094612.png)

   确认运行的程序名字，我的电脑如图所示，运行文件是`Typora.exe`

<img src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/20210530094821.png" style="zoom: 80%;" />

3. 创建注册表

   在磁盘任意位置新建一个文件，后缀为.reg；

   打开编辑刚刚创建好的注册表文件，写入以下内容：

   ```shell
   Windows Registry Editor Version 5.00
   [HKEY_CLASSES_ROOT\.md]
   @="Typora.exe"
   [HKEY_CLASSES_ROOT\.md\ShellNew]
   "NullFile"=""
   [HKEY_CLASSES_ROOT\Typora.exe]
   @="Markdown"
   ```

   > @="Typora.exe" 代表的是指定 .md 文件的运行程序
   >
   > @="Markdown" 代表的是右键时默认的文件名字，这样写新建为`新建Markdown.md`文件，而且右键菜单中显示`MarkDown`

   编辑好之后,另存为，设置如图所示：

   ![image-20210530095406930](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/20210530095526.png)

   文件名可以随便设置，但是后缀必须是`.reg`文件,保存类型一定要是`文本文档(*.txt)`,编码选择`ANSI`,非常重要！

   保存文件后,双击运行，修改注册表即可，现在右键即可达到预期效果，如果不行，请重启一下。

