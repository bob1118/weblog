---
title: "Mdn Html"
date: 2021-05-30T20:22:15+08:00
lastmod: 2021-05-30T20:22:15+08:00
draft: true
keywords: [html]
description: "learn html from mdn web docs"
tags: [html]
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
# HTML

## 1. HTML介绍

### 1.1背景

1990 年，由于对 Web 未来发展的远见，Tim Berners-Lee 提出了 超文本 的概念，并在第二年在 SGML (en-US) 的基础上将其正式定义为一个标记语言。  
1993 年，IETF (en-US) 正式开始制定 HTML 规范，并在经历了几个版本的草案后于 1995 年发布了 HTML 2.0 版本。  
1994 年，Berners-Lee 为了 Web 发展而成立了 W3C (en-US)。  
1996 年，W3C 接管了 HTML 的标准化工作，并在1年后发布了 HTML 3.2 推荐标准。  
1999 年，HTML 4.0 发布，并在 2000 年成为 ISO (en-US) 标准。  
2008 年，两个组织（译注：即 W3C 和 WHATWG）发布了第一份草案。  
2014 年，两个组织（译注：即 W3C 和 WHATWG）发布了 HTML5 标准的最终版。

### 1.2入门

- 什么是HTML

HTML 是一种相当简单的、由不同元素组成的标记语言。  
HTML不是一门编程语言，而是一种用来告知浏览器如何组织页面的标记语言。  
HTML由一系列的元素（elements）组成，每一个元素都用一对开始和结束标签(\<\>)包裹。每一个标签以尖括号开始和结束。这些元素可以用来包围不同部分的内容，使其以某种方式呈现或者工作。

- 元素(Element)和属性(attribute)：

