---
layout: post
title: WordPress 禁用上传媒体图片自动生成缩略图及多尺寸图片教程
categories: [books]
description: some word here
keywords: WordPress,图床,教程
---

一、在 `设置`-`媒体`-`媒体设置` 中几个尺寸大小的设置不勾选或设置为 0。

<div align="center"><img src="http://cdnjson.com/images/2024/10/11/image0c782754dea73a38.md.png" alt=""></div>

二、找到主题文件 function.php 文件，打开后，在 `<?php` 后面添加如下代码：

> function.php 文件路径一般为：`WordPress网站根目录/wp-content/themes/主题文件夹/functions.php`

```php
// 禁用自动生成的图片尺寸
function shapeSpace_disable_image_sizes($sizes) {

    unset($sizes['thumbnail']);    // disable thumbnail size
    unset($sizes['medium']);       // disable medium size
    unset($sizes['large']);        // disable large size
    unset($sizes['medium_large']); // disable medium-large size
    unset($sizes['1536x1536']);    // disable 2x medium-large size
    unset($sizes['2048x2048']);    // disable 2x large size
    unset($sizes['750x1000']);

    return $sizes;

}
add_action('intermediate_image_sizes_advanced', 'shapeSpace_disable_image_sizes');

// 禁用缩放尺寸
add_filter('big_image_size_threshold', '__return_false');

// 禁用其他图片尺寸
function shapeSpace_disable_other_image_sizes() {

    remove_image_size('post-thumbnail'); // disable images added via set_post_thumbnail_size()
    remove_image_size('another-size');   // disable any other added image sizes

}
add_action('init', 'shapeSpace_disable_other_image_sizes');
```

三、设置完后去后台媒体中上传一个图片文件试试，是已经不再自动生成不同尺寸的媒体图片。

本文完！！！

<div align="center"><img src="https://pic.imgdb.cn/item/6707df6bd29ded1a8ce37031.gif" alt="感谢！！！" width="420px" height="auto"/></div>
