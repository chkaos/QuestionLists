IIFE
---

`IIFE（ 立即调用函数表达式）`是一个在定义时就会立即执行的  JavaScript 函数。

这是一个被称为 自执行匿名函数 的设计模式，主要包含两部分。第一部分是包围在 圆括号运算符() 里的一个匿名函数，这个匿名函数拥有独立的词法作用域。这不仅避免了外界访问此 IIFE 中的变量，而且又不会污染全局作用域。

第二部分再一次使用 () 创建了一个立即执行函数表达式，JavaScript 引擎到此将直接执行函数。

示例
当函数变成立即执行的函数表达式时，表达式中的变量不能从外部访问。
~~~js
(function () {
    var name = "Barry";
})();
// 外部不能访问变量 name
name // undefined
~~~
将 IIFE 分配给一个变量，不是存储 IIFE 本身，而是存储 IIFE 执行后返回的结果。
~~~js
var result = (function () {
    var name = "Barry";
    return name;
})();
// IIFE 执行后返回的结果：
result; // "Barry"
~~~

IIFE好处：

* 自执行匿名函数最大的好处 : 避免了全局作用域的污染

* JavaScript 中函数被用来划分变量作用域
故自执行匿名函数可以控制变量的作用域, 阻止变量泄露到代码中的其他地方。
因此它不会向全局名字空间添加任何变量（通过 var 定义的变量）, 这样也就避免了污染全局作用域;

* 自执行匿名函数的这个好处对于创建 JavaScript 插件帮助巨大;
因为作为一个好的 JavaScript 插件来说, 最大的问题就是避免污染了应用代码, 保持独立性.

---
参考：
>https://www.zybuluo.com/mwumli/note/326520

>https://developer.mozilla.org/zh-CN/docs/Glossary/%E7%AB%8B%E5%8D%B3%E6%89%A7%E8%A1%8C%E5%87%BD%E6%95%B0%E8%A1%A8%E8%BE%BE%E5%BC%8F
