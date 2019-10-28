---
layout:     post
title:      Firefox 怎么安装 userChrome\\IDM不显示下载浮动条\\Firefox 右键关闭标签页
subtitle:   姿势
date:       2019-09-13
author:     kkzh
header-img: img/optimization.png
catalog: true
tags:
    - 闲聊
---


## 前言

在经过 Firefox 和 IDM 的几轮更新后，某天开开心心的准备下载一个网页视频的时候，突然发现 IDM 的下载浮动条竟然不显示了，竟然不显示了呀！不显示了我就无法下载网页视频了，无法下载网页视频我就很不开心，考虑到做人最重要就是要开心，而 IDM 是让我开心下载网页视频最最重要的工具，于是我决定解决这个使我不开心的因素。

第一时间上 IDM 官网和部分论坛查看帖子，看有没有人和我出现同样的情况。

在仔细查看完 IDM 更新历史后，发现 IDM 才刚刚修复了 Firefox 的兼容问题，但是我明明已经更新到最新版本了，却依旧出现问题，而论坛上也没有一个人反映有遇到和我相同的问题的，并且在我电脑上的 Chrome 和 Edge 都能正常使用，到了这一步，估计是我的个人问题了。

在我参考了官网的解决方案一一排查下，发现罪魁祸首竟然是 FireDoge v1.1.5 版本和 IDM 浏览器扩展出了冲突，两个都使我开心的工具，竟然只能二选一。因为 FireDoge 的作者 shuax 已经不再更新这个外挂插件了，那我的开心不就只剩一半了吗？不行，我要挣扎一下。

在网上查了下资料后，最终决定放弃 FireDoge，使用 userChrome 和 Gesturefy 来代替，毕竟  FireDoge 的功能全部都有替代品，但 IDM的方便快捷有效上，暂时没找到替代软件。

#### Internet Download Manager

 IDM 在 HTTP 和 FTP 下载方面无可质疑的是一款神器。

#### Gesturefy

Gesturefy 是 Firefox 的一款免费鼠标手势扩展，使用简单方便，功能多样。

#### userChrome

userChrome（下面简称 UC） 是由 Zeniko 从 userChrome.js 衍生而来的一款插件，其可以最大程度的对Firefox进行控制。但在 Firefox 57 更新以后，就决定了这是以后肯定会被淘汰的插件了，但就目前来看，被淘汰的时间还没远远没到，下面详细介绍。

<br>

## 安装

**两步完成安装：**

首先，在地址栏输入：about:config，无视警告后再搜索 toolkit.legacyUserProfileCustomizations.stylesheets，双击参数设置属性为 true。

然后下载UC插件：

目前还在维护的 UC 项目是 alice0775 的
https://github.com/alice0775/userChrome.js

打开上述项目后，根据自己的版本分别下载 **userChrome.css**、**userChrome.js** 和 **userChrome.xml** 三个文件，其余 JS 文件均为维护者正在使用的 JS 脚本。

![enter description here](https://pic.superbed.cn/item/5d7b3843451253d178ab6f55.jpg)

![一般在项目的最下面](https://pic.superbed.cn/item/5d788f03451253d1785b1620.jpg)

接着在 Firefox 浏览器的网址栏输入 about:support ，回车，并打开配置文件夹

![enter description here](https://pic.superbed.cn/item/5d789016451253d1785b3511.jpg)

在打开的配置文件夹中新建文件夹 chrome，将以上三个下载的文件丢进去即完成 userChrome 的安装。

<br>

但是 userChrome 安装完成后没有用，还需要把你的 UC 脚本复制粘贴到 chrome 文件夹中，但 UC 脚本就需要你们自己去找了 。

比如这次我最需要的功能是 “鼠标悬浮标签栏自动激活” 与 “右键关闭标签页” 功能，而 tabPlus.uc.js 脚本刚好有我需要的两个功能，把这个 js 文件移动到 chrome 文件夹中，再重启浏览器即可完成。

如果重启后功无法正常使用，那就可能是 Firefox 版本更新了，需要更新 UC 插件了。

又或者是脚本已经失效了。

又双或者是两者同时失效了。

 tabPlus.uc.js 里的代码里有 4 个功能，每个功能都有注释，条理很清晰。

//1.鼠标悬浮标签栏自动激活



``` javascript
((g, w) => {
  class TabPlus {
    constructor() {
      this.SelectedTabOnMouseover();
    }
    SelectedTabOnMouseover(timeout) {
      g.tabContainer.addEventListener('mouseover', e => {
        const tab = e.target.closest('.tabbrowser-tab');
        if (!tab) return;
        timeout = setTimeout(() => g.selectedTab = tab, 500);	//500表示鼠标悬浮标签多长时间后激活，以毫秒为单位
      }, false);
      g.tabContainer.addEventListener('mouseout', () => clearTimeout(timeout), false);
    }
  }
  new TabPlus();
})(gBrowser, window);
```


userChrome 插件 & tabPlus 脚本打包下载： https://pan.baidu.com/s/1qkm9SVgQzMo8diHzI1jpxg 提取码: 1234 


转载请注明出处