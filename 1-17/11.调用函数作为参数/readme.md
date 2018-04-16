往函数内传另一个函数
---

[Jsbin](https://jsbin.com/qifomen/edit?js,console)

Example:
~~~Js
var nums = [1, 2, 3, 4];

function convert(num) {
    var output = (num * 2) + 1;
    console.log(output); 
}

nums.forEach(convert);
~~~

Output:
~~~
3
5
7
9
~~~

首先，我们创建一个只包含数字的数组对象。用数组的方法`forEach()`来遍历整个数组，将另一个函数作为参数对每个元素进行转换。
