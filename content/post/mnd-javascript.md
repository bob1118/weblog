---
title: "Mnd Javascript"
date: 2021-06-15T09:24:52+08:00
lastmod: 2021-06-15T09:24:52+08:00
draft: true
keywords: [jvavascript]
description: "learn mdn javascript"
tags: [javascript]
categories: [pub]
author: "bob"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: true
autoCollapseToc: false
postMetaInFooter: true
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

# You can enable or disable out-of-date content warning for individual post.
# Comment this out to use the global config.
#enableOutdatedInfoWarning: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

<!--more-->
# 3 JAVASCRIPT

<https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript>

## 3.1 First Steps

### 3.1.1 概述

#### 3.1.1.1 Prerequisites

#### 3.1.1.2 Guides

#### 3.1.1.3 Assessments

### 3.1.2 什么是javascript

#### 3.1.2.1 javascript定义

javascript是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不在是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D动画，滚动播放的视频等等。

- HTML是一种标记语言，用来结构化我们的网页内容并赋予内容含义，例如定义段落、标题和数据表，或在页面中嵌入图片和视频。
- CSS 是一种样式规则语言，可将样式应用于 HTML 内容， 例如设置背景颜色和字体，在多个列中布局内容。
- JavaScript 是一种脚本语言，可以用来创建动态更新的内容，控制多媒体，制作图像动画，还有很多。

#### 3.1.2.2 javascript可以做什么

javascript api分类

- 浏览器api，内建与web浏览器，他们可以将数据从周边计算机环境中筛选出来，还可以做复杂的工作。
  - Document Object Model API 能通过创建、移除和修改HTML，为页面动态应用咸阳市等手段来操作HTML和CSS。
  - Geolocation API 获取地理信息。
  - Canvas/WebGL API 可以创建生动的2D和3D图像。
  - audio/video API 可以i利用多媒体做一些非常有趣的事。
