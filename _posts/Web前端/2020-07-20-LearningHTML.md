---
title: HTML5知识提炼
author: JoyDee
categories: [Web前端, HTML与CSS]
tags: [HTML]
date: 2020-07-20 00:40:00 +0800
math: true
---

# HTML 5 知识提炼

笔记大多是我从老师的课堂讲授中记录的，同时参考了W3school提供的资料。当然，笔记主要是记录个人认为**容易遗忘**或者**有价值**的，因此记录时**不一定能够将所有知识点覆盖**，或出现遗漏，术语上不一定标准规范。更加详细的知识点，可以去W3school或一些文档中查阅。待时间充裕，我也会进一步校对与补充。如果能发现其中的错误，望指正。~~大佬轻喷qaq~~

# 一、网页的组成

伯纳斯李建立万维网联盟(W3C)——为了制订网页开发的标准

根据W3C标准，一个网页主要由三部分组成：

+ 结构——HTML：用于描述页面的结构
+ 表现——CSS：用于控制页面中元素的样式
+ 行为——JavaScript：用于响应用户操作

# 二、HTML简介

HTML（` Hypertext Markup Language `） **超文本标记语言**，它使用**标签**的形式来标识网页中的不同组成部分。其中，超文本可以指超链接，使用超链接可以让我们从一个页面跳转到另一个页面。

HTML元素的内容是**开始标签（起始标签）**与**结束标签（闭合标签）**之间的内容。HTML通过标签来标识出网页的不同内容，而标签一般来说是成对出现，如 `<h1>...</h1>`；部分标签没有结束标签，如`<hr>`, `<br>`大多数HTML元素可以嵌套（即HTML元素可包含其他HTML元素）。

```html
<body>
    <p>我是段落</p>
</body>
```

