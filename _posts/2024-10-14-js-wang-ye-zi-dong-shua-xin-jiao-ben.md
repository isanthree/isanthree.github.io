---
layout: post
title: JS 网页自动刷新脚本
categories: [books]
description: some word here
keywords: JS,网页自动刷新脚本
---

一、使用流程：

1.在浏览器地址栏输入需要的网址；

2.按 F12 打开开发者工具，找到控制台（console）；

3.将下面的脚本代码复制到控制台内，敲回车键即可执行。

4.在弹出的时间设置框内输入刷新时间间隔（该间隔以秒为单位），点击确定，页面将自动根据时间间隔刷新。

二、如何结束自动刷新：

需要停止页面刷新时可以直接关闭该页面（仅关闭控制台不能停止页面刷新）。

三、源代码及解析

```js
// prompt函数用来提醒用户输入
var timeout = prompt("设置刷新时间间隔[S]");
// 获取当前的URL
var current = location.href;

if (timeout > 0) {
  // 时间间隔大于0，timeout秒之后执行reload函数
  setTimeout("reload()", 1000 * timeout);
} else {
  // 时间间隔不大于0，仅刷新一次
  location.replace(current);
}

function reload() {
  // timeout秒后执行reload函数，实现无限循环刷新
  setTimeout("reload()", 1000 * timeout);
  // 下面两行代码的格式化后的内容为：
  // <frameset cols='*'>
  //     <frame src='当前地址栏的URL' />
  // </frameset>
  var fr4me = "<frameset cols='*'>\n<frame src='" + current + "' />";
  fr4me += "</frameset>";

  with (document) {
    // 引用document对象，调用write方法写入框架，打开新窗口
    write(fr4me);
    // 关闭上面的窗口
    void close();
  }
}
```
