# JS 格式规范参考手册
JavaScript - 直译式脚本语言

标签（空格分隔）： javascript dom

---

## JS数据类型
>★ **关键词** `new` ：声明新变量的数据类型

1、`String`（字符串）：存储字符的变量，可用是''或""中的任意文本
2、`Number`（数字）：数字可带小数点，也可以不带
3、`Boolean`（布尔值）：只能有2个值：true或false，常用于条件测试
4、`Array`（数组）：编号从0开始，第一项为[0]，第二项为[1]，以此类推
5、`Object`（对象）：对象由{}分隔，属性由,分隔；在{}内部，对象的属性以名称和值对的形式来定义；空格、换行不影响，声明可跨多行
6、`Undefined`：变量不含值
7、`Null`：通过将变量的值设置为null来清空变量
8、`Symbol`：表示独一无二的值，不能用new声明

---

## JS脚本语言
>每一行的完整语句必须以 `;` 结尾!

### 0、注释：`//……` `/*……*/`
```javascript
//这是对单行js代码的注释

/*
这是对多行
js代码的注释
*/
```
<br/>
### 1、提醒：`alert(……)`（弹窗）
```javascript
alert('Hello!');      //弹出提示窗Hello!
alert(1+1);           //弹出提示窗2（自动计算）
```
<br/>
### 2、变量：`var x` / `var x=……`（声明→赋值）
• **局部变量**：在函数内声明，只能在该函数内部访问它，在函数运行后被删除
• **全局变量**：在函数外声明，所有脚本和函数都能访问它，在页面关闭后被删除

#### ① 直接输出
```javascript
var i;         //Step1：声明变量i
i=1;           //Step2：给i赋值1
alert(i);      //Step3：输出变量值为1

var i=1;       //Step1：声明变量i并赋值1
alert(i);      //Step2：输出变量值为1
```

#### ② 计算结果
```javascript
var a=4;        //Step1：声明变量a
var b=2;        //Step2：声明变量b
var c=a-b;      //Step3：声明变量c及运算法则
alert(c);       //Step4：输出计算结果为2
```
<br/>
### 3、字符串：`"……"`（声明→赋值）
#### ① 直接输出
```javascript
var s;
s="Hello";
alert(s);
```

#### ② 串联输出
```javascript
var a="Hello";
var b="World";
var c=a+b;      //用+串联为一个字符串
alert(c);       //输出结果为Hello World
```
<br/>
### 4、数组：`[元素0,元素1,……,元素n]`（声明变量→创建数组→赋值）
• **编号**：数组中元素的顺序
<table>
    <tr>
        <td style="text-align:right;">从左至右→</td>
        <td style="text-align:center;">0 1 2 …… n</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"></td>
        <td style="text-align:center;">-n …… -2 -1</td>
        <td style="text-align:left;">←从右至左</td>
    </tr>
</table>
• **索引**：`数组名[编号]` 访问数组中的单个元素

#### ① 定义数组
```javascript
var myCars=['Saab','Volvo','BMW'];      //元素之间用,隔开

var myCars=new Array();            //Step1：声明变量为数组函数
myCars[0]="Saab";                  //Step2：索引元素并赋值
myCars[1]="Volvo";
myCars[2]="BMW";

var myCars=new Array("Saab","Volvo","BMW");       //数组函数
```

#### ② 访问数组
```javascript
alert(mycars[0]);      //索引第0个元素并输出值为Saab

$.each(myCars,function(value)){
    alert(value);
});                               //输出每项编号

$.each(myCars,function(value)){
    alert(myCars[value]);
});                               //输出每项元素
```

#### ③ 修改数组中的元素
```javascript
myCars[0]="Open"       //Step1：索引第0个元素并重新赋值
alert(myCars[0]);      //Step2：输出为新值Open
```
<br/>
### 5、对象：`对象名.属性` `对象名.方法()`（声明对象→添加属性/方法）
```javascript
var message="hello world";
var x=message.length;        //使用length属性查找字符串的长度

var message="hello world";
var x=message.toUpperCase();   //使用toUpperCase()方法转换为大写
```

---

## JS函数说明
>★ **关键词** `function` ：调用函数+执行代码+显示结果

