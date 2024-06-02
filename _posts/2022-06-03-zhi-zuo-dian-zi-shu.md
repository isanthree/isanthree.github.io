---
layout: post
title: calibre 制作电子书多级目录教程
categories: [教程]
description: calibre 制作电子书多级目录教程
keywords: calibre,电子书制作,多级目录
---

calibre 制作电子书多级目录教程如下：

calibre 能够识别 markdown 的目录标志 `#`，并制作相应级别的目录。我们只需要做好标记即可。

一、准备一款支持正则表达式替换的编辑器，代码编辑器可以很好的胜任这项工作，比如 NotePad++、Sublime Text 等。

二、以 NotePad++ 为例，首先按下 `Ctrl+H` 打开文本替换工具，界面中启用「正则表达式」。然后如下图进行以下操作：

<div align="center"><img src="https://pic.imgdb.cn/item/665c1ddfd9c307b7e933161e.png"/></div>

- 标记一级标题：查找目标： `^第(.\*)章`，替换为： `# 第\1 章`
- 标记二级标题：查找目标： `^第(.\*)章`，替换为： `## 第\1 章`

> PS：建议 txt 内容全部顶格，不要留空格。

三、用这些方法实现替换后，我们就为 txt 添加了目录 tag，接下来要做的事情就简单很多，把处理完毕的 txt 添加到 calibre 中，然后「右键图书 - 转换图书 - 逐个转换 - 目录」。选择右上角的输出格式，通常选择导出为 epub 和 mobi 格式。

<div align="center"><img src="https://pic.imgdb.cn/item/665c1bb0d9c307b7e930bbeb.png"/></div>
