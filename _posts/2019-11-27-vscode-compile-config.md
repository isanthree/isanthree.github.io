---
layout: post
title: 【vscode】vscode gcc编译教程
categories: [环境配置,vscode]
description: vscode gcc编译教程过程记录
keywords: vscode, 环境配置

---



# vs code gcc编译教程

1. 将[MinGW.rar](https://github.91chifun.workers.dev/https://github.com//isanthree/my-files/releases/download/v1.0/MinGW.rar)解压到任意文件夹，比如，解压至D:\software\目录下

2. 将D:\software\MinGW\bin添加到环境变量

3. 打开vs code

   （1）可选：安装chinese(Simplified) Language Pack for Visual Studio Code插件，中文语言包

   （2）安装C/C++

   （3）安装code runner

   （4）安装include autocomplete

   （5）将[.vscode文件夹](https://github.com/isanthree/my-files/raw/master/vscode/.vscode.zip)复制到存放代码的目录（文末附录会附上文件夹里面的文件内容）

4. 还是保持打开vscode

   （1）打开.vscode所在目录

![1573569707223](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210515232307.png)

   （2）选中.vscode所在文件夹

<img src="https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210515232651.png" alt="1573569750320"  />



   （3）在vscode界面，文件---首选项---设置

![1573570035308](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516002020.png)

   （4）出现如下界面，如图配置（我是用户和工作区都这么配置了）

![1573567528435](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516002030.png)



\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\= 分割线 \=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=

调试，选的是这个，如果没有，好像需要添加，添加这个即可

![1573570234133](https://cdn.jsdelivr.net/gh/isanthree/blog-gallery/20210516002036.png)

\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\== 分割线 \=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=

= = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = 



# 附录

.vscode文件如下：

## c_cpp_properties.json

c_cpp_properties.json

```json
{
    "configurations": [
        {
            "name": "Win32",
            "includePath": [
                "${workspaceFolder}"
            ],
            "defines": [
                "_DEBUG",
                "UNICODE",
                "_UNICODE"
            ],
            "compilerPath": "D:\\software\\MinGW\\bin\\gcc.exe",
            "intelliSenseMode": "msvc-x64",
            "browse": {
                "path": [
                    "${workspaceFolder}"
                ],
                "limitSymbolsToIncludedHeaders": true,
                "databaseFilename": ""
            },
            "cStandard": "c11",
            "cppStandard": "c++17"
        }
    ],
    "version": 4
}
```

## launch.json

launch.json

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "C++ Launch (GDB)", // 配置名称，将会在启动配置的下拉菜单中显示
            "type": "cppdbg", // 配置类型，这里只能为cppdbg
            "request": "launch", // 请求配置类型，可以为launch（启动）或attach（附加）
            "targetArchitecture": "x64", // 生成目标架构，一般为x86或x64，可以为x86, arm, arm64, mips, x64, amd64, x86_64
            "program": "${file}.exe", // 将要进行调试的程序的路径
            "miDebuggerPath": "D:\\software\\MinGW\\bin\\gdb.exe", // miDebugger的路径，注意这里要与MinGw的路径对应
            "args": [], // 程序调试时传递给程序的命令行参数，一般设为空即可
            "stopAtEntry": false, // 设为true时程序将暂停在程序入口处，一般设置为false
            "cwd": "${workspaceRoot}", // 调试程序时的工作目录，一般为${workspaceRoot}即代码所在目录
            "environment": [],
            "MIMode": "gdb",
            "externalConsole": true, // 调试时是否显示控制台窗口，一般设置为true显示控制台
            "preLaunchTask": "g++" // 调试会话开始前执行的任务，一般为编译程序，c++为g++, c为gcc
        }
    ]
}
```

## settings.json

settings.json

```json
{
    "C_Cpp.intelliSenseEngineFallback": "Disabled",
    "files.associations": {
        "cmath": "cpp",
        "iostream": "cpp",
        "new": "cpp",
        "*.tcc": "cpp",
        "ostream": "cpp",
        "sstream": "cpp",
        "array": "cpp",
        "cctype": "cpp",
        "clocale": "cpp",
        "cstdint": "cpp",
        "cstdio": "cpp",
        "cstdlib": "cpp",
        "cstring": "cpp",
        "ctime": "cpp",
        "cwchar": "cpp",
        "cwctype": "cpp",
        "deque": "cpp",
        "unordered_map": "cpp",
        "vector": "cpp",
        "exception": "cpp",
        "fstream": "cpp",
        "functional": "cpp",
        "initializer_list": "cpp",
        "iomanip": "cpp",
        "iosfwd": "cpp",
        "istream": "cpp",
        "limits": "cpp",
        "stdexcept": "cpp",
        "streambuf": "cpp",
        "system_error": "cpp",
        "type_traits": "cpp",
        "tuple": "cpp",
        "typeinfo": "cpp",
        "utility": "cpp",
        "atomic": "cpp",
        "bitset": "cpp",
        "cfenv": "cpp",
        "chrono": "cpp",
        "cinttypes": "cpp",
        "codecvt": "cpp",
        "complex": "cpp",
        "condition_variable": "cpp",
        "csetjmp": "cpp",
        "csignal": "cpp",
        "cstdarg": "cpp",
        "cstddef": "cpp",
        "cuchar": "cpp",
        "forward_list": "cpp",
        "list": "cpp",
        "unordered_set": "cpp",
        "future": "cpp",
        "memory": "cpp",
        "mutex": "cpp",
        "numeric": "cpp",
        "ratio": "cpp",
        "scoped_allocator": "cpp",
        "shared_mutex": "cpp",
        "thread": "cpp",
        "typeindex": "cpp",
        "valarray": "cpp",
        "map": "cpp",
        "memory_resource": "cpp",
        "optional": "cpp",
        "string_view": "cpp"
    },
    "terminal.explorerKind": "external",
    "C_Cpp.errorSquiggles": "Enabled"
}
```



## tasks.json

tasks.json

```json
{
    "version": "2.0.0",
    "command": "g++",
    "args": [
        "-g",
        "${file}",
        "-o",
        "${file}.exe",
    ], // 编译命令参数
    "problemMatcher": {
        "owner": "cpp",
        "fileLocation": [
            "relative",
            "${workspaceRoot}"
        ],
        "pattern": {
            "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
            "file": 1,
            "line": 2,
            "column": 3,
            "severity": 4,
            "message": 5
        }
    }
}
```