### 1、函数：`函数名()`（定义函数→调用显示）
```javascript
function hello()            //Step1：定义函数
{
    alert("hello world");   //Step2：要执行的代码
}
hello();                    //Step3：调用显示
```
<br/>
### 2、参数：`函数名(参数1,参数2,……)`（定义→调用→赋值）
```javascript
function hello(content)        //Step1：定义函数，声明参数（变量）
{
    alert(content);            //Step2：要执行的代码
}
hello(100);                    //Step3：调用、给参数赋值、显示


function add_3(a,b,c)      //定义函数add_3(a,b,c)：返回abc之和
{
    var sum=a+b+c;
    return sum;
}
var s=add_3(1,2,3);        //声明变量s、调用函数、给参数赋值
alert(s);                  //显示结果
```
<br/>
### 3、监听：`函数名.事件=新函数名`（获取元素→定义事件→调用函数）
```html
<body>
    <button id="bt">请点击按钮</button>
    <script type="text/javascript">
        var bt=document.getElementById("bt");   //Step1：获取元素
        bt.onclick=btclick;                     //Step2：定义事件
        function btclick()                      //Step3：调用函数
        {
            alert("按钮被点击！");
        }
    </script>
</body>
```

#### ① UI事件

    onabort  图像加载被中断时触发（不冒泡）
    onerror  当加载文档或图像时发生某个错误时触发（不冒泡）
    onload  某个页面或图像被完成加载时触发
    onresize  窗口或框架被调整尺寸时触发
    onselect  文本被选定时触发
    onunload  用户退出页面时触发
    onscroll  元素滚动条在滚动时触发（冒泡）
    
#### ② 焦点事件

    onfocus  元素获得焦点时触发（不冒泡）
    onblur  元素失去焦点时触发（不冒泡）
    onfocusin  元素即将获得焦点时触发（冒泡）
    onfocusout  元素即将失去焦点时触发（冒泡）
    
#### ③ 变动事件

    onchange  用户改变域的内容时触发
    
#### ④ 鼠标与滚轮事件

    onclick  鼠标点击某个对象时触发
    ondblclick  鼠标双击某个对象时触发
    onmousedown  某个鼠标按键被按下时触发
    onmouseup  某个鼠标按键被松开时触发
    onmousemove  鼠标被移动时触发
    onmouseover  鼠标被移到某元素之上时触发
    onmouseout  鼠标从某元素移开时触发
    onreset  重置按钮被点击时触发（冒泡）
    onsubmit  提交按钮被点击时触发（冒泡）
    
>触发顺序：mousedown → mouseup → click → dbclick

#### ⑤ 键盘与文本事件

    onkeydown  某个键盘的键被按下时触发
    onkeypress  某个键盘的键被按下或按住时触发
    onkeyup  某个键盘的键被松开时触发

>触发顺序：down → press → up

---

## JS代码书写
### 1、JavaScript代码书写位置
① `<head>` 标签内：
```html
<head>
    <script type="text/javascript">
    ……js代码……
    </script>
</head>

<!-- ✔优点：脚本简单；确保载入 -->
<!-- ✘缺点：脚本过大时网页空白 -->
```

② `<body>` 标签内：
```html
<body>
    <p>这是html文档内容</p>
    <script type="text/javascript">
    ……js代码……
    </script>
</body>

<!-- ✔优点：操作HTML元素 -->
<!-- ✘缺点：暂无 -->
```

③ XHTML文档：
```html
<head>
    <script type="text/javascript">
        <![CDATA[……js代码……]]>
    </script>
</head>

<!-- ✔优点：防止XML解析 -->
<!-- ✘缺点：网页空白 -->
```

④ 外部引用：
```html
<head>
    <script type="text/javascript" src="脚本链接.js">
    </script>
</head>

<!-- ✔优点：简洁；公用；文档小 -->
<!-- ✘缺点：增加服务器负担；网页空白 -->
```
<br/>
### 2、JavaScript性能优化：加载和执行
####  ★ 推荐位置
① 将 `<script>` 标签放在 `<body>` 标签内的底部位置
② 减少页面包含的 `<script>` 标签数量，多个js文件合并成一个
③ 尽量引用外部js脚本文件
```html
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="样式表链接.css"/>
    </head>
    <body>
        ……html文档内容……
        <script type="text/javascript" src="脚本链接.js">
        </script>
    </body>
</html>
```

#### ※ 特殊情况
① js脚本放在 `<head>` 标签内
② 使用 `ready()` 方法保证页面加载完成后才开始执行js脚本
```html
<head>
    <meta charset="utf-8">
    <style type="text/css">……css样式内容……</style>
    <script src="jQuery地址"></script>
    <script type="text/javascript">
        $(document).ready(function(){
            ……js脚本代码……
        });
    </script>
</head>
```

---
