---
title: '[cocos]JavaScript基础'
date: 2017-05-13 20:11:51
tags:
---
## 一. DOM、BOM和ECMAScript的关系
ECMAScript提供了js的语法和基本对象。

DOM提供了可以处理html网页上所有元素的接口。

BOM提供了与浏览器进行交互的方法和接口

<!-- more -->
## 二. EMCAScript
EMCAScript作为js的核心，大部分语法与Java相似。以下着重于ES的特点：
### 数据类型细分为三类：

基本类型：

- String：字符串，例如"xxx"
- Number：数字类型，es中Number既可以表示整数（32位或64位）也可以表示浮点数和八、十六进制数
- Boolean：布尔值，有两个值true和false

特殊类型：

- Null：只有一个专用值null，表示不存在的**对象**
- Undefined：同样只有一个专用值，即undefined，声明的变量未初始化
时默认值为undefined

对象类型：

- Object、Array等

### 函数：
函数是es中非常重要的一部分，函数的**基本语法**是：

	function functionName(arg0,arg1,...argN){
		statements
	}
函数有两种常见的**声明方式**：

	// 正常方式：
	function sayHi(sName, sMessage) {
	  alert("Hello " + sName + sMessage);
	}
	sayHi("John", "Tom");

	// FUNCTION方式：
	var sayHi = 
	new Function("sName", "sMessage", "alert(\"Hello \" + sName + sMessage);");
	sayHi("John", "Tom");
在FUNCTION方式中，每个 arg 都是一个参数，最后一个参数是函数主体（要执行的代码）。这些参数必须是字符串。FUNCTION方式比正常方式要慢许多，一般考虑正常方式。

可以看出，函数名只是指向函数对象的引用值，可以作为参数传递。甚至可以使两个变量指向同一个函数。

因此可以得到js中的**扩展函数**，例如为Number扩展：

	Number.prototype.toHexString = function() {
	  return this.toString(16);
	};
	在此环境中，关键字 this 指向 Number 的实例，因此可完全访问 Number 的所有方法。有了这段代码，可实现下面的操作：
	var iNum = 15;
	alert(iNum.toHexString());		//输出 "F"

函数的**参数**：