HTML标签列表可以查阅[手册](https://www.runoob.com/tags/ref-byfunc.html)

> HTML**注释标签**为: `<!-- ... -->`

# 三、标签中的属性

属性是键值对（其中，属性值是包括在双(单)引号内的），在标签中(开始标签或自结束标签)设置属性，用于设置标签中的内容如何显示，是HTML元素提供的附加信息

| 属性    |                             描述                             |
| ------- | :----------------------------------------------------------: |
| `class` | 为html元素定义一个或多个类名（classname）(类名从样式文件引入) |
| `id`    |                       定义元素的唯一id                       |
| `style` |              规定元素的行内样式（inline style）              |
| `title` |            描述了元素的额外信息 (作为工具条使用)             |

> 语法格式一般为`<元素 属性 = "属性值">`，部分属性没有属性值

# 四、网页的基本结构

```html
<!--文档声明-->
<!DOCTYPE html>

<!-- html的根标签(元素)-->
<html lang="en">
	<!--网页的头部-->
    <head>
        <meta charset="UTF-8"> <!--此处的meta标签用于设置网页的字符集，避免乱码-->
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>我的博客</title>
    </head>
    <!--网页的主体-->
    <body>

    </body>
</html>
```

> 在$VS\ Code$中直接打出`!`再按一次回车键，能够立即生成网页的基本结构

+ **文档声明(doctype)**：用于向浏览器声明当前网页的版本 ( eg: html5 )，写在`<html>`标签之前。而`<!DOCTYPE html>` 说明是html5的文档声明，一般写在网页最前面(在`<html></html>`之前)。

+ **html标签**：网页中所有内容必须要放在根标签内部

+ **head标签**：定义网页的**头部**，作为文档的信息，head中的内容不会在网页中直接出现，主要用来帮助浏览器或搜索引擎解析网页

+ **meta标签**：用于设置网页的元数据，不显示在页面上，但被浏览器解析。它有多种可选属性：

  + `charset` ：见上文代码

  + `content` ：指定的数据的内容

  + `name` ：指定的数据的名称，它常常需要搭配`content`属性使用，可选值有：

    + `keywords`：表示网站的关键字，可以指定多个关键字，关键字间用`,`隔开

      ```html
      <meta name = "keywords" content = "网上购物, 网上商城">
      ```

    + `description`：用于指定网站的描述，其描述会显示在搜索引擎的搜索结果中

      ```html
      <meta name="description" content="At Microsoft our mission and values are to help people and businesses throughout the world realize their full potential.">
      ```

      ![](https://gitee.com/j__strawhat/MyImages/raw/master/20200816013216.png)

      

  + `http-equiv` ：将页面重定向到另一个网站

+ **title标签**：定义浏览器工具栏的标题，搜索引擎会主要根据title中的内容来判断网页的主要内容。

+ **style标签**：定义了HTML文档的样式文件。

+ **script标签**：用于加载脚本文件，如$JavaScript$

+ **body标签**：定义网页的**主体**，其元素包含文档的所有(可见)内容。

# 五、字符实体

在文档中，有些特殊符号并不能直接书写（多个连续空格、小于/大于号），此时需要实体（转义字符），其基本语法为`&实体名; `。如下：

- `&nbsp;`：表示不间断空格(non-breaking space)
- `&gt;`：表示大于号
- `&lt;`：表示小于号
- `&times;`：表示乘号
- `&quot;`：表示引号

更多实体可以查阅[参考手册](https://www.runoob.com/html/html-entities.html)。

# 六、文本格式化

+ 标题标签：h1~h6共六级标题，属于块元素。

  `<hgroup>`标签能够为标题标签分组，即将一组相关的标题同时放入到hgroup标签中。（**html5**）

+ `<p>`：表示页面中的一个段落，它会**独占一行**，属于块元素。

+ `<em>`：语音语调加重，它的样式也许是斜线样式，属于行内元素；

  `<strong>`：强调重要内容，属于行内元素。

+ `<blockquote>`：表示一个长引用，属于块元素；

  `<q>`：表示短引用，不会独占一行！

+ `<br>`：换行

# 七、区块布局

大多数HTML元素被定义为行内元素或块元素。

> **行内元素**(inline element)（内联元素）：在页面中不会独占一行的元素。
>
> **块元素**(block element)（块级元素）：在页面中独占一行的元素，在网页中一般通过块元素布局，也会将行内元素放到块元素中，但注意`<p>`元素不能放任何块元素。

**而HTML可以通过`<div>`和`span`将元素组合起来。**

> `<div>` ： 布局元素，属于**块内元素**，无具体特定语义，用于**组合**其他HTML的容器，使用频率极为频繁。
>
> `<span>`：用于在网页中选中文字，属于**行内元素**，无具体特定语义，可用作文本的容器。

**[附]：**布局标签(结构化语义标签)

作为html5新增标签，非必需。

- `<header>` 表示网页的头部

- `<main>` 表示网页的主体部分，一个页面只会有一个main

- `<footer>` 表示网页的底部

  `<nav>`表示网页中的导航

- `<aside>` 与主体相关的内容(例如侧边栏)

- `<article>` 表示一个独立的文章

- `<section>` 表示一个独立的区块

# 八、列表

html列表属于块元素，共分三种类型：

- **有序列表**：使用`<ol>`来创建，使用`<li>`表示列表项，几个`<li>`表示共有几个项。

- **无序列表**：使用`<ul>`来创建，使用`<li>`表示列表项，几个`<li>`表示共有几个项。多用于制作网页上的菜单

- **定义列表**：使用`<dl>`来创建，使用`<dt>`表示定义的内容，用`<dd>`来对内容进行解释说明（~~样式上其实就是增加了缩进~~）。虽然使用频率不高，它可用于制作网页上的下拉菜单。

  ```HTML
  <!--定义列表的举例-->
  <dl>
      <dt>群</dt>
      <dd>一个拥有满足封闭性、满足结合律、有单位元、有逆元的二元运算的代数结构。</dd>
  </dl>
  ```

列表之间可以互相嵌套。

 # 九、超链接

超链接可以让我们从一个页面跳转到其他页面，或者是当前页面其他的位置。而HTML中使用`<a>`来定义超链接，属于行内元素，在`<a>`标签可以嵌套除它自身外的任何元素（eg:`<div>`）

`<a>`的常用属性有：

* `href`：指定跳转的目标路径，其属性值既可为外部网站的地址，也能是内部页面的地址。

  + 当需要跳转一个服务器内部的页面时，一般要使用**相对路径**，其格式为：
    + `./`表示**当前文件**所在的目录；
    + `../`表示当前文件所在目录的上一级目录

  ```html
  <a href = "https://www.cnblogs.com/J-StrawHat/"> 点击原文 </a>
  <!--当前网页为now.html，现在我希望访问同一服务器内部的destination网页-->
  <a href = "./inner/destination.html"> 访问destination </a>
  ```

  ![](https://gitee.com/j__strawhat/MyImages/raw/master/20200816190150.png)

  + 另外，可以将`href`属性值设置为"#"，由此点击超链接以后页面不会发生跳转，而是转至当前页面的**顶部位置**

  ```html
  <a href = "#"> 回至顶部 </a>
  ```

  * 还可以将在`a`标签中设置`#id`属性，设置该属性即为跳转到属性为`id`的元素，`id`不能以数字作为开头。同时，除了指定标签为`id`属性以外，同一页面中不能再出现重复的`id`属性值。

    ```html
    <p id = "p3">  2333 </p>
    <a href = "#p3"> 前往第三个自然段 </a> <!--即跳转到"2333"-->
    ```

  * 在开发中，可以为`href`属性设置为`"javascript:;"`，以此作为临时的占位符，不发生什么作用。

* `target`：用于指定超链接打开的位置，其可选属性值有：

  + `"_self"`：默认值，在当前页面中打开超链接，国外网站常用。

  + `"_blank"`：在一个**新的空白页面**中打开超链接，国内常用。
  
   ```html
  <a href = "www.baidu.com" target = "blank"> 点击原文 </a>
   ```

# 十、替换元素

## 图片标签

图片标签用于向当前页面引入一个外部图片，

`<img>`属于替换元素（基于块和行内元素之间），别忘记它是自结束标签，它的属性有：

- `src`：指定的是外部图片的路径。
- `alt`：图片的描述，默认情况下不会显示，有些浏览器无法加载该图片的显示，更重要的是，搜索引擎能根据alt中的内容来识别图片
- `width`和`height`：它的单位为像素。宽度和高度中如果只修改其中一个参数，则另一个参数也会等比例缩放。

## 音视频播放

`<audio>`标签向页面中引入一个外部的音频文件，注意，音视频文件引入时默认不允许用户自己控制播放停止。其属性：

- `controls`: 允许用户控制播放，不需要赋值。
- `autoplay`：音频文件是否自动播放。（兼容性较低，因为一般浏览器都不会对音乐自动进行播放）
- `loop`： 是否循环播放

兼容问题：为了解决兼容问题，可以这样引入音视频文件

```html
<audio controls>
	对不起，您的浏览器不支持播放音频！请升级浏览器 
    <source src = "./source/audio.mp3">
    <source src = "./source/audio.ogg">
</audio>
```

`<video>`标签来向网页中引入一个视频，其属性与`<audio>`基本相同

## 内联框架 (较少使用)

内联框架用于向当前页面中引入另一个页面 

`<iframe>`标签，具有的属性有：


- `src`：指定要引入的网页的路径。
- `width`和`height`
- `frameborder`：指定内联框架的边框，默认情况带有边框（即值为1），若要去掉边框则设置0。



*感谢李立超老师的讲授*