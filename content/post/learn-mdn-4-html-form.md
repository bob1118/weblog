---
title: "Mdn Html Form"
date: 2021-06-23T10:43:28+08:00
lastmod: 2021-06-23T10:43:28+08:00
draft: true
keywords: [html]
description: "learn mdn html form"
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
# 4 FORM

## 4.1 Web表单核心

### 4.1.1 表单概述

### 4.1.2 第一个表单

#### 4.1.2.1 表单定义

- HTML Form 是用户和web站点交互的主要内容之一。
- 表单由一个或多个小部件组成，类似其他语言的可视化控件。

#### 4.1.2.2 设计表单

构建一个简单的联系人表单。  
![form](https://media.prod.mdn.mozit.cloud/attachments/2013/01/15/4579/4e332c8c2a22f459b786ce12c5071d73/form-sketch-low.jpg)

#### 4.1.2.3 实现表单

为了实现上述表单，需要使用以下HTML element

- [\<form>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)
- [\<label>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)
- [\<input>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)
- [\<textarea>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)
- [\<button>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)

#### 4.1.2.4 基本表单样式

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <title>Your first HTML form</title>
    <style>
        form {
            /* 居中表单 */
            margin: 0 auto;
            width: 400px;
            /* 显示表单的轮廓 */
            padding: 1em;
            border: 1px solid #CCC;
            border-radius: 1em;
        }

        ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        form li+li {
            margin-top: 1em;
        }

        label {
            /* 确保所有label大小相同并正确对齐 */
            display: inline-block;
            width: 90px;
            text-align: right;
        }

        input,
        textarea {
            /* 确保所有文本输入框字体相同
     textarea默认是等宽字体 */
            font: 1em sans-serif;

            /* 使所有文本输入框大小相同 */
            width: 300px;
            box-sizing: border-box;

            /* 调整文本输入框的边框样式 */
            border: 1px solid #999;
        }

        input:focus,
        textarea:focus {
            /* 给激活的元素一点高亮效果 */
            border-color: #000;
        }

        textarea {
            /* 使多行文本输入框和它们的label正确对齐 */
            vertical-align: top;

            /* 给文本留下足够的空间 */
            height: 5em;
        }

        .button {
            /* 把按钮放到和文本输入框一样的位置 */
            padding-left: 90px;
            /* 和label的大小一样 */
        }

        button {
            /* 这个外边距的大小与label和文本输入框之间的间距差不多 */
            margin-left: .5em;
        }
    </style>
</head>

<body>
    <form action="/my-handling-form-page" method="post">
        <ul>
            <li>
                <label for="name">Name:</label>
                <input type="text" id="name" name="user_name" />
            </li>
            <li>
                <label for="mail">E-mail:</label>
                <input type="email" id="mail" name="user_mail" />
            </li>
            <li>
                <label for="msg">Message:</label>
                <textarea id="msg" name="user_message"></textarea>
            </li>
            <li class="button">
                <button type="submit">Send your message</button>
            </li>
        </ul>
    </form>
</body>

</html>
```

#### 4.1.2.5 发送数据

- action
- method

### 4.1.3 构造表单

- [\<form>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)
- [fieldset](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)
- [label](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>Payment form example</title>
    <style>
        h1 {
            margin-top: 0;
        }

        ul {
            margin: 0;
            padding: 0;
            list-style: none;
        }

        form {
            margin: 0 auto;
            width: 400px;
            padding: 1em;
            border: 1px solid #CCC;
            border-radius: 1em;
        }

        div+div {
            margin-top: 1em;
        }

        label span {
            display: inline-block;
            width: 120px;
            text-align: right;
        }

        input,
        textarea {
            font: 1em sans-serif;
            width: 250px;
            box-sizing: border-box;
            border: 1px solid #999;
        }

        input[type=checkbox],
        input[type=radio] {
            width: auto;
            border: none;
        }

        input:focus,
        textarea:focus {
            border-color: #000;
        }

        textarea {
            vertical-align: top;
            height: 5em;
            resize: vertical;
        }

        fieldset {
            width: 250px;
            box-sizing: border-box;
            margin-left: 136px;
            border: 1px solid #999;
        }

        button {
            margin: 20px 0 0 124px;
        }

        label {
            position: relative;
        }

        label em {
            position: absolute;
            right: 5px;
            top: 20px;
        }
    </style>
</head>

<body>
    <form method="post">
        <h1>Payment form</h1>
        <p>Required fields are followed by <strong><abbr title="required">*</abbr></strong>.</p>
        <section>
            <h2>Contact information</h2>
            <fieldset>
                <legend>Title</legend>
                <ul>
                    <li>
                        <label for="title_1">
                            <input type="radio" id="title_1" name="title" value="A">
                            Ace
                        </label>
                    </li>
                    <li>
                        <label for="title_2">
                            <input type="radio" id="title_2" name="title" value="K">
                            King
                        </label>
                    </li>
                    <li>
                        <label for="title_3">
                            <input type="radio" id="title_3" name="title" value="Q">
                            Queen
                        </label>
                    </li>
                </ul>
            </fieldset>
            <p>
                <label for="name">
                    <span>Name: </span>
                    <strong><abbr title="required">*</abbr></strong>
                </label>
                <input type="text" id="name" name="username">
            </p>
            <p>
                <label for="mail">
                    <span>E-mail: </span>
                    <strong><abbr title="required">*</abbr></strong>
                </label>
                <input type="email" id="mail" name="usermail">
            </p>
            <p>
                <label for="pwd">
                    <span>Password: </span>
                    <strong><abbr title="required">*</abbr></strong>
                </label>
                <input type="password" id="pwd" name="password">
            </p>
        </section>
        <section>
            <h2>Payment information</h2>
            <p>
                <label for="card">
                    <span>Card type:</span>
                </label>
                <select id="card" name="usercard">
                    <option value="visa">Visa</option>
                    <option value="mc">Mastercard</option>
                    <option value="amex">American Express</option>
                </select>
            </p>
            <p>
                <label for="number">
                    <span>Card number:</span>
                    <strong><abbr title="required">*</abbr></strong>
                </label>
                <input type="tel" id="number" name="cardnumber">
            </p>
            <p>
                <label for="date">
                    <span>Expiration date:</span>
                    <strong><abbr title="required">*</abbr></strong>
                    <em>formatted as mm/dd/yyyy</em>
                </label>
                <input type="date" id="date" name="expiration">
            </p>
        </section>
        <section>
            <p> <button type="submit">Validate the payment</button> </p>
        </section>
    </form>
</body>

</html>
```

### 4.1.4 表单控件

#### 4.1.4.1 通用属性

- autofocus(false) 文档中只有一个与表单相关的元素可以指定具有输入焦点。
- disabled(false) 用户不能与元素交互。
- form
- name
- value

#### 4.1.4.2 文本输入

<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input>

- 通用属性
  - readonly
  - placeholder
  - size
- 单行文本框
`<input type="text" id="comment" name="comment" value="I'm a text field">`
  - Email地址框
  `<input type="email" id="email" name="email" multiple>`
  - 密码框
  `<input type="password" id="pswd" name="pswd">`
  - 搜索框
  `<input type="search" id="search" name="search">`
  - 电话号码
  `<input type="tel" id="tel" name="tel">`
  - URL
  `<input type="url" id="url" name="url">`
- 多行文本框
`<textarea cols="30" rows="10"></textarea>`
  - cols
  - rows
  - wrap

#### 4.1.4.3 下拉内容

<https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select>

- 单选择框

```html
<select id="groups" name="groups">
  <optgroup label="fruits">
    <option>Banana</option>
    <option selected>Cherry</option>
    <option>Lemon</option>
  </optgroup>
  <optgroup label= "vagetables">
    <option>Carrot</option>
    <option>Eggplant</option>
    <option>Potato</option>
  </optgroup>
</select>
```

- 多选择框

```html
<select multiple id="multi" name="multi">
  <option>Banana</option>
  <option>Cherry</option>
  <option>Lemon</option>
</select>
```

- 自动补全输入框

```html
<label for="myFruit">What's your favorite fruit?</label>
<input type="text" name="myFruit" id="myFruit" list="mySuggestion">
<datalist id="mySuggestion">
  <option>Apple</option>
  <option>Banana</option>
  <option>Blackberry</option>
  <option>Blueberry</option>
  <option>Lemon</option>
  <option>Lychee</option>
  <option>Peach</option>
  <option>Pear</option>
</datalist>
```

#### 4.1.4.4 可选中项

- 单选
`<input type="radio" checked id="soup" name="meal">`

- 复选
`<input type="checkbox" checked id="carrots" name="carrots" value="carrots">`

#### 4.1.4.5 按钮

- Submit
- Reset
- Anonymous

#### 4.1.4.6 高级表单部件

- 数字
`<input type="number" name="age" id="age" min="1" max="10" step="2">`

-滑块
`<input type="range" name="beans" id="beans" min="0" max="500" step="10">`

- 日期时间

  - 本地时间`<input type="datetime-local" name="datetime" id="datetime">`
  - 月`<input type="month" name="month" id="month">`
  - 时间`<input type="time" name="time" id="time">`
  - 星期`<input type="week" name="week" id="week">`
- 拾色器
`<input type="color" name="color" id="color">`

#### 4.1.4.7 其他小部件

- 文件选择器
`<input type="file" name="file" id="file" accept="image/*" multiple>`
- 隐藏内容
`<input type="hidden" id="timestamp" name="timestamp" value="1286705410">`
- 图像按钮
`<input type="image" alt="Click me!" src="my-img.png" width="80" height="30" />`
- 仪表和进度条
  - 进度条
  `<progress max="100" value="75">75/100</progress>`
  - 仪表
  `<meter min="0" max="100" value="75" low="33" high="66" optimum="50">75</meter>`

### 4.1.5 HTML5的表单

### 4.1.6 其他表单

### 4.1.7 样式化表单

#### 4.1.7.1 基本样式美化

- Search字段

```css
input[type=search]{
    border: 1px dotted #999;
    border-radius: 0;
    -webkit-appearance: none;
}
```

```html
<form>
    <input type="search">
</form>
```

- 字体和文本

```css
button, input, select, textarea{
    font-family: inherit;
    font-size: 100%;
}
```

- 盒子模型

```css
button, input, select, textarea{
    width: 150px;
    margin: 0;

    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```

- 定位
  - legend
  - textarea

```html
<style>
    legend {
        width: 1px;
        height: 1px;
        overflow: hidden;
    }
</style>

<fieldset>
    <legend>hi</legend>
    <h1>hello</h1>
</fieldset>
```

```css
textarea {
    vertical-align: top;
    }
```

#### 4.1.7.2 实际案例

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>Postcard example</title>
    <style>
        @font-face {
            font-family: 'handwriting';
            src: url('fonts/journal-webfont.woff2') format('woff2'),
                url('fonts/journal-webfont.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }

        @font-face {
            font-family: 'typewriter';
            src: url('fonts/veteran_typewriter-webfont.woff2') format('woff2'),
                url('fonts/veteran_typewriter-webfont.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }

        body {
            font: 1.3rem sans-serif;
            padding: 0.5em;
            margin: 0;
            background: #222;
        }

        form {
            position: relative;
            width: 740px;
            height: 498px;
            margin: 0 auto;
            padding: 1em;
            box-sizing: border-box;
            background: #FFF url(background.jpg);

            /* we create our grid */
            display: grid;
            grid-gap: 20px;
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: 10em 1em 1em 1em;
        }

        h1 {
            font: 1em "typewriter", monospace;
            align-self: end;
        }

        #message {
            grid-row: 1 / 5;
        }

        #from,
        #reply {
            display: flex;
        }

        label {
            font: .8em "typewriter", sans-serif;
        }

        input,
        textarea {
            font: 1.4em/1.5em "handwriting", cursive, sans-serif;
            border: none;
            padding: 0 10px;
            margin: 0;
            width: 80%;
            background: none;
        }

        input:focus,
        textarea:focus {
            background: rgba(0, 0, 0, .1);
            border-radius: 5px;
        }

        textarea {
            display: block;

            padding: 10px;
            margin: 10px 0 0 -10px;
            width: 100%;
            height: 90%;

            border-right: 1px solid;

            /* resize  : none; */
            overflow: auto;
        }

        button {
            padding: 5px;
            font: bold .6em sans-serif;
            border: 2px solid #333;
            border-radius: 5px;
            background: none;
            cursor: pointer;
            transform: rotate(-1.5deg);
        }

        button:after {
            content: " >>>";
        }

        button:hover,
        button:focus {
            outline: none;
            background: #000;
            color: #FFF;
        }
    </style>
</head>

<body>

    <form>
        <h1>to: Mozilla</h1>

        <div id="from">
            <label for="name">from:</label>
            <input type="text" id="name" name="user_name">
        </div>

        <div id="reply">
            <label for="mail">reply:</label>
            <input type="email" id="mail" name="user_email">
        </div>

        <div id="message">
            <label for="msg">Your message:</label>
            <textarea id="msg" name="user_message"></textarea>
        </div>

        <div class="button">
            <button type="submit">Send your message</button>
        </div>
    </form>

</body>

</html>
```

### 4.1.8 高级样式表单

#### 4.1.8.1 CSS表现力

- CSS 2.1
  - :active
  - :focus
  - :hover
- CSS Selector Level 3
  - :enabled
  - :disabled
  - :checked
  - :indeterminate
- CSS Basic UI Level 3
  - :default
  - :valid
  - :invalid
  - :in-range
  - :out-of-range
  - :required
  - :optional
  - :read-only
  - :read-write
- CSS Selector Level 4
  - :user-error

- Mozilla CSS
  - :-moz-placeholder
  - :-moz-submit-invalid
  - :-moz-ui-invalid
  - :-moz-ui-valid
- WebKit CSS
  - ::-webkit-input-placeholder
  - others
- Microsoft CSS
  - :-ms-input-placeholder

#### 4.1.8.2 案例

- 复选框和单选框

### 4.1.9 UI伪类

### 4.1.10 客户端表单验证

#### 4.1.10.1 什么是表单数据校验

- 客户端校验
  - HTML5内置校验
  - JavaScript校验
- 服务器端校验

#### 4.1.10.2 HTML5内置表单校验

- Input元素的校校验
- Input元素required属性
- 正则表达式校验
- 限制输入长度maxlength/minlength
- 自定义错误信息(javascript)

#### 4.1.10.3 JavaScript校验表单

- 支持约束校验API的表单元素
  - [HTMLButtonElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
  - [HTMLFieldSetElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
  - [HTMLInputElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  - [HTMLOutputElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
  - [HTMLSelectElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
  - [HTMLTextAreaElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)
- 约束校验API的属性
  - validationMessage
  - validity
  - validity.customError
  - validity.patternMismatch
  - validity.rageOverflow
  - validity.rageUnderflow
  - validity.stepMismatch
  - validity.tooLong
  - validity.typeMismatch
  - validity.valid
  - validity.valueMissing
  - willValidate
- 约束校验API的方法
  - checkValidity()
  - HTMLFormElement.reportValidity()
  - setCustomValidity(message)
- 使用约束校验API的例子

### 4.1.11 发送表单数据

<https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data>

#### 4.1.11.1 数据都去那儿了

- 客户端/服务器体系结构
- 客户端定义如何发送数据
  - action="http://example.com/action"
  - method
    - GET([get-method.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/get-method.html))
    - POST([post-method.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/post-method.html))
  - 浏览器里查看HTTP请求
- 服务端如何检索数据
  - PHP([php-example.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/php-example.html))
  - Python([python-example.py](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/python-example.py))
  - 其他语言和框架
    - Django for Python
    - Express for Node.js
    - Laravel for PHP
    - Ruby On Rails for Ruby
    - Phoenix for Elixir

#### 4.1.11.2 发送文件

- method get
- enctype multipart/form-data

#### 4.1.11.3 安全问题

- XSS CSRF

- SQL 注入

- HTPP数据头注入

- 电子邮件注入

## 4.2 Web表单进阶

### 4.2.1 构造自定义表单控件

### 4.2.2 使用Javascript发送表单

### 4.2.3 表单组件兼容性列表
