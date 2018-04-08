HTML5
---
**HTML5** 是HTML 标准的最新演进版本。

它是一个新的HTML语言版本包含了新的元素，属性和行为，同时包含了一系列可以被用来让 Web 站点和应用更加多样化，功能更强大的技术。
尽管HTML5 代表的是HTML 进化革命里的一大步。它向后兼容的能力意味着只要你适应HTML4， 你就可以适应 HTML5绝大多数新特性。
你要知道HTML5不仅是设计取代 HTML4的，还有XHTML1 和DOM level 2 HTML。


#### HTML4 和 HTML5 的主要区别
##### 1 语法
HTML5的 doctype非常简单。表明你的HTML内容使用 HTML5，只需要简单的使用：

	<!DOCTYPE HTML>

在以前版本的HTML声明使用的字符集，它是一个非常复杂的<meta>元素，现在它变得非常简单：

	<meta charset="UTF-8">

比以前更短，更简单，更容易记住并且减少必须下载的字节数。

MathML和SVG分别使得数学公式和矢量图像格式可以直接嵌入到HTML中。


##### 2 新元素

新的语义元素``<mark>``,``<figure>``, ``<figcaption>``, ``<data>``, ``<time>``, ``<output>``, ``<progress>``， ``<meter>``；

新的外观概要和节段元素: ``<section>``, ``<article>``, 	``<nav>``, ``<header>``, ``<footer>``, ``<aside>``, ``<hgroup>``；
能让你更精确地阐述你的内容。

还有其他新属性用于拓展现存元素的功能。

##### 3 HTML5 表单
HTML5 拥有多个新的表单输入类型，包括email，url, number, Date pickers, color 等。
HTML5中的表单元素和属性提供了比HTML4更多的语义标记，并取消了大量的在HTML4不可缺少的脚本和样式。HTML5中的表单功能为用户提供了更好的体验，使表单在不同网站之间更一致，并向用户提供有关数据输入的即时反馈。

##### 4 元素内容模型
HTML4将元素分为块级元素和行内元素, 不仅容易让人迷惑，还和CSS display属性中的同名术语一起容易造成混淆。
HTML5 细分了元素内容模型，光主内容类就分成了元数据内容（Metadata content), 流式元素（Flow content），章节元素（Sectioning content）,标题元素（Heading contect）, 短语元素（Phrasing content）,嵌入元素（Embedded content），交互元素（Interactive content），表单相关内容（Form-associated content）。
每个HTML元素都属于0个、1 个或多个内容模型，每个模型都有一些规则使得元素中的内容必须遵循一个HTML规范文档。

##### 5 新APIs
新APIs使得网络应用程序可以适用于不同设备和用户代理。
``<audio>`` 和 ``<video>`` 元素嵌入并支持新的多媒体内容的操作；
``<canvas>``元素可被用来通过脚本（通常是JavaScript）绘制图形。比如,它可以被用来绘制图形,制作图片集合,甚至用来实现动画效果。
应用缓存，在线离线事件，客户端会话和持久化存储等促进网络应用程序的储存和离线能力。

Drag and Drop API 能够支持在网站内部和网站之间拖放项目。同时也提供了一个更简单的供扩展和基于 Mozilla 的应用程序使用的 API。

Web Workers 能够把 JavaScript 计算委托给后台线程，通过允许这些活动以防止使交互型事件变得缓慢。Web Sockets允许在页面和服务器之间建立持久连接并通过这种方法来交换非 HTML 数据。

以上是 HTML5和 HTML4的主要几项区别。


---

HTML5代码的特征
---
#### 1.简洁的代码

不仅有新的doctype，字符串声明， HTML 5 还包含一系列新的予以元素像``<header>``,``<footer>``, ``<article>`` 和 ``<section>``，让我们清晰理解网页结构。 去除了先前版本多余的标签，使得代码更加优雅简洁并且标准化。

#### 2.兼容性

网页内容日渐多元化，人们将动画，视频流，音乐，社交网络应用整合到网站来放它们的交互性。 HTML 5的到来使得这一切触手可得。

#### 3.全新的表单
HTML5中的表单元素和属性提供了比HTML4更多的语义标记，并取消了大量的在HTML4不可缺少的脚本和样式。HTML5中的表单功能为用户提供了更好的体验，使表单在不同网站之间更一致，并向用户提供有关数据输入的即时反馈。它们还为使用禁用脚本的浏览器的用户提供相同的用户体验。

#### 4.离线浏览

火狐全面支持 HTML5 离线资源规范，WHATWG 在线和离线事件，这可以让应用程序和扩展检测是否存在可用的网络连接，以及在连接建立和断开时能感知到。保证了当无网络情况下重新加载网页时，页面能在第一时间显示出来

#### 5.内置地理API
HTML 5 包含几种地理 APIs. 与HTML 5兼容的浏览器可以使用地理位置服务定位用户的位置。

####  6.客户端数据库
 HTML 5户端会话和持久化存储让 web 应用程序能够在客户端存储结构化数据。这减少缓存的大小并提升网页的反应速度。

---

参考资料：

http://www.acewebacademy.com/blog/top-10-most-important-features-of-html5/
https://code.tutsplus.com/tutorials/28-html5-features-tips-and-techniques-you-must-know--net-13520
https://www.youtube.com/watch?v=9MzAzLHmaRs
https://www.w3.org/TR/html5-diff/
https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML
http://www.w3school.com.cn/html5/html_5_intro.asp
