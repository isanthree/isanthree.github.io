---
layout: page
title: About
description: 打码改变世界
keywords: isanthree, about, 关于
comments: true
menu: 关于
permalink: /about/
---

我开不了双线程，同一时间，只能专注一件事，一步又一步。

仰慕「优雅编码的艺术」。

坚信熟能生巧，努力改变人生。

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'isanthree.github.io' %}
<li>
博客：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ assets_base_url }}/assets/images/qrcode.jpg" alt="程序员" />
</li>
{% endif %}
</ul>




## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}

