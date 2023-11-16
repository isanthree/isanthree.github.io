---
layout: post
title: 申请 SSL 证书并部署，开启 https 访问网站
categories: [建站]
description: 申请 SSL 证书并部署，开启 https 访问网站
keywords: SSL,https,建站
---

注册域名的云服务商会提供免费的 SSL 证书，去申请即可。这里以阿里云为例（不是打广告哈，因为就是只申请了这个，想着记录一下搭建博客的过程，就把全流程全记下来了，分享给大家，希望对大家有帮助）

> 网址不好贴，找不到 SSL 证书的话，到阿里云官网（[www.aliyun.com](www.aliyun.com)）直接搜就行了

我之前已经购买了免费的证书，所以下面显示有证书：

![image-20231114110347063](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114110347063.png)

如果还没买过的话，点击立即购买即可，购买过的会显示已经领取了免费证书，不能重复领取（如下图）：

![image-20231114110658881](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114110658881.png)

点击【创建证书】后，会自动创建一个 “待申请” 状态的 DigiCert 免费版 SSL，点击 “证书申请”，然后填写证书申请表单，按照实际情况填写即可，需要实名认证。因为已经申请过了，无法截原图，这里借一下网图（版面可能已经改版了，不影响，能进行下去就行）

证书申请表单填写

- 证书绑定域名：输入你的域名
- 域名验证方式：如果你的域名在当前的阿里云账号下，那么可以选择自动 DNS 验证，如果域名不在当前账号下，选择手工 DNS 验证，当然也可以选择文件验证，根据实际情况选择
- 联系人：如果之前没有填写过，则需要新建联系人，输入联系人姓名、邮箱地址、手机号和身份证号等信息。申请 OV、EV 证书需要填写身份信息，免费证书是 DV 证书，可以不填身份证号码
- 可以使用阿里云测速工具 [https://aliyunping.com](https://aliyunping.com) 测试一下本地到阿里云服务器各个地域节点的 Ping 值网络延迟
- 所在地：根据实际情况填写
- 密钥算法：RSA
- CSR 生成方式：系统生成，建议您使用系统创建的 CSR，避免因内容不正确而导致的审核失败

![image-20231114112703880](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114112703880.png)

填写完后，点【提交审核】，完成域名的 DNS 验证。

域名 DNS 验证，等待审核，一般几分钟就能通过并下发证书，证书下发后直接下载即可。

下载 SSL 证书。根据自己的服务器类型下载证书。

![image-20231114112953287](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114112953287.png)

如果不知道自己的服务器类型，打开 cmd，输入命令：`curl -i XXX.cn`（换自己的 IP 再 curl）

![image-20231114113207883](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114113207883.png)

得到了服务器类型，下载对应证书即可，以 nginx 类型服务器为例，证书包含两个文件：.pem 文件和 .key 文件，前者是证书文件，后者是私钥文件。

在服务器部署证书，这里直接在宝塔 Linux 面板上操作，可以大大简化操作，如下图，把下载的证书文件内容分别填写到正确的位置，保存并启用证书。

![image-20231114113834114](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114113834114.png)

强制启用 https：

![image-20231114114133279](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114114133279.png)

再次访问网站，网址前的 “小锁” 就出现了，整个的 SSL 部署至此结束！！！！

![image-20231114114256566](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/image-20231114114256566.png)
