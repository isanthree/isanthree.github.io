---
layout: post
title: office 或 wps 三件套使用技巧
categories: [books]
description: some word here
keywords: office,wps,tips,使用技巧
---

一、excel 表格

1.存在 A 和 B 两列数据，筛选出 B 列的数据是否存在于 A 列

方法一：输入公式 `=IF(COUNTIF($A:$A,B1)>0,"相同","不同")`

方法二：以 WPS 为例，选中 A、B 两列数据，依次点击「数据-重复项-设置高亮重复项」，弹出「高亮显示重复值」方框后，点击「确定」

> office excel 是「开始-条件格式-突出显示单元格规则-重复值」

<div align="center"><img src="https://qweree.cn/wp-content/uploads/2026/11/execel-chongfu01.png" alt="此处描述图片信息"></div>

2.存在 A 和 B 两列数据，筛选出同一行的数据是否相同

输入公式：`=IF(A1=B1,"相同","不同")`

二、word 文档

待续，持续更新...
