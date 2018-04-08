JS Var
---

在Javascript程序中，使用一个变量应该事先声明。其中一种声明方式就是使用关键字`var`.

**`variable`语句** 声明了一个变量，可选地将其初始化为一个值。

#### 语法
~~~js
var varname1 [= value1 [, varname2 [, varname3 ... [, varnameN]]]];
~~~

---

变量通过关键字`var`声明；如:
~~~js
var a;    //一个简单的变量；
~~~

也可以通过一个关键字声明多个变量，注意用逗号分隔开：
~~~js
var a, b, c;   //三个变量；
~~~

可以将变量初始赋值和变量声明写在一起：
~~~js
var a=1 , b=2, c=3，d;
~~~

使用`console.log()`输出上述变量的值。我们虽然声明了`d`这个变量但并未赋予初始值，再给它存入一个值之前，它的初始值就是`undefined`.
~~~js
console.log(a,b,c,d);
1 2 3 undefined
~~~

Javascript是典型的动态语言，它的变量可以是任意数据类型。例如，我们可以先将一个数字赋予一个变量，随后再将文本赋值给这个变量；
~~~js
var i = 8;
i = "eight";
~~~

---

#### 变量作用域

上述例子声明的变量都是全局变量，在整个Javascript程序里都是可见的。如果`var`语句出现在函数体内，那么它声明的就是局部变量。
~~~js
var scope = "global";    //声明一个全局变量；
function checkScope() {
    var scope = "local"; //声明一个同名的局部变量；
    return scope;        //返回局部变量scope；
}
checkScope();
~~~
Output:
~~~
"local"
~~~
>这里函数checkScope()返回的是局部变量的值，如果在函数的作用域里没有找到该变量，它会继续往外层找到全局变量scope.此时返回的值应该是`"global"`.

全局变量的声明可以不使用关键词`var`,但是局部变量则不可以，否则会赋值到同名的全局变量造成混乱。
~~~js
scope = "global";    //声明一个全局变量；
function checkScope2() {
    scope = "local";
    return scope;
}
checkScope2();       //"local"
scope                //"local" 全局变量被修改；
~~~

#### 变量提升

由于变量声明（以及其他声明）总是在任意代码执行之前处理的，所以在代码中的任意位置声明变量总是等效于在代码开头声明。这意味着变量可以在声明之前使用，这个行为叫做“hoisting”。“hoisting”就像是把所有的变量声明移动到函数或者全局代码的开头位置。

~~~js
scope = "global";    //声明一个全局变量；
function doSomething() {
    console.log(scope);
    var scope = "local";
    console.log(scope);
}
doSomething();       
//undefined
//local
~~~
>你可能误以为函数第一行会输出"global"，因为函数还未执行到变量声明的那一行。其实不是，由于函数作用域的特性，局部变量在整个函数体内是有定义的，也就是说在函数体内局部变量涵盖了同名全剧变量。尽管如此，只有在整个函数体执行到var语句的时候，局部变量才会被赋值。因此，上述过程中等同于将函数内的变量声明`var scope`"提升"至函数体顶部,同时变量初始化留在原来的位置。

#### 声明和未声明变量的区别

1.声明变量的作用域限制在其声明位置的上下文中，而非声明变量总是全局的。
~~~js
function x() {
  y = 1;   // 在严格模式（strict mode）下会抛出ReferenceError异常。
  var z = 2;
}
x();
~~~
~~~
console.log(y); // 打印"1" 。
console.log(z); // 抛出ReferenceError: z未在x外部声明。
~~~

2.声明变量在任何代码执行前创建，而非声明变量只有在执行赋值操作的时候才会被创建。
~~~
console.log(a);                // 抛出ReferenceError(a is not defined)
console.log('still going...'); // 永不执行。
var a;
console.log(a);                // 打印"undefined"或""（不同浏览器实现不同）。
console.log('still going...'); // 打印"still going..."。
~~~

3.当声明一个Javascript全局变量时，实际上是定义了全局对象的一个属性。当使用`var`语句声明一个变量时，它是不可配置的。而非声明变量是可配置的（非声明变量可以被删除）。
~~~
var a = 1;
b = 2;
delete this.a; // 在严格模式（strict mode）下抛出TypeError，其他情况下执行失败并无任何提示。
delete this.b;
console.log(a, b);
// 抛出ReferenceError。(b is not defined.)
// 'b'属性已经被删除。
~~~

Note：由于这三个差异，未能声明变量将很可能导致意想不到的结果。因此，建议始终声明变量，无论它们是在函数还是全局作用域内。 而在 ECMAScript 5 严格模式下，分配给未声明的变量会引发错误。

---

参考：
>Javascript权威指南 3.9变量声明/5.3声明语句  

>https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var
