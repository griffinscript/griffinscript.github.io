---
layout: default
title: Griffin Script
nav_order: 1
permalink: /
has_children: true
---

## 简介
Griffin Script（以下简称GS）是一种根据ECMAScript基本语法定义的一种针对物流实操和设备流程定义设计的DSL(领域编程语言)，基本的语法和ECMAScript 2015 (也被称为ECMAScript 6或者ES6，以下简称ES6) 保持一致，可以参考相关文档学习基本语法，本文主要介绍和ECMAScript有差异的部分。
## 通用限制
GS运作在ES6的strict mode下，同时GS对于代码有更严格的检查和要求，比如ES6允许省略必要的参数，但是GS会对于缺失的参数报错。所以ES6里面能运行的代码在GS引擎上可能会报错。
## 环境变量
GS引擎允许平台层通过```Bindings```设置脚本运行时环境变量，这些变量有点类似JavaScript里面的window或者console，可以不需要声明直接使用，但是这些变量禁止赋值。
## 关键字
除了ES6规定的关键词以外，GS额外定义了一个关键字```emit```，该关键字用于产生事件，请参考下文了解详细信息。同时字符 ```@``` 作为特殊字符保留。
## 字母大小写
GS 对大小写敏感，所有的变量，函数名等都需要正确的大小写，因此函数```foo()```与```Foo()```是不同的函数，
变量```myvariable```与```MyVariable```也是不同的。