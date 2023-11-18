---
layout: post
title: ﻿sublime 配置 MinGW 搭建 C/C++ 编译环境
categories: [环境配置,sublime]
description: sublime 配置 MinGW 搭建 C/C++ 编译环境
keywords: sublime,MinGW,C/C++编程环境
---



1. 当安装好 MinGW 和 sublime text 后，执行下面 2 个动作：

2. 按照菜单 Tools ==> Build System ==> New Build System 新建一个 “Build System”，其中输出下面内容：
	```json
	{
	  "working_dir": "$file_path",
	  "cmd": "gcc -Wall -fexec-charset=GBK \"$file_name\" -o \"$file_base_name\"",
	  "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	  "selector": "source.c",
	 
	  "variants": 
	  [
	    { 
	    "name": "Run",
	          "shell_cmd": "gcc -Wall -fexec-charset=GBK \"$file\" -o \"$file_base_name\" && start cmd /c \"\"${file_path}/${file_base_name}\" & pause\""
	    }
	  ]
	}
	```

	> 当然如果要编译 c++ 程序，可以将 gcc 换成 g++：
	> ```json
	> {  
	>   "working_dir": "$file_path",
	>   "shell_cmd": "g++ -Wall -std=c++14 -fexec-charset=GBK \"$file_name\" -o \"$file_base_name\"",
	>   "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	>   "selector": "source.c, source.c++",
	> 
	>   "variants": 
	>   [
	>     { 
	>     "name": "Run",
	>         "shell_cmd": "g++ -Wall -std=c++14 -fexec-charset=GBK \"$file\" -o \"$file_base_name\" && start cmd /c \"\"${file_path}/${file_base_name}\" & pause\""
	>  }
	>   ]
	> }
	> ```
	>
	> 如果是 Linux/Unix 系统，需要将 cmd 换成 bash，例如：
	> ```json
	> {
	> "cmd": ["g++", "-std=c++14", "${file}", "-o", "${file_path}/${file_base_name}"],
	> "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	> "working_dir": "${file_path}",
	> "selector": "source.c, source.c++",
	> "variants":
	> [
	>  {
	>      "name": "Run",
	>      "cmd":["bash", "-c", "g++ -std=c++1y '${file}' -o '${file_path}/${file_base_name}' && '${file_path}/${file_base_name}'"]
	>    }
	>  ]
	> }
	> ```
	
3. 将该 “Build System” 保存为比如 “cpp.sublime-build” 到 “…/Packages/User/” （如：`C:\Users\lenovo\AppData\Roaming\Sublime Text 3\Packages\User\`）目录下：`C:\Users\lenovo\AppData\Roaming\Sublime Text 3\Packages\User\cpp.sublime-build`

   ![image-20210717195425590](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/pic/20210717195721.png)

4. 重启 sublime，在 Tools ==> Build System 选择 C

5. 当要编译或运行 C 程序时，可以 “Ctrl + Shift + B”。在弹出菜单中先选择 “C” 表示编译，然后选择 “C-Run” 表示运行！
