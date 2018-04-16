`new` 运算符
---

`new` 运算符创建一个用户定义的对象类型的实例或具有构造函数的内置对象的实例。

##### 语法
~~~
new constructor[([arguments])]
~~~
##### 参数

`constructor`

一个指定对象实例的类型的类或函数。

`arguments`

一个用来被constructor 调用的参数列表。

Example:

假设你要创建一个人的对象类型。你希望这个类型叫做Person 它有name, age, sex等属性，要做到这些，你需要写这样一个函数：
~~~js
function Person(name, age, sex){
   this.name = name;
   this.age = age;
   this.sex = sex;
}
~~~
实例化一个person对象：
~~~js
var person1 = new Person("Aaron Copland", "30","M");
~~~
这段代码创建了 person1 并给他的属性指定值，于是 person1.name 的值为"Aaron Copland"， person1.age 的值为30，以此类推。

你可以通过调用 `new` 来创建任意个person对象。例如：
~~~js
var person2 = new Person("Clara Dylan", "26","F");
~~~

对象属性也可以是其他对象，假如你想在person类型新增一个spouse属性(其他person对象)，
~~~js
function Person(name, age, sex，spouse){
   this.name = name;
   this.age = age;
   this.sex = sex;
   this.spouse = spouse;
}
~~~
又刚好上面的两个对象恰好是配偶，创建对象时，并没有传字符串或数字给spouse，而是传了对象 person2。这个时候，你可以这样来获取 person2 的spouse的name：
~~~js
var person1 = new Person("Aaron Copland", "30","M", person2);
console.log(person1.spouse.name);
//"Clara Dylan"
~~~

[Jsbin例子使用的是类声明](https://jsbin.com/bufikex/edit?html,js,console,output)

---

参考：

>https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/new
