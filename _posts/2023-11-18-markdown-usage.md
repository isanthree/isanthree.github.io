---
layout: post
title: Markdown 常用语句
categories: [Markdown]
description: Markdown 常用语句
keywords: Markdown
---

# 贴图

对图片加以控制（居中，宽：65 长：75）：

```html
<div align="center">
  <img
    width="65"
    height="75"
    src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/title.ico"
  />
</div>
```

效果：

<div align="center"><img width="72" height="72" 
src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/title.ico"/>
</div>

或

```html
<center>
  <img
    src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/title.ico"
    style="width:7%"
  />
</center>
```

效果：

<center><img src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/title.ico" style="width:7%"/></center>

# 首行缩进

直接在 Markdown 里用空格和 Tab 键缩进在渲染后会被忽略掉，需要借助 HTML 转义字符在行首添加空格来实现，`&ensp;` 代表半角空格，`&emsp;` 代表全角空格。

```
&emsp;&emsp;hello world!
```

效果：

&emsp;&emsp;hello world!

# 字体调整大小、红色居中

```html
<div align="center" style="font-size:20px;color:red;">
  字体大小调整为 20px、红色居中！
</div>
```

效果：

<div align="center" style="font-size:20px;color:red;">字体大小调整为 20px、红色居中！</div>
