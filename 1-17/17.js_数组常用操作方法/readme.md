JS 数组常用操作方法
---
数组对象是一个有序的数据（数据可以是 原始类型 或 对象类型）集合。相对于变量，数组可用于在一个变量中存储多个变量值。

数组中的每一项都有一个数字附于其上，被称为索引。在JavaScript中，数组索引从0开始，并可以使用多种 方法 操作.。


#### 创建数组

~~~js
var myArray = [1, 2, 3, 4];
var catNamesArray = ["Jacqueline", "Sophia", "Autumn"];
var arr = [myArray, catNamesArray];  //数组嵌套。
//Javascript中的数据可以处理不用类型的数据。
~~~

#### 通过索引访问数组元素

和字符串一样，数组也可以通过索引来访问元素：
~~~js
var zoo = ["monkey", "lion", "elephant", "flamingo"]
console.log(zoo[0]);    //monkey
console.log(zoo[3]);    //flamingo
console.log(zoo[5]);    //undefined
~~~

#### 属性
`Array.length`

    Array 构造函数的 length 属性，其值为1（注意该属性为静态属性，不是数组实例的 length 属性）。
~~~js
var zoo = ["monkey", "lion", "elephant", "flamingo"];
zoo.length;

-> 4
~~~


#### 方法
##### 修改器方法

下面的这些方法会改变调用它们的对象自身的值：

`pop()`方法从数组中删除最后一个元素，并返回该元素的值。此方法更改数组的长度。

~~~js
var arr = [1, 2, 3];
a.length; // 3

a.pop(); // 3

console.log(a); // [1, 2]
a.length; // 2
~~~

`push()` 方法将一个或多个元素添加到数组的末尾，并返回新数组的长度。
~~~js
var numbers = [1, 2, 3];

numbers.push(5, 6, 7);

console.log(numbers); 
// Array [ 1, 2, 3, 5, 6, 7 ]
~~~

`reverse()` 方法将数组中元素的位置颠倒。
~~~js
var numbers = [1, 3, 5, 7, 9];
numbers.reverse();

//Array [ 9, 7, 5, 3, 1 ]
~~~

`shift()` 方法从数组中删除第一个元素，并返回该元素的值。
~~~js
var zoo = ["monkey", "lion", "elephant", "flamingo"];
zoo.shift();             //"monkey"
console.log(zoo);

// Array [ "lion", "elephant", "flamingo" ]
~~~

`unshift()` 方法将一个或多个元素添加到数组的开头，并返回新数组的长度。
~~~js
var zoo = ["monkey", "lion", "elephant", "flamingo"];
zoo.unshift("giraffe");
console.log(zoo);

//Array [ "giraffe", "monkey", "lion", "elephant", "flamingo"]
~~~

`sort()` 方法用就地（ in-place ）的算法对数组的元素进行排序，并返回数组。 sort 排序不一定是稳定的。默认排序顺序是根据字符串Unicode码点。
~~~js
var fruit = ['cherries', 'apples', 'bananas'];
fruit.sort(); 
// ['apples', 'bananas', 'cherries']

var scores = [1, 10, 21, 2]; 
scores.sort(); 
// [1, 10, 2, 21]
// 注意10在2之前,因为在 Unicode 指针顺序中"10"在"2"之前,
//因为"10"会先读取“1”的Unicode码点;

var things = ['word', 'Word', '1 Word', '2 Words'];
things.sort(); 
// ['1 Word', '2 Words', 'Word', 'word']
// 在Unicode中, 数字在大写字母之前,
// 大写字母在小写字母之前.
~~~

`splice()` 方法通过删除现有元素和/或添加新元素来更改一个数组的内容。

		array.splice(start, deleteCount, item1, item2, ...)


`start`

    指定修改的开始位置（从0计数）。如果超出了数组的长度，则从数组末尾开始添加内容；如果是负值，则表示从数组末位开始的第几位（从-1计数）；若只使用start参数而不使用deleteCount、item，如：array.splice(start) ，表示删除[start，end]的元素。


`deleteCount` 可选

    整数，表示要移除的数组元素的个数。如果 deleteCount 是 0，则不移除元素。这种情况下，至少应添加一个新元素。如果 deleteCount 大于start 之后的元素的总数，则从 start 后面的元素都将被删除（含第 start 位）。
    如果deleteCount被省略，则其相当于(arr.length - start)。

`item1, item2, ...` 可选

    要添加进数组的元素,从start 位置开始。如果不指定，则 splice() 将只删除数组元素。

~~~js
var numbers = [1, 2, 3, 4, 5, 6, 7];
numbers.splice(1,2);    
//删除从索引1开始的两个元素，numbers变为Array [ 1, 4, 5, 6, 7 ]

numbers.splice(3, 0, "eight", "ten");
//索引3后添加2个元素numbers变为Array [ 1, 4, 5, "eight", "ten", 6, 7 ]
//如果start 为负数，则添加在该索引前面;
//如果`deleteCount`为2，则会替换掉索引开始的两个元素;
~~~ 


##### 访问方法

下面的这些方法绝对不会改变调用它们的对象的值，只会返回一个新的数组或者返回一个其它的期望值。

