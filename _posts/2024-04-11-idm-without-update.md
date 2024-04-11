---
layout: post
title: 关闭 IDM (internet download manager) 自动弹出自动更新的提示
categories: [教程, IDM]
description: 关闭 IDM (internet download manager) 自动弹出自动更新的提示
keywords: 教程,IDM,关闭IDM自动更新提示
---

通过修改注册表来实现这一目标。

第一步：打开注册表编辑器。按下 `Win + R` 组合键，打开运行对话框。在运行框中输入 “regedit” 并点击 “确定” ，打开注册表编辑器。

第二步：定位到 LstCheck 项目。在注册表编辑器中，导航到路径：`计算机\HKEY_CURRENT_USER\SOFTWARE\DownloadManager`，找到 “LstCheck” 项（这是控制 IDM 自动更新的注册表项），双击该项并将数值数据改为 0 即可。

<center><img src="https://pic.imgdb.cn/item/6617498368eb935713cc3bf4.png"></center>

<center><img src="https://pic.imgdb.cn/item/66174a5368eb935713cda0fb.png"></center>

第三步：重启电脑。已经成功地修改了注册表项以禁用 IDM 的自动更新。为了确保更改生效，需要重新启动你的计算机。

![](https://pic.imgdb.cn/item/661246bf68eb935713c7f81c.gif)