![元素实列](https://media.prod.mdn.mozit.cloud/attachments/2014/04/09/7659/a731e40efad1f6e0b728bfcf86c0035b/anatomy-of-an-html-element.png "\<p\>元素附带class属性")

- 一个完整的HTML页面案例:  

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>mywebsite</title>
  </head>
  <body>
    <p class="nice">hello world!</p>
  </body>
</html>
```

1. >\<!DOCTYPE html\>        声明文档类型。
2. >\<html\>\</html\>        \<html\>元素，该元素是一个根元素，包裹了整个页面。
3. >\<head\>\</head\>        \<head\>元素，该元素是一个容器，包含了你想包含在HTML页面但不想在HTML页面显示的内容。
4. >\<meta charset="utf-8">  \<mata\>元素的charset属性设置了文档使用的字符集。
5. >\<title\>\</title\>      \<title\>元素设置页面标题。浏览器在收藏页面的时候title的内容会做为书签的默认名称。
6. >\<body\>\</body\>        \<body\>元素包含你访问页面的所有可见内容。

### 1.3\<head\>

HTML中的\<head\>元素，他的内容不会在浏览器中显示，他的作用是保存页面中的一些元数据。  
包含在\<head\>中的一些元数据有\<title\>,\<meta\>,\<link\>等。

1. \<title\>元素是一项元数据，用来表示整个页面的标题。
   - >\<title\>here is tilte\</title\>
2. \<meta\>元素是一项元数据，用来描述数据的数据。
   - >\<meta charset="utf-8"\>
   - >\<meta name="author" content="Chris Mills"\>
   - >\<meta name="description" content="The MDN Learning Area aims to provide complete beginners to the Web with all they need to know ..."\>
   - >\<meta property="og:title" content="Mozilla Developer Network"\>
3. \<link\>元素
   - >\<link rel="shortcut icon" href="favicon.ico" type="image/x-icon"\>
   - >\<link rel="shortcut icon" href="https://developer.mozilla.org/static/img/favicon32.png"\>
4. HTML中应用CSS和JAVASCRIPT
   - >\<link rel="stylesheet" href="my-css-file.css"\>
   - >\<script src="my-js-file.js"></script\>
5. 为文档设定主语言
   - >\<html language="zh-CN"\>

### 1.4HTML文字基础

标题标签

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
```

段落标签

```html
<p>hello world</p>
```

斜体粗体下划线

```html
<i>斜体</i>
<b>粗体</b>
<u>下划线</u>
```

列表

```html
<ul>
  <li>豆浆</li>
  <li>油条</li>
  <li>豆汁</li>
  <li>焦圈</li>
</ul>
```

```html
<ol>
  <li>豆浆</li>
  <li>油条</li>
  <li>豆汁</li>
  <li>焦圈</li>
</ol>
```

### 1.5超链接

超链接是互联网提供的最令人兴奋的创新之一。  
通过将文本转换为[\<a\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a "mdn docs html element \<a\>")元素(锚元素)内的链接来创建基本链接。

几个简单的超链接例子：

```html
<ul>
  <li><a href="https://example.com">Website</a></li>
  <li><a href="mailto:m.bluth@example.com">Email</a></li>
  <li><a href="tel:+123456789">Phone</a></li>
</ul>

```

title属性：

`<a href="https://example.com" title="here is my website.">Website</a>`

target属性:

`<a href="https://example.com" title="here is my website." target= "_blank">Website</a>`

download属性:

```html
<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
   download="firefox-latest-64bit-installer.exe">
  下载最新的 Firefox 中文版 - Windows（64位）
</a>
```

### 1.6高级文字格式

- 描述列表(describtion list)

描述列表使用与其他列表类型不同的闭合标签 \<dl\>; 此外，每一项都用 \<dt\> (description term) 元素闭合。每个描述都用 \<dd\> (description description) 元素闭合。

```html
<dl>
<dt>培根</dt>
<dd>整个世界的粘合剂。</dd>
<dt>鸡蛋</dt>
<dd>一块蛋糕的粘合剂。</dd>
<dt>咖啡</dt>
<dd>一种浅棕色的饮料。</dd>
<dd>可以在清晨带来活力。</dd>
</dl>
```

- 引用(blockquote)
- 略缩语(abbr)
- 标记联系方式(address)
- 上标和下标(sup sub)
- 展示计算机代码(code pre var kbd samp)
- 标记时间(time)

### 1.7文档与网站构架

网站由若干html文档组成，每一个html文档包含若干的布局元素。

- 页眉 \<header\>
- 导航栏 \<nav\>
- 主内容 \<main\>
- 侧边栏 \<aside\>
- 页脚 \<footer\>
- 无语义元素
  - \<div>
  - \<span>

### 1.8HTML调试

firefox调试技术。

## 2 多媒体

### 2.1 图片

- [\<img\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img)  

```html
<img src="images/dinosaur.jpg">

<img src="images/dinosaur.jpg"
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。">

<img src="images/dinosaur.jpg"  
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341">

<img src="images/dinosaur.jpg"  
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341"
     title="曼彻斯特大学博物馆展出的一只霸王龙的化石。">
```

- \<img\>搭配说明文字

```html
<figure>
  <img src="images/dinosaur.jpg"
    alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
    width="400"
    height="341">
  <figcaption>曼彻斯特大学博物馆展出的一只霸王龙的化石</figcaption>
</figure>
```

- CSS背景图片

```css
p{
  background-image: url("images/dinosaur.jpg");
}
```

### 2.2 音频

- [\<audio\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio)

```html
<audio controls>
  <source src="viper.mp3" type="audio/mp3">
  <source src="viper.ogg" type="audio/ogg">
  <p>你的浏览器不支持 HTML5 音频，可点击<a href="viper.mp3">此链接</a>收听。</p>
</audio>
```

### 2.3 视频

- [\<video\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video)

```html
<video controls width="400" height="400"
       autoplay loop muted
       poster="poster.png"
       preload="auto">
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>你的浏览器不支持 HTML5 视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>
</video>
```

### 2.4 嵌入

- [\<iframe\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

```html
<iframe src="https://player.bilibili.com/player.html?aid=19390801&cid=31621681&page=1"
  scrolling="no" 
  border="0" 
  frameborder="no" 
  framespacing="0" 
  allowfullscreen="true">
</iframe> 
<p>改革春风吹满地</p>
```

- [\<embed\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed)

```html
<embed src="whoosh.swf" quality="medium"
       bgcolor="#ffffff" width="550" height="400"
       name="whoosh" align="middle" allowScriptAccess="sameDomain"
       allowFullScreen="false" type="application/x-shockwave-flash"
       pluginspage="http://www.macromedia.com/go/getflashplayer">
```

- [\<object\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object)

```html
<object data="mypdf.pdf" type="application/pdf"
        width="800" height="1200" typemustmatch>
  <p>You don't have a PDF plugin, but you can <a href="myfile.pdf">download the PDF file.</a></p>
</object>
```

### 2.5 矢量图

在网上，你会和两种类型的图片打交道-位图和矢量图。

- 位图使用像素网络来定义

一个位图文件精确包含每一个像素的位置和色彩信息，流行的格式有bitmap，png，jepg，gif等。

- 矢量图使用算法来定义

一个矢量图文件包含了图形和路径的定义，计算机根据定义计算出当它们在屏幕上渲染时呈现的样子，SVG格式可以让我们创造用于web的矢量图形。

- [\<svg\>](https://developer.mozilla.org/zh-CN/docs/Web/SVG)

```html
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="black" />
  <circle cx="150" cy="100" r="90" fill="blue" />
</svg>
```

```html
  <svg width="100%" height="100%">
    <rect width="100%" height="100%" fill="red" />
    <circle cx="100%" cy="100%" r="150" fill="blue" stroke="black" />
    <polygon points="120,0 240,225 0,225" fill="green"/>
    <text x="50" y="100" font-family="Verdana" font-size="55"
          fill="white" stroke="black" stroke-width="2">
            Hello!
    </text>
  </svg>
```

### 2.6 图片自适应

```html
<img srcset="elva-fairy-320w.jpg 320w,
             elva-fairy-480w.jpg 480w,
             elva-fairy-800w.jpg 800w"
     sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
     src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy">
```

- 查看设备宽度
- 检查sizes列表中那个媒体条件为真
- 查看给与该媒体查询的槽大小
- 加载srcset列表中引用的最接近所选槽大小的图像

## 3 表格

### 3.1 基础表格

- [\<table\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)

- [\<tr\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) table row

- [\<th\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th) table header

- [\<td\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) table data
  - [\<colspan\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td#attr-colspan)
  - [\<rowspan\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td#attr-rowspan)

```html
    <table>
      <colgroup>
        <col span="2">
        <col style="background-color:#97DB9A;">
        <col style="width:42px;">
        <col style="background-color:#97DB9A;">
        <col style="background-color:#DCC48E; border:4px solid #C1437A;">
        <col span="2" style="width:42px;">
      </colgroup>
      <tr>
        <td>&nbsp;</td>
        <th>Mon</th>
        <th>Tues</th>
        <th>Wed</th>
        <th>Thurs</th>
        <th>Fri</th>
        <th>Sat</th>
        <th>Sun</th>
      </tr>
      <tr>
        <th>1st period</th>
        <td>English</td>
        <td>&nbsp;</td>
        <td>&nbsp;</td>
        <td>German</td>
        <td>Dutch</td>
        <td>&nbsp;</td>
        <td>&nbsp;</td>
      </tr>
      <tr>
        <th>2nd period</th>
        <td>English</td>
        <td>English</td>
        <td>&nbsp;</td>
        <td>German</td>
        <td>Dutch</td>
        <td>&nbsp;</td>
        <td>&nbsp;</td>
      </tr>
      <tr>
        <th>3rd period</th>
        <td>&nbsp;</td>
        <td>German</td>
        <td>&nbsp;</td>
        <td>German</td>
        <td>Dutch</td>
        <td>&nbsp;</td>
        <td>&nbsp;</td>
      </tr>
      <tr>
        <th>4th period</th>
        <td>&nbsp;</td>
        <td>English</td>
        <td>&nbsp;</td>
        <td>English</td>
        <td>Dutch</td>
        <td>&nbsp;</td>
        <td>&nbsp;</td>
      </tr>
    </table>
```

### 3.2 高级表格

- [\<caption\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption)

```html
<table>
  <caption>Florence's weekly lesson timetable</caption>
</table>
```

- [\<col\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/col)

- [\<colgroup\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/colgroup)

- [\<thead\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/thead)

- [\<tfoot\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/tfoot)

- [\<tbody\>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)

```html
      <table>
        <caption>How I chose to spend my money</caption>
        <thead>
          <tr>
            <th>Purchase</th>
            <th>Location</th>
            <th>Date</th>
            <th>Evaluation</th>
            <th>Cost (€)</th>
          </tr>
        </thead>
        <tfoot>
          <tr>
            <td colspan="4">SUM</td>
            <td>118</td>
          </tr>
        </tfoot>
        <tbody>
          <tr>
            <td>Haircut</td>
            <td>Hairdresser</td>
            <td>12/09</td>
            <td>Great idea</td>
            <td>30</td>
          </tr>
          <tr>
            <td>Lasagna</td>
            <td>Restaurant</td>
            <td>12/09</td>
            <td>Regrets</td>
            <td>18</td>
          </tr>
          <tr>
            <td>Shoes</td>
            <td>Shoeshop</td>
            <td>13/09</td>
            <td>Big regrets</td>
            <td>65</td>
          </tr>
          <tr>
            <td>Toothpaste</td>
            <td>Supermarket</td>
            <td>13/09</td>
            <td>Good</td>
            <td>5</td>
          </tr>
        </tbody>
    </table>
```

- [\<scope\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th#attr-scope)

```html
<thead>
  <tr>
    <th scope="col">Purchase</th>
    <th scope="col">Location</th>
    <th scope="col">Date</th>
    <th scope="col">Evaluation</th>
    <th scope="col">Cost (€)</th>
  </tr>
</thead>
```

- [\<id\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes#attr-id)和[\<headers\>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td#attr-headers)

```html
<thead>
  <tr>
    <th id="purchase">Purchase</th>
    <th id="location">Location</th>
    <th id="date">Date</th>
    <th id="evaluation">Evaluation</th>
    <th id="cost">Cost (€)</th>
  </tr>
</thead>
<tbody>
<tr>
  <th id="haircut">Haircut</th>
  <td headers="location haircut">Hairdresser</td>
  <td headers="date haircut">12/09</td>
  <td headers="evaluation haircut">Great idea</td>
  <td headers="cost haircut">30</td>
</tr>

  ...

</tbody>
```
