## 微信小游戏的分包加载机制

### 概述

本示例如何使用微信小游戏支持库2.1.0的[分包加载](https://developers.weixin.qq.com/minigame/dev/tutorial/base/subpackages.html)功能

### 实现原理

通过写一个subpackage插件实现把不同js文件拷贝到不同目录，同时修改目录内的game.js

### 将该项目移植进您的游戏

* 将 scripts/wxgame/subpackage.ts 拷贝进您的项目
* 修改 config.wxgame.ts，将 ManifestPlugin 替换为 SubPackagePlugin （注意，您需要修改 build 和 publish）
* 修改 config.wxgame.ts 中的 CleanPlugin，将 subpackage 对应的目录清除
* 将示例项目的 EgretSubpackageLoading.js 拷贝进您的微信小游戏项目
* 修改微信小游戏项目的 game.json，引入 subpackages 属性，参考示例项目
* 修改微信小游戏项目的 game.js，添加调用 wx.loadSubPackage 的逻辑，参考示例项目


### 高级用法

* 您可以通过修改 SubPackagePlugin 的参数和 game.json 的 subpackage 字段配置多个 subpackage
* 您可以在游戏过程运行中，而不是游戏初始化时加载某个 subpackage，比如您可以在游戏启动时只加载一个登陆页面，在用户登陆之后再加载游戏主逻辑
* 每个 subpackage 可以包含多个 js 文件

### 问题反馈
使用过程中遇到疑问或者发现bug可以反馈至论坛，或者发送问题描述到我邮箱：linchaojie@egret.com