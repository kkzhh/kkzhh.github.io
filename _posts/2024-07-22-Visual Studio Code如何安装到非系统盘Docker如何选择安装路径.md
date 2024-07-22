---
layout:     post
title:      Visual Studio Code/VsCode 如何安装到非系统盘/Docker如何选择安装路径
subtitle:   姿势
date:       2024-07-22
author:     kkzh
header-img: img/optimization.png
catalog: true
tags:
    - 分享
    - 安装
---

很简单，根据官网介绍
```
What command-line arguments are supported by the Windows Setup?

VS Code uses Inno Setup to create its setup package for Windows. Thus, all the Inno Setup command-line switches are available for use.

Additionally, you can prevent the Setup from launching VS Code after completion with /mergetasks=!runcode.
```

可以得知能直接在 CMD 界面指定目录，所以举例：
`
Z:\Downloads>VSCodeUserSetup-x64-1.91.1.exe /dir="D:\Software\Microsoft VS Code"
`

`Z:\Downloads>VSCodeUserSetup-x64-1.91.1.exe` Z盘下的安装文件

`D:\Software\Microsoft VS Code` 想要安装到的目录