`concat()` 方法用于合并两个或多个数组。此方法不会更改现有数组，而是返回一个新数组。

		arrayObject.concat(arrayX,arrayX,......,arrayX)


~~~js
var arr1 = [1, 2, 3];
var arr2 = [4, 5];
arr1.concat(arr2);

=>Array [ 1, 2, 3, 4, 5 ]
~~~


`join()` 方法用于把数组中的所有元素放入一个字符串。指定要使用的分隔符。如果省略该参数，则使用逗号作为分隔符。

		arrayObject.join(separator)

~~~js
var arr1 = [1, 2, 3];
arr1.join();              //"1,2,3"
arr1.join("$");			  //"1$2$3"
~~~


`slice()` 方法返回一个从开始到结束（不包括结束）选择的数组的一部分浅拷贝到一个新数组对象。且原始数组不会被修改。
~~~js
var zoo= ["giraffe", "monkey", "lion", "elephant", "flamingo"];
zoo.slice(1,3);

// return Array [ "monkey", "lion" ]
~~~

`toString()` 返回一个字符串，表示指定的数组及其元素。
~~~js
var arr1 = [1, 2, 3, 4];
arr1.toString();

->"1,2,3,4"
~~~

`toLocaleString()`返回一个由所有数组元素组合而成的本地化后的字符串。
将`toLocaleString()`作用于上面的例子，返回结果是一致的，那么它们的区别是什么呢？
~~~js
var number = 1337;
var date = new Date();
var myArr = [number, date, "foo"];

var str1 = myArr.toLocaleString(); 
console.log(str1); 
// 输出 "1,337,2018/4/16 下午2:13:18,foo"
// 假定运行在中文（zh-CN）环境，北京时区

var str2 = myArr.toString(); 
console.log(str2); 
// 输出 “1337,Mon Apr 16 2018 14:13:18 GMT-0400,foo”
// 根据电脑上设置的时区；
~~~

因为LocaleString()会根据你机器的本地环境来返回字符串,它和toString()返回的值在不同的本地环境下使用的符号会有微妙的变化.

所以使用toString()是保险的,返回唯一值的方法,它不会因为本地环境的改变而发生变化.

如果是为了返回时间类型的数据,推荐使用LocaleString().若是在后台处理字符串,请务必使用toString().

`indexOf()`方法返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1。

		arr.indexOf(searchElement[, fromIndex = 0])

~~~js
var arr = [1, 2, 3, 1];
arr.indexOf(1);                //0
arr.indexOf(1,1);              //3
arr.indexOf(4);				   //-1
~~~

`lastIndexOf()` 方法返回指定元素（也即有效的 JavaScript 值或变量）在数组中的最后一个的索引，如果不存在则返回 -1。从数组的后面向前查找，从 fromIndex 处开始。

		arr.lastIndexOf(searchElement[, fromIndex = arr.length - 1])

~~~js
var arr = [1, 2, 3, 1];
arr.lastIndexOf(1);                //3
arr.lastIndexOf(1,1);              //0
arr.lastIndexOf(4);				   //-1
~~~

##### 迭代方法

`forEach()`为数组中的每个元素执行一次回调函数。
~~~js
var nums = [1, 2, 3, 4];
nums.forEach(element => console.log(element*2 + 1));

//  3
//  5
//	7
//	9
~~~

`every()`如果数组中的每个元素都满足测试函数，则返回 true，否则返回 false。

callback 被调用时传入三个参数：元素值，元素的索引，原数组。

		arr.every(callback[, thisArg])

~~~js
var nums = [1, 2, 3, 4];

nums.every(isBigEnough(2));
// false
nums.every(isBigEnough(0));
// true
~~~

另外，空数组也是返回true。(空数组中所有元素都符合给定的条件，注：因为空数组没有元素)。

`some()`如果数组中至少有一个元素满足测试函数，则返回 true，否则返回 false。
~~~js
function isBigEnough(element, index, array) {
  return (element >= 10);
}
var passed = [2, 5, 8, 1, 4].some(isBigEnough);
// passed is false
passed = [12, 5, 8, 1, 4].some(isBigEnough);
// passed is true
~~~

`filter()`将所有在过滤函数中返回 true 的数组元素放进一个新数组中并返回。
~~~js
function isBigEnough(value) {
  return value >= 10;
}

var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
console.log(filtered);

-> Array [ 12, 130, 44 ]
~~~

`map()`返回一个由回调函数的返回值组成的新数组。
~~~js
var nums = [1, 2, 3, 4];
nums.map(element => element*2 + 1);

->Array [ 3, 5, 7, 9 ]
~~~

`reduce()`从左到右为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。

~~~js
var nums = [3,67,63,7,9,84,7,5];
function compare(a, b){
	if(a>b){
		return a;
	} else {
		return b;
	}
}
nums.reduce(compare);

//找到最大值84
~~~

`reduceRight`右到左为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。

~~~js
var flattened = [[0, 1], [2, 3], [4, 5]].reduceRight(function(a, b) {
    return a.concat(b);
}, []);
console.log(flattened);

// Array [ 4, 5, 2, 3, 0, 1 ]
~~~




[其他实验性方法及尚未标准化方法请见](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)

---
参考：
>https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array
