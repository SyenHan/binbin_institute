#任务一：零基础JavaScript编码（一）

####任务目的

+ JavaScript初体验
+ 初步明白JavaScript的简单基本语法，如变量、函数
+ 初步了解JavaScript的事件是什么
+ 初步了解JavaScript中的DOM是什么

####任务描述

+ 参考以下示例代码，补充其中的JavaScript功能，完成一个JavaScript代码的编写
+ 本任务完成的功能为：用户可以在输入框中输入任何内容，点击“确认填写”按钮后，用户输入的内容会显示在“您输入的值是”文字的右边

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>IFE JavaScript Task 01</title>
  </head>
<body>

  <label>请输入北京今天空气质量：<input id="aqi-input" type="text"></label>
  <button id="button">确认填写</button>

  <div>您输入的值是：<span id="aqi-display">尚无录入</span></div>

<script type="text/javascript">

(function() {
  /*    
  在注释下方写下代码
  给按钮button绑定一个点击事件
  在事件处理函数中
  获取aqi-input输入的值，并显示在aqi-display中
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
+ 可以不考虑输入的合法性
+ 建议不使用任何第三方库、框架
+ 示例代码仅为示例，可以直接使用，也可以完全自己重写

####在线学习参考资料
+ [JavaScript入门篇](http://www.imooc.com/learn/36)
+ [MDN JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)



```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>无标题文档</title>
<script language="javascript" type="application/javascript">


  function add(){
 //获取输入的值
 var name=document.getElementById("name").value;
 var sex=document.getElementById("sex").value;
 var phone=document.getElementById("phone").value;
 var email=document.getElementById("email").value;
 
// input.setAttribute("value","修改");
 
 var table=document.createElement("table");
 //设置table的border
  table.setAttribute("border","1");
  //创建tr
  var tr=document.createElement("tr");
  
  var enter=new Array();
  enter[0]=document.createTextNode(name);
  enter[1]=document.createTextNode(sex);
  enter[2]=document.createTextNode(phone);
  enter[3]=document.createTextNode(email);
 
  
  for(var i=0;i<enter.length;i++){
  //创建td
  var td=document.createElement("td");
  //文本追加到td
 td.appendChild(enter[i]);  
 //把td添加到tr
 tr.appendChild(td);
    
  }
   //insertCell() 方法用于在 HTML 表的一行的指定位置插入一个空的 <td> 元素。
   var newtd=tr.insertCell();
newtd.innerHTML='<input type="button"   onclick="edit()" value="修改">';




 
  // table.appendChild(tr);
  document.getElementById("table1").appendChild(tr);
  //把table追加到div中
  //document.getElementById("d1").appendChild(table);
  
 
}
 


</script>
</head>


<body>


姓名：<input type="text" id="name"  /><br />
性别：<input type="text" id="sex"  /><br />
电话：<input type="text" id="phone"  /><br />
邮箱：<input type="text" id="email"  /><br />
<input type="button" onclick="add()" value="添加" />


<table width="313" border="1" id="table1">
  <tr>
    <td width="56">姓名</td>
    <td width="41">性别</td>
    <td width="67">电话</td>
    <td width="121">邮箱</td>
    <td width="121">操作</td>
    
  </tr>
  
  <tr>
    <td height="28">王志涵</td>
    <td>女</td>
    <td>12456747</td>
    <td>133523@qq.com</td>
    <td><input type="button" onclick="edit()" value="修改" /></td>
  </tr>
</table>


</body>
</html>
```