---
layout: post
title: git 部署到码云和 github，同时提交到两个仓库
categories: [环境配置]
description: git 部署到码云和 github，同时提交到两个仓库
keywords: git, gitee, github, ssh
---

# 删除旧的全局设置

1. 查看旧的全局设置

`git config --global --list `

![80e49ee1af94460e8158acac68b31af9-169959699852210.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/80e49ee1af94460e8158acac68b31af9-169959699852210.png)

2. 如果有，执行：

```bash
git config --global --unset user.name "xxx"
git config --global --unset user.email "xxx@163.com"
```

# 开始配置

1. 在目录`C:\Users\lenovo\.ssh`下右键，点击 `git bash here`
2. 生成 Key

```bash
ssh-keygen -t rsa -C "XXX@163.com" -f "github_id_rsa"
ssh-keygen -t rsa -C "XXX@163.com" -f "gitee_id_rsa"
```

3. 打开目录下的文件，将 Key 分别复制到 gitee 和 github 上

![0d6179787faa4475b3a9b2c992143a68.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/0d6179787faa4475b3a9b2c992143a68.png)

4. 配置 github ssh

配置 ssh 地址：<https://github.com/settings/keys>。将 .pub 文件内容复制到 Key 框内，Title 随便填。

New SSH key：

![12276b383c19428bbbe0210491171593.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/12276b383c19428bbbe0210491171593.png)

填写 Title 和 Key：

![6d0a1a7e55394b508b12b794d0e6c224.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/6d0a1a7e55394b508b12b794d0e6c224.png)

5. 在目录`C:\Users\lenovo\.ssh`下创建 config 文件解决 ssh 冲突，填写如下内容：

```bash
# gitee
Host gitee.com
HostName gitee.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/gitee_id_rsa

# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/github_id_rsa
```

# 测试连接

```bash
ssh -T git@github.com
ssh -T git@gitee.com
```

如图，说明成功：

![0d3d02271419490e880e8630d6c9449e.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/0d3d02271419490e880e8630d6c9449e.png)

如果出现下图情况，输入 `yes`：

![9e6f58466d6f4dfa957809498477dfb9.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/9e6f58466d6f4dfa957809498477dfb9.png)

到了这里配置就成功了

# 分别提交到两个仓库

1. 执行操作后，发现有问题

![f41fd0aa80e744df8ca76d1ee4ab724e.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/f41fd0aa80e744df8ca76d1ee4ab724e.png)

2. 这时候执行以下代码（注意不要用全局的）：

```bash
git config user.name "LongSir"
git config user.email "sylzy66sina@163.com"
```

然后再次提交：`git commit -m "first-commit"`

3. 连接远端仓库并提交

```bash
git remote add origin git@gitee.com:jonnylong/computer_learning_notes.git
git push -u origin master
```

![cb36c70eb5a847d192866c33c75a5119.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/cb36c70eb5a847d192866c33c75a5119.png)

4. 在`.git`文件夹中加入 github 的 SSH 地址

![da6bdb754974410dacd8813728a3c785.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/da6bdb754974410dacd8813728a3c785.png)

![b9c8dead44e7437e82cbd01c469b7c92.png](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/b9c8dead44e7437e82cbd01c469b7c92.png)

5. 再次`git push`时候就可以推送到两个仓库了