CSS 盒模型
----
[JSbin链接](https://jsbin.com/robaruz/edit?html,css,output)

**Box Model** 是网页布局的基础 ——每个元素被表示为一个矩形的方框，框的内容、内边距、边界和外边距像洋葱的膜那样，一层包着一层构建起来。浏览器渲染网页布局时，它会算出每个框的内容要用什么样式，周围的洋葱层有多大，以及框相对于其它框放在哪里。

![](/raw/images/box.png)

**width** 和 **height** 设置内容框（content box）的宽度和高度。内容框是框内容显示的区域——包括框内的文本内容，以及表示嵌套子元素的其它框。

---

**每个盒模型都拥有3种属性来设置它的外观**：



**padding** 表示一个 CSS 框的内边距 ——这一层位于内容框的外边缘与边界的内边缘之间。该层的大小可以通过简写属性padding 一次设置所有四个边，或用 `padding-top`、`padding-right`、`padding-bottom` 和 `padding-left` 属性一次设置一个边。

**border** 表示CSS 框的边界，是一个分隔层，位于内边距的外边缘以及外边距的内边缘之间。边界的默认大小为0——从而让它不可见——不过我们可以设置边界的厚度、风格和颜色让它出现。 border 简写属性可以让我们一次设置所有四个边，例如  `border: 1px solid black`; 但这个简写可以被各种普通书写的更详细的属性所覆盖：
  >  `border-top`, `border-right`, `border-bottom`, `border-left`: 分别设置某一边的边界厚度／风格／颜色。

  >`border-width`, `border-style`, `border-color`: 分别仅设置边界的厚度／风格／颜色，并应用到全部四边边界。

  >你也可以单独设置某一个边的三个不同属性，如 `border-top-width`, `border-top-style`, `border-top-color`。


**margin** 代表 CSS 框周围的外部区域，称为外边距，它在布局中推开其它 CSS 框。其表现与 padding 很相似；简写属性为 margin，单个属性分别为 `margin-top`、`margin-right`、`margin-bottom` 和 `margin-left`。


Note:

外边距有一个特别的行为被称作**外边距塌陷（margin collapsing）** ：当两个框彼此接触时，它们的间距将取两个相邻外边界的最大值，而非两者的总和。

~~~html
<div><p id=box1>box1</p></div>
<div><p id=box2>box2</p></div>
~~~
~~~css
p#box1 {
    width: 100px;
    height: 50px;
    background: orange;
    margin-bottom: 50px;
}  
p#box2 {
    width: 100px;
    height: 50px;
    background: purple;
    margin-top: 10px;
}
~~~
![code1](/1-17/5. css的box model及jsbin例子/raw/images/code1.png)

>可以看出两个元素之间的距离为他们本身的height 50px,因为BOX1的下外边距50px为在二者中较大。


外边距可以接受负数，这可以用来引起元素框的重叠。
~~~css
p#box1 {
    width: 100px;
    height: 50px;
    background: orange;
    margin-bottom: 50px;
    opacity: 0.8;
}   
p#box2 {
    width: 100px;
    height: 50px;
    background: purple;
    margin-top: -60px;
    }
~~~
![code2](/1-17/5. css的box model及jsbin例子/raw/images/code2.png)

> 把BOX2的   margin-top改为-60px并给Box1加点透明度，此时可以看到两个元素部分重叠。

其他：100px数字与单位之间不能有空格！




---
参考：

  [https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Box_model](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Box_model)

  HTML And CSS - Design and Build Websites - Charpter 13 Boxes