- 第三方api
  - [Weibo API](https://open.weibo.com/)
  - [Twitter API](https://dev.twitter.com/overview/documentation)
  - [GoogleMap API](https://developers.google.com/maps/)
  - [AMap API](https://lbs.amap.com/)

#### 3.1.2.3 javascript在页面上做了什么

- 浏览器安全
- JavaScript运行次序
- 解释代码VS编译代码
- 服务端VS客户端
- 动态代码VS静态代码

#### 3.1.2.4 向页面添加JavaScript

css使用[\<link\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)元素链接外部样式表，使用[\<style\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/style)元素向HTML嵌入内部样式表，javascript这里只需要一个元素[\<script\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script)。

- 内部javascript
- 外部javascript
- 内联javascript
- 脚本调用策略
- async和defer

#### 3.1.2.5 注释

```javascript
//我是一行注释

/*
我是多行注释
我是多行注释
*/
```

### 3.1.3 Javascript初体验

#### 3.1.3.1 像程序员一样思考

#### 3.1.3.2 猜数字游戏

- 初始设置
- 添加变量
- 函数
- 运算符
- 条件语句
- 事件
  - Event Listener
  - Event Handler
- 补全代码
- 循环
- 对象
- 浏览器对象

#### 3.1.3.3 大功告成

<https://roy-tian.github.io/learning-area/javascript/introduction-to-js-1/first-splash/number-guessing-game.html>

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">

    <title>猜数字游戏</title>

    <style>
        html {
            font-family: sans-serif;
        }

        body {
            width: 50%;
            max-width: 800px;
            min-width: 480px;
            margin: 0 auto;
        }

        .lastResult {
            color: white;
            padding: 3px;
        }
    </style>
</head>

<body>
    <h1>猜数字游戏</h1>

    <p>我刚才随机选定了一个100以内的自然数。看你能否在 10 次以内猜中它。每次我都会告诉你所猜的结果是高了还是低了。</p>

    <div class="form">
        <label for="guessField">请猜数：</label><input type="text" id="guessField" class="guessField">
        <input type="submit" value="我猜" class="guessSubmit">
    </div>

    <div class="resultParas">
        <p class="guesses"></p>
        <p class="lastResult"></p>
        <p class="lowOrHi"></p>
    </div>

    <script>
        let randomNumber = Math.floor(Math.random() * 100) + 1;
        const guesses = document.querySelector('.guesses');
        const lastResult = document.querySelector('.lastResult');
        const lowOrHi = document.querySelector('.lowOrHi');
        const guessSubmit = document.querySelector('.guessSubmit');
        const guessField = document.querySelector('.guessField');
        let guessCount = 1;
        let resetButton;

        function checkGuess() {
            let userGuess = Number(guessField.value);
            if (guessCount === 1) {
                guesses.textContent = '上次猜的数：';
            }

            guesses.textContent += userGuess + ' ';

            if (userGuess === randomNumber) {
                lastResult.textContent = '恭喜你！猜对了！';
                lastResult.style.backgroundColor = 'green';
                lowOrHi.textContent = '';
                setGameOver();
            } else if (guessCount === 10) {
                lastResult.textContent = '!!!游戏结束!!!';
                lowOrHi.textContent = '';
                setGameOver();
            } else {
                lastResult.textContent = '你猜错了！';
                lastResult.style.backgroundColor = 'red';
                if (userGuess < randomNumber) {
                    lowOrHi.textContent = '你刚才猜低了！';
                } else if (userGuess > randomNumber) {
                    lowOrHi.textContent = '你刚才猜高了！';
                }
            }

            guessCount++;
            guessField.value = '';
            guessField.focus();
        }

        guessSubmit.addEventListener('click', checkGuess);

        function setGameOver() {
            guessField.disabled = true;
            guessSubmit.disabled = true;
            resetButton = document.createElement('button');
            resetButton.textContent = '开始新游戏';
            document.body.appendChild(resetButton);
            resetButton.addEventListener('click', resetGame);
        }

        function resetGame() {
            guessCount = 1;
            const resetParas = document.querySelectorAll('.resultParas p');
            for (let i = 0; i < resetParas.length; i++) {
                resetParas[i].textContent = '';
            }

            resetButton.parentNode.removeChild(resetButton);
            guessField.disabled = false;
            guessSubmit.disabled = false;
            guessField.value = '';
            guessField.focus();
            lastResult.style.backgroundColor = 'white';
            randomNumber = Math.floor(Math.random() * 100) + 1;
        }
    </script>
</body>

</html>
```

### 3.1.4 Javascript代码的错误

#### 3.1.4.1 错误类型

- 语法错误
- 逻辑错误
- 其他错误

#### 3.1.4.2 出错的示例

#### 3.1.4.3 修复语法错误

### 3.1.5 变量

#### 3.1.5.1 声明变量

#### 3.1.5.2 初始化变量

#### 3.1.5.3 var与let的区别

#### 3.1.5.4 更新变量

#### 3.1.5.5 变量类型

- Number
- String
- Boolean
- Array
- Object

#### 3.1.5.6 动态类型

### 3.1.6 数字与运算符

#### 3.1.6.1 数字

- Number
  - 整数
  - 浮点数
  - 双精度
- 进制
  - 二进制
  - 八进制
  - 十六进制

#### 3.1.6.2 算术运算符

- 加法(+)
- 减法(-)
- 乘法(*)
- 除法(/)
- 求余(%)
- 幂(**)

#### 3.1.6.3 自增和自减

- 自增(++)
- 自减(--)

#### 3.1.6.4 赋值运算符

- 加法赋值(+=)
- 减法赋值(-=)
- 乘法赋值(*=)
- 除法赋值(/=)

#### 3.1.6.5 比较运算符

- 严格等于(===)
- 严格不等于(!==)
- 小于(<)
- 大于(>)
- 小于等于(<=)
- 大于等于(>=)

### 3.1.7 字符串

#### 3.1.7.1 基本知识

- 单引号和双引号
- 转义字符(\\)

#### 3.1.7.2 连接字符串

### 3.1.8 有用的字符串方法

#### 3.1.8.1 字符串当对象

- 字符串长度[(length)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- 检索字符
- 查找子串[(indexOf)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
- 大小写[(toLowerCase)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)[(toUpperCase)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)
- 替换字符串[(replace)](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

### 3.1.9 数组

#### 3.1.9.1 什么是数组

#### 3.1.9.2 有用的方法

- 字符串和数组转换
  - [split](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split)
  - [join](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
  - [toString](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/toString)
- 添加删除数组项
  - [unshift](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
  - [shift](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
  - [push](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
  - [pop](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)

### 3.1.10 笑话生成器

## 3.2 Javascript基础要件

### 3.2.1 基础要件概述

### 3.2.2 条件语句

### 3.2.3 代码循环

### 3.2.4 函数

### 3.2.5 建立自己的函数

### 3.2.5 函数返回值

### 3.2.6 事件介绍

在web中，[事件](https://developer.mozilla.org/zh-CN/docs/Web/Events)在浏览器窗口中被触发并且通常被绑定到窗口内部的特定部分。

#### 3.2.6.1 事件举例

- 用户在某个元素上点击鼠标或者悬停光标。
- 用户在键盘按下某个按键。
- 用户调整浏览器的大小或关闭浏览器。
- 页面停止加载。
- 提交表单。
- 播放、暂停、关闭视频。
- 发生错误。
- 等...

#### 3.2.6.2 使用事件

- 事件处理器属性
- 行内事件处理器
- [addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
- [removeEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)

#### 3.2.6.2 其他事件概念

- 事件对象
- 阻止默认行为
- 事件冒泡及捕获

## 3.3 Javascript对象介绍

### 3.3.1 对象概述

### 3.3.2 对象基础概念

### 3.3.3 适合新手的javascript

### 3.3.4 对象原型

### 3.3.5 继承

### 3.3.6 JSON

### 3.3.7 对象构建实践

## 3.4 Javascript异步

### 3.4.1 异步概述

### 3.4.2 异步编程概念

### 3.4.3 异步JavaScript简介

### 3.4.4 超时和间隔

### 3.4.5 优雅的异步处理

### 3.4.6 async和await

### 3.4.7 选择正确的方法

## 3.5 客户端网页API

### 3.5.1 网页API介绍

### 3.5.2 操纵文档

### 3.5.3 从服务器获取数据

### 3.5.4 第三方API

### 3.5.5 画图

### 3.5.6 视频与音频

### 3.5.7 客户端存储
