---
layout: post
title: 小书匠编辑器
categories: [小书匠, 使用手册]
description: 小书匠编辑器使用手册
keywords: keyword1, keyword2
---


[toc]


# 概要

小书匠编辑器不仅仅是一款专为 markdown 写作而设计的编辑器，还内置了[数据中心](http://soft.xiaoshujiang.com/docs/tutorial/database/)，实现了[过滤器](http://soft.xiaoshujiang.com/docs/tutorial/filter/),[全文搜索](http://soft.xiaoshujiang.com/docs/tutorial/search_grammar/)，[链接关系图](http://soft.xiaoshujiang.com/docs/tutorial/link_network_map/),反向链接等方便快速定位历史文章的功能，完全可以做为一款个人 **真** 离线的笔记系统，知识管理工具。

# 主要功能
1. **专为markdown写作设计的文档编辑器**，让用户心无旁骛的进行创作。
1. **多种编辑模式**。单栏编辑，双栏编辑，三栏编辑，全屏写作，全屏阅读...想怎么切换，就怎么切换，就是这样随心所欲。
1. **多种编辑器实现**。codemirror编辑器（提供vim,emacs按键，行专注等），ace编辑器（提供vim，emacs按键绑定，显示行号），CJK竖排编辑器, 自定义外部编辑器, 总有一款编辑器按键符合你的要求
3. **多种主题选择**。包括编辑器主题，预览区代码高亮主题，及预览区用户自定义css。
4. **丰富的语法支持**。不仅提供了常用的commanmarkdown语法，还提供了许多有用的扩展语法，比如==Latex公式==，==表格==, ==目录==， ==脚注==, ==视频==, ==音频==, ==附件==, ==checklist==, ==流程图==等。更多语法可查看<小书匠语法使用手册>
5. **drawio 绘图**, 想要在 markdown 文章上表达更复杂的图形, drawio 绝对是你的不二选择,配合小书匠, 简直就是 **1+1>2** 的最有力证明
6. **表格组件**, 单元格合并,表格内嵌套表格,富文本式的表格编辑,弥补了 markdown 对表格支持的不足,再也不会为复杂的表格呈现而烦恼.
4. **代码块文字格式语法**。语法可查看<小书匠语法使用手册>
5. **第三方同步**。==浏览器存储==, ==本地文件系统存储==, ==Dropbox==, ==Evernote==, ==印象笔记==,==gitee==, ==为知笔记==, ==Github==, ==Webdav==, ==坚果云==, ==Seafile==, ==Gitlab==, ==ownCloud==, ==NextCloud==, ==有道笔记==等多种存储方案，保证了用户数据的安全，也让用户在存储方案上有了更多的选择。
6. **支持evernote，印象笔记**。提供双向操作，可以将文章保存到evernote/印象笔记上，也可以从evernote/印象笔记上导入数据。同时提供标签，附件，图片，待办等相关处理。
7. **模板管理**, 通过模板,创建自己经常使用的文章格式
6. **强大的文件管理功能**。文件信息，标签，附件，音频，视频，图片管理。
7. **过滤器**. 标签过滤,分类树过滤,日历时间过滤,快速归类自己的文件
8. **置顶**. 将经常编辑的文章进行置顶操作,再不用来回查找那些高频修改的文章
9. **数据中心**, 自定义数据中心数据库,实现自己的云数据库.
7. **发布功能**。 支持将文章发布到博客平台上。
8. **邮件发送功能**
9. **全文分词搜索**
10. **ppt**
11. **ppt跨屏演示**
12. **pdf预览**
13. **typewriter scrolling**
14. **autocomplete 和 snippets 功能**
15. **链接关系图**
16. **反向链接**
17. **微信公众号分享**

# 离线版下载地址

http://soft.xiaoshujiang.com

# WEB版访问地址

http://markdown.xiaoshujiang.com

___

# 元数据使用说明

语法开关元数据项，可以到设置面板里的语法扩展标签页下查看对应的元数据标识．在元数据里true时，表示当前文档强制打开该语法，false时表示强制关闭该语法．如果没有对应的元数据，则使用全局设置里的语法开关.

`preview_previewType`元数据，可用的值为`normal`和`presentation`．用于文章在打开时，控制是否需要系统切换对应的预览界面．如果文章里没有该项元数据，或者元数据值不正确，则系统默认使用`normal`预览界面．该元数据仅控制文章打开时初始化的界面，用户依然可以通过按钮在不同预览界面间切换．

___

# 浏览器存储
系统对创建的文章，都会在浏览器存储上进行保存。包括像evernote/印象笔记/github/dropbox等导入的文章，也都会保存一份副本，并创建一个标识，表示跟哪些第三方存储关联。

## 标题，标签
文章标题的处理规则：如果文章内存在元数据title，则系统自动使用元数据内的title做为标题。如果文章未使用到元数据功能，用户可以通过维护文章信息按钮，修改标题。标签tags的规则也跟标题一样。
## 附件
文章使用`./`做为附件的引用标识。对于`图片`，`音频`，`视频`，`附件`等链接的处理，系统只处理以`./`开头的链接，并转换成附件真实的地址进行显示。用户可以通过工具栏的`插入图片`，`插入音频`，`插入视频`，`插入附件`等按钮上传附件。

___

# evernote/印象笔记
小书匠编辑器提供对evernote/印象笔记的支持，下面的使用说明默认用户已经完成了evernote/印象笔记的绑定操作，并将当前的工作平台切换到evernote/印象笔记下。
## 新建
通过新建按钮后，创建的文章将自动关联到evernote/印象笔记上(**注:这里仅仅是在文章上创建一个关联的标识，只有当用户保存后，才能在服务器上查看到新的笔记**)
## 打开
点击笔记，系统将自动把笔记导入，并将当前文章切换为导入的笔记内容。导入的文章自动与evernote/印象笔记上的笔记关联，下次再点击该笔记时，将直接从浏览器存储上打开。用户可以通过切换存储平台`浏览器存储`，来删除该缓存的文件。导入的笔记如果本地没有缓存，系统将对服务器上的笔记进行判断，如果笔记是通过小书匠编辑器进行保存，并且文章在保存后没有被操作过，则系统自动使用保存时附带的markdown附件做为文章内容，重新导入。如果笔记已经被修改，或者笔记不是通过小书匠编辑器进行保存的，系统将自动将文章转换成markdown格式。
## 保存
对于新创建的文章，用户可以直接保存`ctrl+s`，系统将弹出一个选择笔记本的窗口，确认后，系统将保存当前文章到evernote/印象笔记上。（在弹出窗口上选择笔记本时，如果用户选择了笔记，系统将覆盖该笔记）

对于已经存在的文章，但还没有保存到evernote/印象笔记，用户可以通过另存为`ctrl+shift+s`将当前文章保存到evernote/印象笔记上。

不管是保存，还是另存为，保存成功后，系统都将自动对当前文章与evernote/印象笔记上的笔记进行关联。下次保存时`ctrl+s`系统将自动同步保存到evernote/印象笔记上。
## 删除
系统不提供删除操作，用户需要自己到evernote/印象笔记端删除，如果本地缓存了笔记，可以通过`浏览器存储`删除缓存。
## 重命名
直接修改元数据title，如果文章内未使用元数据功能，可通过`浏览器存储`里的修改文章信息进行修改
## 标签管理
系统自动通过每篇文章的元数据`tags`提取为笔记的标签。
## 附件管理
打开时，系统自动将笔记上的附件导入到文章对应的附件管理器上。保存时，系统将根据**文章内对附件的引用**，将附件保存到服务器上。这里的引用包括`音频`，`视频`，`附件`，`图片`。如果文章内使用到了`流程图`，`序列图`，`公式`，`统计图`等，系统将会把这些内容转换成图片进行保存。由于evernote/印象笔记在部分终端不提供视频，音频的支持，查看保存的文章时，对应的音频，视频将以附件的形式存储。
## 待办事项
目前系统仅同步了待办事项。

___

# github/dropbox

## 新建
参考`evernote/印象笔记`的`新建`

## 打开
参考`evernote/印象笔记`的`打开`
不同的是，github/dropbox只能打开扩展名为`html`，`markdown`，`md`，`mkd`以及无扩展名的文件。
## 保存
参考`evernote/印象笔记`的`保存`
不同的是，github/dropbox保存时，仅保存了markdown文章本身，并不会将markdown转换成html进行保存，也不会处理附件相关的内容。
对于新文章的保存，github/dropbox存储需要用户指定文件名及存储的位置。

## 删除
系统不提供删除操作
## 重命名
系统不提供重命名操作，只能通过另存为`ctrl+shift+s`，保存成新的文件。

___

# 本地文件系统存储
本地文件系统存储仅在离线版提供支持。
## 新建
参考`evernote/印象笔记`的`新建`

## 打开
参考`github/dropbox`的`打开`
不同的是，本地文件系统存储在打开文件时，将会自动关联文章内的附件引用标识`./`，自动抓取同级目录下对应的附件资源。
## 保存
参考`github/dropbox`的`保存`
不同的是，本地文件系统存储在保存时，不仅保存了markdown文章，还会处理附件相关的内容，将附件保存到同级目录下，请确保附件的名称不要重复，防止数据被覆盖丢失。

## 删除
右击相应的文章可进行删除操作
## 重命名
右击相应的文章可进行重命名操作

___

# 发布
小书匠编辑器**离线版**提供文章发布功能，用户可以将自己的文章发布到博客系统上。发布功能实现了博客的metaweblogAPI（newPost, editPost, newMediaObject）。使用该发布功能，需要博客系统提供对应的api接口，系统将转换成html的文章和图片自动提交到博客系统上。

**配置发布示例：**
博客链接地址：比如`http://www.cnblogs.com/[用户名]/`
用户名：用户在该博客上的用户名
密码：用户在该博客上的密码

**测试通过的博客地址：**
博客园：`http://www.cnblogs.com/[用户名]/`
开源中国：`http://my.oschina.net/[用户名]/blog`

___

# 邮件发送
小书匠编辑器提供邮件发送功能，系统将对当前文章转换成html格式后进行发送，并对图片，视频等文件以附件的形式进行发送。

___

# 导出
小书匠编辑器提供多种格式的导出文件功能。==html==,==markdown==,==html(inlinestyle)==,==word==,==zip==,==pdf==。

**zip导出**： 该导出将导出文章的所有信息，包括markdown,html,markdown文章内引用的所有附件，公式，流程图等对应的图片文件，以及方便再次导入时需要的标识数据文件。

**pdf导出**：目前pdf导出只能在chrome版浏览器上使用。

___

# 导入
小书匠编辑器提供markdown, html, zip三种导入功能，并且实现了文本文件直接拖动导入功能。

**zip导入**：导入的zip文件必需是由小书匠编辑器导出的文件。

___

# 其他
web版实现了图片直接粘贴功能，用户不仅可以拖动图片上传，还可以直接复制粘贴图片。





[小书匠更新手册](storywriter/upgrade_log)
[小书匠语法手册](storywriter/grammar)
[小书匠使用手册](storywriter/tutorial)