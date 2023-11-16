---
layout: post
title: centos 如何开启 ssh 远程登录
categories: [ssh, 建站]
description: centos 如何开启 ssh 远程登录，这里给你答案！
keywords: centos, ssh, 远程登录
---

1.确保 CentOS 系统已安装了 SSH 服务器软件。可以使用命令检查是否已安装：

```bash
sudo yum list installed | grep openssh-server
```

2.如果没安装，输入命令安装：

```bash
sudo yum install openssh-server
```

3.安装完成后，输入命令启动 SSH 服务：

```bash
sudo systemctl start sshd
```

4.如果希望在系统启动时自动启动 SSH 服务，可以输入命令设置：

```bash
sudo systemctl enable sshd
```

5.确定防火墙允许 SSH 连接。默认情况下，CentOS 启用了防火墙，需要添加 SSH 服务的规则。输入命令打开 SSH 服务的防火墙规则：

```bash
sudo firewall-cmd --permanent --add-service=ssh
sudo firewall-cmd --reload
```

6.完成上述步骤后，CentOS 就可以通过 SSH 远程登录了。可以使用任何 SSH 客户端应用程序，如 XShell、PuTTY 或 Terminal 来连接到 CentOS 服务器。
