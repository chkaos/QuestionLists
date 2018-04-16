JS 事件绑定
---

[Jsbin例子](https://jsbin.com/wularu/edit?html,js,console,output)

javascript给DOM绑定事件处理函数总的来说有2种方式：在html文档中绑定、在js代码中绑定,绑定事件监听函数。

#### 一. html文档绑定：

HTML的DOM元素支持onclick、onblur等以on开头属性，我们可以直接在这些属性值中编写javascript代码。当点击div的时候，下面的代码会弹出div的id：

~~~html
<div id="button1" onclick="var id = this.id;alert(id);return false;">DIV1</div>
~~~

事件处理函数中的this代表的是window对象，所以我们在onclick属性值中，通过this将dom对象作为参数传递。

~~~html
<script>
function showAlert() {
    alert("clicked!")
}
</script>
<div id="button2" onclick="showAlert();">DIV2</div>
~~~

当代码比较多的时候，我们可以在onclick等属性中指定函数名。跟上面的做法相比，这种做法略好一些。但是仍然不推荐。

#### 二. js代码中绑定：

在JavaScript代码中绑定事件可以使JavaScript代码与HTML标签分离，文档结构清晰，便于管理和开发。

例如，为 id="button3" 的div元素绑定另一个alert：

~~~html
<script>
document.getElementById("button3").onclick=function(){
    alert("Another Warning.");
}
</script>
<div id="button3" >DIV3</div>
~~~

#### 三. 绑定事件监听函数
绑定事件的另一种方法是用 `addEventListener()` 或 `attachEvent()` 来绑定事件监听函数。

addEventListener()函数语法：

elementObject.addEventListener(eventName,handle,useCapture);

|参数	|说明|
|-----|----|
|elementObject	|DOM对象（即DOM元素）。|
|eventName	|事件名称。注意，这里的事件名称没有“ on ”，如鼠标单击事件 click ，鼠标双击事件doubleclick, 鼠标移入事件 mouseover，鼠标移出事件 mouseout 等。
|handle	|事件句柄函数，即用来处理事件的函数。|
|useCapture	|Boolean类型，是否使用捕获，一般用false。|

attachEvent()函数语法：

elementObject.attachEvent(eventName,handle);

|参数|	说明|
|-----|----|
|elementObject	|DOM对象（即DOM元素）。|
|eventName	|事件名称。注意，与addEventListener()不同，这里的事件名称有“ on ”，如鼠标单击事件|
 |onclick |鼠标双击事件 ondoubleclick ，鼠标移入事件 onmouseover，鼠标移出事件 onmouseout 等。|
|handle|	事件句柄函数，即用来处理事件的函数。|

>Note: 事件句柄函数是指“ 函数名 ”，不能带小括号.

W3C标准的addEventListener和removeEventListener。

这2个函数是W3C标准规定的，FF和Chrome浏览器都支持，IE6/IE7/IE8都不支持这2个函数。不过从IE9开始就支持了这2个标准的API。

attachEvent/detachEvent兼容性不好，IE6~IE10都支持该函数，但是FF和Chrome浏览器都不支持该方法。而且attachEvent/detachEvent不是W3C标准的做法。

<!-- ~~~js
function addEvent(obj,type,handle){
    try{  // Chrome、FireFox、Opera、Safari、IE9.0及其以上版本
        obj.addEventListener(type,handle,false);
    }catch(e){
        try{  // IE8.0及其以下版本
            obj.attachEvent('on' + type,handle);
        }catch(e){  // 早期浏览器
            obj['on' + type] = handle;
        }
    }
}
~~~ -->

我们来写一个例子：
~~~html
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
~~~
~~~js
var lis = document.getElementsByTagName("li");
for (var i=0;i<lis.length;i++){
  lis[i].addEventListener("click", showAlert)
  //   lis[i].attachEvent("onclick", showAlert);
}
~~~
