---
layout:     post
title:      Epic平台 GTA5 使用MOD
subtitle:   姿势
date:       2020-5-26
author:     kkzh
header-img: img/optimization.png
catalog: true
tags:
    - 闲聊
---

## 前言

Epic 这个破平台竟然免费送 GTA5 了，相信每个使用过的人都能切身体会到什么是正版游戏受害者。。。

骂归骂，香还是要香的，但我的宗旨是，在 PC 玩单机游戏怎么能不用 MOD，不用 MOD 实在太可惜了。

但问题是 Epic 平台的 GTA5 版本是1868.4，而（前）最多 PC 用户的 Steam 是1868.1 的，某些不想多说的原因，ScriptHookV.dll 的官网已经关闭了，这个插件能不能兼容 Epic 代表了我们能不能在Epic 平台的 GTA5 中使用 MOD，但运气不错的是两个版本之间的改变并不多，哈希值不需要做出太多的改变，国外有大神已经通过反编译手段，把 1868.1 的 ScriptHookV.dll 插件做了一点修改，使其兼容了 Epic 版本的1868.4，所以现在两个版本都能用 MOD 了。

话不多说，记录一下我用的MOD，以作备份。

---

## 插件

没添加网址的插件都能在 zh.gta5-mods.com 里搜索到

必装插件不需要我说了吧 ScriptHookV，NativeUI，ScriptHookVDotNet，OpenIV（OpenIV自带官方中文，软件自带该插件）

[**ScriptHookV**](https://gtaforums.com/topic/717612-v-scriptnative-documentation-and-research/page/39/#comments) <br>先去 [zh.gta5-mods.com](zh.gta5-mods.com) 里下载 1868.1 版的，解压到游戏根目录后，再把这里下载的 ScriptHookV 覆盖进去。


**Addon Peds Editor** 添加人物 MOD 必备，有汉化版

**Character Swap** 让你可以用 MOD 人物来过主线任务，游侠有汉化版

**Added Traffic** 能够使得线下也能自动刷出 DLC 车辆和 MOD 车辆

**The Character Vehicle** 在单机里更改主角的默认车轴，还能在有后备箱的车辆里保存你的武器，把你不需要的武器放在后备箱里

**GTA V Modding Launcher** 一键转移MOD，轻松切换线上线下

**Gameconfig**,Heap Limit Adjuster，Packfile Limit Adjuster，三个MOD都是增加MOD上限，三个都装

**LeFix Simple Fuel** 简单燃油系统，让你的汽车需要到加油站里加油 

[**LeFix Speedometer**](https://zh.gta5-mods.com/scripts/lefix-speedometer ) 配合上面的燃油系统，很不错

[**MrchaztaSmartFuelMod**](https://game.ali213.net/thread-6258674-1-1.html ) 最完善的燃油系统汉化版，需要LUA插件

[**简繁字体兼容**](https://game.ali213.net/thread-6410926-1-1.html) 游戏不再出现口口

**载具防消失补丁**，DLC车辆是不能在单机里使用的，这个插件解决了这个限制，这个我忘记在哪里下的了，网上挺容易找到

**Sitting** 可以在地图的椅子上坐下，可以回血

修改器类：
[**Enhanced Native Trainer**](https://game.ali213.net/thread-6385570-1-1.html ) 我个人感觉最好用的一款修改器，游侠的汉化版不是最新版

**menyoo** 有汉化，功能很多的一个内置修改器

**NativeTrainer** 有汉化，和ScriptHookV.dll一起的一款修改器，基本满足一般要求

---

## 经验

直接在根目录新建 commandline.txt 文件，然后里面写上 -scOfflineOnly 即可自动以离线模式运行，Epic 要离线模式，不然一样启动半天

人物 MOD 我就不啰嗦了，我暂时只用了2B A2 Tifa 不知火舞 洛奇英雄传的Vella，DOA的角色HONOKA Christie Kokoro Tamaki helena cristie Luna Tina Momiji...

如果你要替换 NPC，一定要小心，因为部分人物 MOD，你用修改器刷出来的正常，但如果让系统自动刷出来，那你的游戏就会莫名闪退

用 OpenIV 替换角色，角色文件名可以在 NativeTrainer 修改器的xml文件里找到，直接在 OpenIV 里按 Ctrl+F3 全局搜索，如果发现有多个 patchday7ng、patchday10ng 等重复的文件，直接替换最新的 patchday10ng 文件夹里的人物文件。

我个人是推荐不要替换的，因为有可能出现各种奇怪问题

---

时间有点紧，暂时写到这