# 任务二：零基础JavaScript编码（二）

####任务目的
+ 在上一任务基础上继续JavaScript的体验
+ 学习JavaScript中的if判断语法，for循环语法
+ 学习JavaScript中的数组对象
+ 学习如何读取、处理数据，并动态创建、修改DOM中的内容

####任务描述

参考以下示例代码，页面加载后，将提供的空气质量数据数组，按照某种逻辑（比如空气质量大于60）进行过滤筛选，最后将符合条件的数据按照一定的格式要求显示在网页上
```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>IFE JavaScript Task 01</title>
  </head>
<body>

  <h3>污染城市列表</h3>
  <ul id="aqi-list">
<!--   
    <li>第一名：福州（样例），10</li>
      <li>第二名：福州（样例），10</li> -->
  </ul>

<script type="text/javascript">

var aqiData = [
  ["北京", 90],
  ["上海", 50],
  ["福州", 10],
  ["广州", 50],
  ["成都", 90],
  ["西安", 100]
];

(function () {

  /*
  在注释下方编写代码
  遍历读取aqiData中各个城市的数据
  将空气质量指数大于60的城市显示到aqi-list的列表中
  */

})();

</script>
</body>
</html>
```

####任务注意事项

+ 实现简单功能的同时，请仔细学习JavaScript基本语法、事件、DOM相关的知识
+ 请注意代码风格的整齐、优雅
+ 代码中含有必要的注释
+ 其中的数据以及60的判断逻辑可以自行设定
+ 建议不使用任何第三方库、框架
+ 示例代码仅为示例，可以直接使用，也可以完全自己重写

####在线学习参考资料

+ [JavaScript入门篇](http://www.imooc.com/learn/36)
+ [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

##sort()方法

####定义和用法
sort() 方法用于对数组的元素进行排序

####语法
```
arrayObject.sort(sortby)
//sortby	可选。规定排序顺序。必须是函数。
```

####返回值
对数组的引用。请注意，数组在原数组上进行排序，不生成副本。

####说明
如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。要实现这一点，首先应把数组的元素都转换成字符串（如有必要），以便进行比较。

如果想按照其他标准进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 a 和 b，其返回值如下：
+ 若 a 小于 b，在排序后的数组中 a 应该出现在 b 之前，则返回一个小于 0 的值。
+ 若 a 等于 b，则返回 0。
+ 若 a 大于 b，则返回一个大于 0 的值。

####例子

在本例中，我们将创建一个数组，并按字母顺序进行排序：
```
<script type="text/javascript">

var arr = new Array(6)
arr[0] = "10"
arr[1] = "5"
arr[2] = "40"
arr[3] = "25"
arr[4] = "1000"
arr[5] = "1"

document.write(arr + "<br />")
document.write(arr.sort())

</script>
```
输出：
```
10,5,40,25,1000,1
1,10,1000,25,40,5
```

####请注意，上面的代码没有按照数值的大小对数字进行排序，要实现这一点，就必须使用一个排序函数：
```
<script type="text/javascript">

function sortNumber(a,b)
{
return b - a
}

var arr = new Array(6)
arr[0] = "10"
arr[1] = "5"
arr[2] = "40"
arr[3] = "25"
arr[4] = "1000"
arr[5] = "1"

document.write(arr + "<br />")
document.write(arr.sort(sortNumber))

</script>
```
输出：
```
10,5,40,25,1000,1
1000,40,25,10,5,1
```