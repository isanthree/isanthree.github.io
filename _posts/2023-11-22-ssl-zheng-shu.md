---
layout: post
title: 阿里云 SSL 免费证书申请入口链接及流程
categories: [教程]
description: 阿里云 SSL 免费证书申请入口链接及流程
keywords: ssl证书
---

一、前言
本文主要介绍阿里云 SSL 免费证书申请入口链接及流程

二、操作流程

2.1 阿里云 SSL 免费证书申请

1、登录到[阿里云数字证书管理服务控制台](https://yundun.console.aliyun.com/?userCode=r3yteowb&p=cas#/certExtend/free/cn-hangzhou)

2、点击左侧栏的【SSL 证书】–【免费证书】–【立即购买】，如下图：

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-1700572347753.png](https://qweree.cn/wp-content/uploads/2023/11/image-1700572347753.png)

3、产品选择【免费证书】，购买数量选择【20】，其他服务选择【不需要】，勾选同意协议，一共是 0 元，如下图：

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-1753d0d87d8cb9c6502bc430063d2c40_r.jpg](https://pic1.zhimg.com/80/v2-1753d0d87d8cb9c6502bc430063d2c40_720w.webp)

4、点击【支付】即可

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-90d318d294881b2fa25842d337b33f52_720w.webp](https://pic3.zhimg.com/v2-90d318d294881b2fa25842d337b33f52_r.jpg)

2.2 免费 SSL 证书绑定域名下载教程

1、进入[阿里云数字证书管理服务控制台](https://yundun.console.aliyun.com/?userCode=r3yteowb&p=cas#/overview/cn-hangzhou)

2、点击左侧栏的【SSL 证书】–【免费证书】–【创建证书】，如下图：

![](https://pic3.zhimg.com/v2-778d14c022cbacb1087b4108c5ae26a2_r.jpg)

点击【创建证书】后，会自动创建一个“待申请”状态的 DigiCert 免费版 SSL

3、找到 DigiCert 免费版 SSL 右侧的【证书申请】，如下图：

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-75dd192d91e14563ef4bb78a783bf3c5_720w.webp](https://pic2.zhimg.com/80/v2-75dd192d91e14563ef4bb78a783bf3c5_720w.webp)

4、证书申请表单填写

- 证书绑定域名：输入你的域名

- 域名验证方式：如果你的域名在当前的阿里云账号下，那么可以选择自动 DNS 验证，如果域名不在当前账号下，选择手工 DNS 验证，当然也可以选择文件验证，根据实际情况选择

- 联系人：如果之前没有填写过，则需要新建联系人，输入联系人姓名、邮箱地址、手机号和身份证号等信息。申请 OV、EV 证书需要填写身份信息，免费证书是 DV 证书，可以不填身份证号码

- 可以使用阿里云测速工具 <https://aliyunping.com> 测试一下本地到阿里云服务器各个地域节点的 Ping 值网络延迟

- 所在地：根据实际情况填写

- 密钥算法：RSA

- CSR 生成方式：系统生成，建议您使用系统创建的 CSR，避免因内容不正确而导致的审核失败

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-c1246b8827ac2e95ad89d0812797232e_r.jpg](https://pic3.zhimg.com/v2-c1246b8827ac2e95ad89d0812797232e_r.jpg)

填写完后，点【提交审核】，完成域名的 DNS 验证。

说明：如果域名是阿里云申请的，会省很多事情

5、域名 DNS 验证
![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-f60c229a92247d598ee5fa3dfbf2a7be_720w.webp](https://pic3.zhimg.com/80/v2-f60c229a92247d598ee5fa3dfbf2a7be_720w.webp)

一般等待几分钟即可审核通过下发证书，证书下发后直接下载即可。

6、下载 SSL 证书

点击【下载】

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-f48c33759fe957a2c8a0137b4e1d911b_720w.webp](https://pic4.zhimg.com/80/v2-f48c33759fe957a2c8a0137b4e1d911b_720w.webp)

阿里云 SSL 证书支持多种服务器类型，如：Tomcat、Apache、Nginx、IIS、JKS、其他及根证书下载，根据服务器类型，选择对应的 SSL 证书下载即可。

![https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/v2-f99885dfdb404c57847fbd9c23277a4e_720w.webp](https://pic3.zhimg.com/80/v2-f99885dfdb404c57847fbd9c23277a4e_720w.webp)

<!--转自：https://zhuanlan.zhihu.com/p/659159604-->
