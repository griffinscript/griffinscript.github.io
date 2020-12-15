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
## 注释
# 声明
## 变量
GS推荐使用```let```定义变量，同时也支持通过```var```来定义变量，两种语法的作用域符合ES6规范，但是GS不支持先使用再申明变量，未经申明的变量使用会产生编译期错误。
## 声明变量
## 变量求值
## 变量的作用域
## 变量提升
## 函数提升
GS 的函数必须先定义再使用
```javascript
/* 函数声明 */

foo(); // "bar"

function foo() {
  console.log("bar");
}
```

上面的代码会提示:```runProgram exception : Run program failed.undefined object: foo```

## 全局变量
window是浏览器的全局变量，在GS中不支持。
## 常量(Constants)

# 数据结构和类型
## 数据类型
## 数据类型的转换
## 字符串转换为数字
 ```parseInt()``` 和 ```parseFloat()```
## 字面量 (Literals)
### 数组字面量 (Array literals)
### 布尔字面量 (Boolean literals)
布尔类型有两种字面量：```true``` 和 ```false```。
### 整数 (Integers)
严格模式下，八进制整数字面量必须以0o或0O开头，而不能以0开头。
### 浮点数字面量 (Floating-point literals)
### 对象字面量 (Object literals)
### 增强的对象字面量 (Enhanced Object literals)
### RegExp 字面值
### 字符串字面量 (String literals)
GS暂时不支持模板字面量
```javascript
var poem =
`Roses are red,
Violets are blue.
Sugar is sweet,
and so is foo.`
console.log(poem);
```
以上写法会报错。

---
以上文档和下面的MDN校验，主要描述有差异部门，没有描述的部分默认行为一致。
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_Types#%E5%9F%BA%E7%A1%80
---

