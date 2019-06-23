# Code Tips

## 1. Markdown

```markdown
# 一级标题
## 二级标题
### 三级标题

[链接文字](链接地址)
![图片名称](图片地址)

- 强调圆点
- 无序列表

1. 数字序号
2. 有序列表

**加粗**   _斜体_   `代码`

表头1 | 表头2
--- | ---
单元格1-1 | 单元格1-2
单元格2-1 | 单元格2-2
```

## 2. HTML/CSS

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1, maximum-scale=1, shrink-to-fit=no">
    
    <!-- 引入样式库 -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.2/css/all.css">
    <!-- 私有样式 -->
    <link rel="stylesheet" type="text/css" href="...">
    <!-- 图标 -->
    <link rel="icon" type="image/x-icon" href="favicon.ico">
    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
    
    <title>...</title>
</head>
<body>
    <!-- HTML属性建议书写顺序： -->
    <div class="" id="" name="" data-*="" src="" for="" type="" href="" title="" alt="" aria-*="" role="" disabled></div>
    <!-- 减少标签的数量，尽量避免多余的父元素；尽量避免通过 JavaScript 生成标签 -->

    <!-- 动态调整字号 -->
    <script type="text/javascript" src="font-size.js"></script>
    <!-- 引入脚本库 -->
    <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
    <script src="https://vuejs.org/js/vue.js"></script>
    <script src="https://unpkg.com/vue-router/dist/vue-router.js"></script>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/hammer.js/2.0.8/hammer.js"></script>
    <script src="./node_modules/vue-touch/dist/vue-touch.js"></script>
    <!-- 私有脚本 -->
    <script type="text/javascript" src="..."></script>
</body>
</html>
```

```css
/* 为选择器分组时，每个选择器独占一行 */
/* rgb()、rgba()、hsl()、hsla()、rect() 内部只加逗号不加空格 */
/* 省略小数点前面的0（例如：.5 代替 0.5，-.5px 代替 -0.5px） */
/* 十六进制值应该全部小写，并且尽量简写（例如：用 #fff 代替 #ffffff） */
/* 为选择器中的属性添加双引号（例如：input[type="text"]） */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}

/* 相关的属性声明应当归为一组，书写顺序： */
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}

/* 带有前缀的属性，多行缩进对齐 */
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```

- bootstrap全局样式修改：

属性 | 基础值
--- | ---
bg | `white`(body/input/input-focus/nav-tabs-link-active/dropdown/pagination/pagination-disabled/card/popover/modal-content/list-group/list-group-disabled/thumbnail/carousel-indicator-active) `#4F94CD`(component-active/dropdown-link-active/pagination-active/progress-bar/list-group-active)  `#fcf8e3`(mark)  `rgba(#000, .05)`(table-accent)  `rgba(#000, .075)`(table-hover/table-active)  `#e9ecef`(table-head/input-disabled/input-group-addon/dropdown-divider/pagination-hover/jumbotron/progress/list-group-action-active/breadcrumb)  `#343a40`(table-dark)  `rgba($white, .05)`(table-dark-accent)  `rgba($white, .075)`(table-dark-hover)  `#f8f9fa`(dropdown-link-hover/list-group-hover)  `rgba(#000, .03)`(card-cap)  `black`(tooltip/modal-backdrop)  `#212529`(kbd)
border-color | `#dee2e6`(base/table/nav-tabs/pagination/pagination-hover/pagination-disabled/modal-header/modal-footer/thumbnail)  `rgba(#000, .1)`(hr/navbar-light-toggler/toast)  `#ced4da`(input/input-group-addon)  `#A9A9A9`(nav-pills-link)  `white`(nav-pills-link-active)  `rgba(#fff, .1)`(navbar-dark-toggler)  `rgba(#000, .15)`(dropdown)  `#4F94CD`(pagination-active/list-group-active)  `rgba(#000, .125)`(card/list-group)  `rgba(#000, .2)`(popover/modal-content)  `rgba(#000, .05)`(toast-header)
border-radius | `.25rem`(base/btn/input/nav-tabs/nav-pills/navbar-toggler/dropdown/card/tooltip/form-feedback-tooltip/toast/badge/alert/progress/list-group/thumbnail/breadcrumb)  `.3rem`(lg/btn-lg/input-lg/popover/modal-content)  `.2rem`(sm/btn-sm/input-sm)  `50rem`(rounded-pill) `10rem`(badge-pill)
border-width | `1px`(base/hr/table/input-btn/btn/input/nav-tabs/dropdown/pagination/card/popover/toast/modal-content/modal-header/modal-footer/alert/list-group/thumbnail)  `.25em`(spinner)  `.2em`(spinner-sm)
box-shadow | `0 .5rem 1rem rgba(#000, .15)`  `0 1rem 3rem rgba(#000, .175)`(lg)  `0 .125rem .25rem rgba(#000, .075)`(sm)  `inset 0 -.1rem 0 rgba($black, .25)`(kbd)  `inset 0 1px 0 rgba(#fff, .15), 0 1px 1px rgba(#000, .075)`(btn)
color | `white`(component-active/nav-pills-link-active/dropdown-link-active/navbar-dark-active/navbar-dark-brand/navbar-dark-brand-hover)  `#6c757d`(muted/blockquote-small/nav-link-disabled/btn-link-disabled/dropdown-link-disabled)  `#4F94CD`(link)  `#495057`(nav-tabs-link-active)  `#A9A9A9`(nav-pills-link)  `#212529`(dropdown-link)  `#e9ecef`(nav-divider)  `rgba(#fff, .5)`(navbar-dark)  `rgba(#fff, .75)`(navbar-dark-hover)  `rgba(#fff, .25)`(navbar-dark-disabled)  `rgba(#000, .5)`(navbar-light)  `rgba(#000, .7)`(navbar-light-hover)  `rgba(#000, .9)`(navbar-light-active/navbar-light-brand/navbar-light-brand-hover)  `rgba(#000, .3)`(navbar-light-disabled)
font-size | `1rem`(base/input-btn/btn/input)  `1.25rem`(lg/lead/blockquote/navbar-brand/navbar-toggler/input-btn-lg/btn-lg/input-lg)  `.875rem`(sm/input-btn-sm/btn-sm/input-sm)  `6rem`(display1)  `5.5rem`(display2)  `4.5rem`(display3)  `3.5rem`(display4)  `80%`(small/blockquote-small)
font-weight | `400`(base/btn/input)  `700`(bold/dt/nested-kbd/alert-link)  `500`(headings)  `300`(display/lead)
height | `2.5rem`(nav-link)  `1.875rem`(navbar-brand)
line-height | `1.5`(base/lg/sm/input-btn/input-btn-sm/input-btn-lg/btn/btn-sm/btn-lg/input/input-sm/input-lg)  `1.2`(headings/display)
margin | `.255em`(caret)  `.5rem`(headings-bottom/nav-divider-y/btn-block-y)  `1rem`(hr-y)
opacity | `.65`(btn-disabled)
padding | `.255em`(caret)  `.2em`(mark)  `.5rem`(list-inline/nav-link-y/navbar-nav-link-x/navbar-y/input-btn-x-sm/input-btn-y-lg/btn-x-sm/btn-y-lg/btn-block-y/input-x-sm/input-y-lg)  `1rem`(nav-link-x/navbar-x/input-btn-x-lg/btn-x-lg/input-x-lg)  `.3125rem`(navbar-brand-y)  `.25rem`(navbar-toggler-y/input-btn-y-sm/btn-y-sm/input-y-sm)  `.75rem`(navbar-toggler-x/input-btn-x/btn-x/input-x)  `.375rem`(input-btn-y/btn-y/input-y)
transition | `all .2s ease-in-out`  `opacity .15s linear`(fade)  `height .35s ease`(collapse)
vertical-align | `.255em`(caret)
width | `.3em`(caret)  `.2rem`(input-btn-focus/btn-focus)

- bootstrap组件居中对齐：

调整属性 | 组件名称
--- | ---
line-height | headings、display、input-btn、btn、input、custom-select、custom-file、pagination、form-feedback-tooltip、modal-title
margin | paragraph、headings、hr、label、form-text、form-check-input、form-check-inline、form-check-inline-input、form-group、form-feedback、nav-divider、dropdown-divider、card-group、card-deck、card-columns、tooltip、modal-dialog、alert、breadcrumb
padding | mark、list-inline、table-cell、input-btn、btn、input、custom-select、custom-select-indicator、custom-select-feedback-icon、custom-file、nav-link、navbar、navbar-nav-link、navbar-brand、navbar-toggler、dropdown、dropdown-item、pagination、jumbotron、card-img-overlay、tooltip、form-feedback-tooltip、popover-header、popover-body、toast、badge、badge-pill、modal-inner、modal-header、alert、list-group-item、thumbnail、breadcrumb、breadcrumb-item、kbd

- 初次加载后显示的tab-pane初始页面不要fade，会一片空白

- 因导航栏固定需向body添加padding，但会影响锚点定位，所以建议用设置了高度的空div撑开页面内容

- 内联元素内的文字居中（写在该元素上）：
```css
a {
    height: 1.5rem;    /* step1：确定高度 */
    padding-top: .35rem;    /* step4：paddingTop=(height-fontSize)/2 */
    font-size: .8rem;    /* step2：确定字号 */
    line-height: 1;    /* step3：行高设为字号的1倍 */
    text-align: center;    /* step5：文本水平居中 */
} 
```

- 实现动画效果的经验小结：

场景 | 方法 | 备注
--- | --- | ---
滚动条/多个属性值过渡 | jQuery - animate() | document和window对象不能执行此方法
hover/单个属性值过渡 | CSS - transition | 
延迟执行/循环动画 | CSS - animation | 

- 元素添加绝对定位后会覆盖在同级元素之上，不用设置`z-index`

- `display: none`之后，元素依然存在文档中，所以绑定的事件等脚本仍有效

- 电影海报尺寸：

版本 | 尺寸
--- | ---
原版/再版 | 99*69cm
授权 | 88*59cm

- 内联元素自适应父元素尺寸：
```css
/* 先给父元素设置宽高，然后在子元素上调整 */
.child {
    width: 100%;
    height: 100%;
}
```

- 元素尺寸填满当前窗口（写在该元素上）：
```css
body {
    width: 100vw; 
    height: 100vh;
}
```

- 溢出部分显示滚动条查看：
```css
div {
    height: 100vh;
    overflow: auto;
}
```

- 多行文本溢出部分省略：
```css
p {
    overflow: hidden;
    text-overflow: ellipsis;     /* 溢出部分省略为... */
 /* text-overflow: '>>';     Firefox下，溢出部分可省略为字符串内容 */
    display: -webkit-box;
    -webkit-line-clamp: 3;     /* 指定文本可显示的行数 */
    -webkit-box-orient: vertical;
}
```

- 块级元素容器尺寸自适应内容（写在该元素上）：
```css
.parent {
    display: inline-block;    /* 仍可设置宽高 */
}
```

- 块元素清除内部元素的浮动（写在容器元素上）：
```css
.parent::after {
    content: "";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
}
.parent {
    zoom: 1;
}
```

## 3. JavaScript/jQuery

- jQuery选择器建议：
```javascript
$("#idName")  //首选
$("tagName")  //其次
$("Parent").find("Child")  //父子

//优先使用原生javascript方法，尽量避免使用jQuery方法

//声明变量做好缓存，使用选择器的次数越少越好
var cached = jQuery('#top');
cached.find('p.classA');
cached.find('p.classB');

//使用链式写法
$('div').find('h3').eq(2).html('Hello');

//尽量不要改动DOM结构，不要频繁使用append()、insertBefore()、insetAfter()这样的方法
```

- 在一个方法内部，第一个`return`关键字将中断后面的代码执行，所以if判断应放在return内部

- 兼容性获取滚动条位置：
```javascript
var scrollTop = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop;
```

- 嵌套循环性能优化：在嵌套外实例化全部变量；循环次数越少放在越外层

- jQuery AJAX方法比较

方法 | 作用 | 适用场合
:--- | :--- | :---
`$.ajax()` | 执行 AJAX（异步 HTTP）请求 | 精确控制
`$.get()` | 使用 HTTP GET 请求从服务器加载数据 | 取回数据/可以缓存/历史记录/收藏书签/长度限制
`$.getJSON()` | 使用 AJAX 的 HTTP GET 请求获取 JSON 数据 | json专用/跨域调用/安全保密
`$.post()` | 使用 HTTP POST 请求从服务器加载数据 | 提交数据/不能缓存/后退刷新/安全保密/没有限制

- 遍历方法性能比较

方法 | 语法 | 短循环等级 | 长循环等级
:--- | :--- | :--- | :---
for | `for (var i = 0, len = arr.length; i < len; i++) {……}` | 1 | 1
for | `for (var i = 0; i < arr.length; i++) {……}` | 2 | 2
for | `for (var i = 0; arr[i] != null; i++) {……}` | 3 | 3
forEach | `Array.prototype.forEach.call(arr,function(el){……});` | 4 | 7
forEach | `arr.forEach(function(e){……});` | 5 | 6
map | `arr.map(function(n){……});` | 6 | -
for of | `for (x of arr) {……}` | 7 | 4
for of | `for (let x of arr) {……}` | 8 | 5
for in | `for (x in arr) {……}` | 9 | -

- js数组方法

检测数组元素 | 作用 | 返回 | 参数
:--- | :--- | :--- | :---
`every()` | 使用指定函数检测数组中的所有元素 | true/false | function(currentValue,index,arr), thisValue
`filter()` | 检测数组中符合条件的所有元素 | 新数组 | function(currentValue,index,arr), thisValue
`some()` | 使用指定函数检测数组中的每个元素 | true/false | function(currentValue,index,arr), thisValue
**遍历执行函数** | **作用** | **返回** | **参数**
`find()` | 为数组中的每个元素依次执行函数 | 元素值/undefined | function(currentValue,index,arr), thisValue
`findIndex()` | 为数组中的每个元素依次执行函数 | 索引/-1 | function(currentValue,index,arr), thisValue
`forEach()` | 调用数组的每个元素传递给回调函数 | 函数执行结果 | function(currentValue,index,arr), thisValue
`map()` | 按照原始数组元素顺序依次处理元素 | 函数执行结果 | function(currentValue,index,arr), thisValue
**判断包含元素** | **作用** | **返回** | **参数**
`includes()` | 判断一个数组是否包含指定的值 | true/false | searchElement, fromIndex
`indexOf()` | 从头到尾地检索数组是否含有某个元素 | 索引/-1 | item, start
`lastIndexOf()` | 从尾到头地检索数组是否含有某个元素 | 索引/-1 | item, start
**转换为字符串** | **作用** | **返回** | **参数**
`join()` | 把数组转换为一个字符串，指定分隔符 | 字符串 | separator
`toString()` | 把数组转换为一个字符串，逗号分隔 | 字符串 | 
`valueOf()` | 返回数组的原始值，逗号分隔 | 字符串 | 

- if语句与switch语句

语句 | 适用场合
--- | ---
if | 布尔值；动态/区间的值；复杂的逻辑关系；选项数量小于5个
switch | 整数/字符串；固定/有限的值；选项数量（含default）大于5个

- 滚动条效果
```javascript
$("html, body").animate({ scrollTop: 0 }, 300, "linear");    // 滚动到顶部
$("html, body").animate({ scrollTop: $(document).height() }, 300, "linear");    // 滚动到底部
$(document).scrollLeft(0);    // 复位水平滚动条
```

- 点击除该元素以外的其他位置触发事件：
```javascript
//需是同一类事件（例如同为点击事件）
$(document).click(function(){
    ……
});
$("#idName").click(function(event){
    event.stopPropagation();
});
```

- 真假值：

Truthy（真值） | Falsy（假值）
--- | ---
`true`  `{}`  `[]`  `42`  `-42`  `"foo"`  `new Date()`  `3.14`  `-3.14`  `Infinity`  `-Infinity` | `false`  `null`  `undefined`  `0`  `NaN`  `' '`  `" "`  `` ``  `document.all`

- YYYY-MM-DD（简单位数验证）：
```javascript
/^\d{4}-\d{2}-\d{2}$/
```
- YYYY-MM-DD（考虑闰年）：
```javascript
/^(?:(?!0000)[0-9]{4}-(?:(?:0[1-9]|1[0-2])-(?:0[1-9]|1[0-9]|2[0-8])|(?:0[13-9]|1[0-2])-(?:29|30)|(?:0[13578]|1[02])-31)|(?:[0-9]{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)-02-29)$/
```
- YYYY-/.MM-/.DD（考虑闰年）：
```javascript
/^(?:(?!0000)[0-9]{4}([-/.])(?:(?:0[1-9]|1[0-2])([-/.])(?:0[1-9]|1[0-9]|2[0-8])|(?:0[13-9]|1[0-2])([-/.])(?:29|30)|(?:0[13578]|1[02])([-/.])31)|(?:[0-9]{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)([-/.])02([-/.])29)$/
```
- YYYY-/.M(M)-/.D(D)（考虑闰年）：
```javascript
/^(?:(?!0000)[0-9]{4}([-/.])(?:(?:0?[1-9]|1[0-2])\1(?:0?[1-9]|1[0-9]|2[0-8])|(?:0?[13-9]|1[0-2])\1(?:29|30)|(?:0?[13578]|1[02])\1(?:31))|(?:[0-9]{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)([-/.])0?2\2(?:29))$/
```
- DD/MM/YYYY（考虑闰年）：
```javascript
/^(((0[1-9]|[12][0-9]|3[01])/((0[13578]|1[02]))|((0[1-9]|[12][0-9]|30)/(0[469]|11))|(0[1-9]|[1][0-9]|2[0-8])/(02))/([0-9]{3}[1-9]|[0-9]{2}[1-9][0-9]{1}|[0-9]{1}[1-9][0-9]{2}|[1-9][0-9]{3}))|(29/02/(([0-9]{2})(0[48]|[2468][048]|[13579][26])|((0[48]|[2468][048]|[3579][26])00)))$/
```
- D(D)-/.M(M)-/.YYYY（考虑闰年）：
```javascript
/^(?:(?:(?:0?[1-9]|1[0-9]|2[0-8])([-/.])(?:0?[1-9]|1[0-2])|(?:29|30)([-/.])(?:0?[13-9]|1[0-2])|31([-/.])(?:0?[13578]|1[02]))([-/.])(?!0000)[0-9]{4}|29([-/.])0?2([-/.])(?:[0-9]{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00))$/
```
- hh:mm:ss（24时制）：
```javascript
/^([01][0-9]|2[0-3]):[0-5][0-9]:[0-5][0-9]$/
```

- 布尔类型变量取反，实现切换效果：
```javascript
var b = true;
b = !b;    //对t取反并赋值给t，此时b = false，再次执行变为true，再次执行变为false……
```

- 返回操作对比：

方法 | 效果
--- | ---
`return ……` | 返回值，存储在参数中，不写入HTML
`$(……).text()` | 返回文本内容，会删除HTML标记 ；设置文本内容，写入原HTML，会覆盖
`…….innerHTML=……` | 返回或设置HTML内容，写入原HTML，会覆盖
`$(……).html()` | 返回或设置HTML内容，写入原HTML，会覆盖
`document.write(……)` | 返回或设置HTML/JavaScript，写入原HTML，会覆盖

- 替换一条字符串中的多个字符：
```javascript
stringObject.replace(……).replace(……)    //连续替换多次即可
```

- 不足两位数时在前面补0：
```javascript
num = num > 9 ? num : "0" + num    //三元运算符简单实现条件语句
```

- 事件触发顺序：

click事件 | focus事件
--- | ---
mousedown → mouseup → click | mousedown → focus → mouseup → click


## 4. Vue.js
- 风格指南
```html
<!-- 永远不要把 v-if 和 v-for 同时用在同一个元素上 -->
<ul>
  <li
    v-for="user in activeUsers"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>

<!-- 为组件样式设置作用域 -->
<style scoped>
.button {
  border: none;
  border-radius: 2px;
}

.button-close {
  background-color: red;
}
</style>

<!-- 在单文件组件、字符串模板和 JSX 中没有内容的组件应该是自闭合的；对于绝大多数项目来说，总是 PascalCase 的 -->
<MyComponent/>
<!-- 但在 DOM 模板里永远不要这样做；总是 kebab-case 的 -->
<my-component></my-component>

<!-- 在声明 prop 的时候，在模板和 JSX 中应该始终使用 kebab-case -->
<WelcomeMessage greeting-text="hi"/>

<!-- 多个特性的元素应该分多行撰写，每个特性一行 -->
<MyComponent
  foo="a"
  bar="b"
  baz="c"
/>

<!-- 元素 (包括组件) 的特性应该有统一的顺序 -->
<MyComponent
  is
  v-for
  v-if
  v-else-if
  v-else
  v-show
  v-cloak
  v-pre
  v-once
  id
  ref
  key
  slot
  v-model
  v-on
  v-html
  v-text
/>

<!-- 单文件组件的顶级元素的顺序 -->
<template>...</template>
<script>/* ... */</script>
<style>/* ... */</style>

<!-- 如果一组 v-if + v-else 的元素类型相同，最好使用 key (比如两个 <div> 元素) -->
<div
  v-if="error"
  key="search-status"
>
  错误：{{ error }}
</div>
<div
  v-else
  key="search-results"
>
  {{ results }}
</div>
```
```javascript
// 组件名为多个单词
export default {
  name: 'TodoItem',
  // ...
}

// Prop 定义应该尽量详细
props: {
  status: {
    type: String,
    required: true,
    validator: function (value) {
      return [
        'syncing',
        'synced',
        'version-conflict',
        'error'
      ].indexOf(value) !== -1
    }
  }
}

// 使用模块作用域保持不允许外部访问的函数的私有性
var myGreatMixin = {
  // ...
  methods: {
    publicMethod() {
      // ...
      myPrivateFunction()
    }
  }
}

function myPrivateFunction() {
  // ...
}

export default myGreatMixin

// JS/JSX 中的组件名应该始终是 PascalCase 的
import MyComponent from './MyComponent.vue'
export default {
  name: 'MyComponent',
  // ...
}

// 在声明 prop 的时候，其命名应该始终使用 camelCase
props: {
  greetingText: String
}

// 组件/实例的选项应该有统一的顺序
el
name
parent
functional
delimiters
comments
components
directives
filters
extends
mixins
inheritAttrs
model
props/propsData
data
computed
watch
beforeCreate
created
beforeMount
mounted
beforeUpdate
updated
activated
deactivated
beforeDestroy
destroyed
methods
template/render
renderError
```
```shell
# 单文件组件的文件名应该要么始终是单词大写开头 (PascalCase)，要么始终是横线连接 (kebab-case)
components/
|- MyComponent.vue
components/
|- my-component.vue

# 应用特定样式和约定的基础组件 (也就是展示类的、无逻辑的或无状态的组件) 应该全部以一个特定的前缀开头，比如 Base、App 或 V
components/
|- BaseButton.vue
|- BaseTable.vue
|- BaseIcon.vue

# 只应该拥有单个活跃实例的组件应该以 The 前缀命名，以示其唯一性
components/
|- TheHeading.vue
|- TheSidebar.vue

# 和父组件紧密耦合的子组件应该以父组件名作为前缀命名
components/
|- TodoList.vue
|- TodoListItem.vue
|- TodoListItemButton.vue

# 组件名应该以高级别的 (通常是一般化描述的) 单词开头，以描述性的修饰词结尾
components/
|- SearchButtonClear.vue
|- SearchButtonRun.vue
|- SearchInputQuery.vue
|- SearchInputExcludeGlob.vue
|- SettingsCheckboxTerms.vue
|- SettingsCheckboxLaunchOnStartup.vue

# 组件名应该倾向于完整单词而不是缩写
components/
|- StudentDashboardSettings.vue
|- UserProfileOptions.vue
```

- 若出现vue实例渲染空白，请检查以下几项：1、函数内部的`this`指向 2、`v-on="{}"`内部不能带修饰符

- vue-touch事件

分类 | 事件 | 效果
--- | --- | ---
Pan | `pan` `panstart` `panmove` `panend` `pancancel` `panleft` `panright` `panup` `pandown` | 按住拖动
Pinch | `pinch` `pinchstart` `pinchmove` `pinchend` `pinchcancel` `pinchin` `pinchout` | 双指放大/缩小
Press | `press` `pressup` | 长按（至少500毫秒）
Rotate | `rotate` `rotatestart` `rotatemove` `rotateend` `rotatecancel` | 多指旋转
Swipe | `swipe` `swipeleft` `swiperight` `swipeup` `swipedown` | 滑动
Tap | `tap` | 点击（最多250毫秒）

- 单选切换效果：
```html
<button :class="{active: order == 0}" @click="order = 0">单选框</button>
```

- v-for循环中尽量不使用id，因为id是唯一的，无法循环！但如果非要使用id，可利用item.id或index动态绑定不同的id值~

- 命名法：

命名法 | 适用范围
--- | ---
camelCase | 变量、参数、函数、方法、方法属性、id、空间
PascalCase | 类、枚举、Vue组件
kebab-case | html文件、标签、元素属性、选择器
underline_case | css文件
UNDERLINE_CASE | 常量、枚举属性
_underlinecase | 私有成员

- 命名用词：

名称范围 | 建议用词
--- | ---
变量名 | （名词短语）、 isName/hasName（布尔值）
函数/方法名 | canName/hasName/isName（布尔值）、getName（获取值）、setName/loadName（无返回或……）
Vue方法名 | （动宾短语）、onName（事件）、setName/getName/openName/closeName/jumpName/loadName（常用单词）

## 5. Vue-Cli
### Step 1: 创建一个vue项目
运行命令提示符（快捷键"Win+R" → 输入"cmd"）：
```shell
E:    # 命令执行环境转移到E盘内
```
```shell
cd _projects    # 命令执行环境转移到E:\_projects内
```
```shell
cd Vues    # 命令执行环境转移到E:\_projects\Vues内
```
```shell
vue create vue-project    # 创建一套名为"vue-project"的工程项目
# 使用键盘上下键和空格键选择preset（一般沿用上次项目的设置即可）
```
```shell
cd vue-project    # 命令执行环境转移到E:\_projects\Vues\vue-project内
```
```shell
npm run serve    # 在开发环境下编译和热加载
```
关闭命令提示符窗口，复制`vue.config.js`和`touch.js`文件到vue-project文件夹内，修改文件中的基本配置

### Step 2: 安装各种依赖
vue-project文件夹内右键选择 Git Bash Here：
#### • 引入vue-touch
```bash
$ npm install vue-touch@next    # 安装vue-touch
```
在`main.js`文件中调用：
```javascript
...
import touch from './touch'
...
new Vue({
  router,
  touch,
  render: h => h(App)
}).$mount('#app')
```
#### • 引入*-loader
```bash
$ npm install style-loader --save-dev    # 安装style-loader
```
```bash
$ npm install --save-dev css-loader    # 安装css-loader
```
```bash
$ npm install file-loader --save-dev    # 安装file-loader
```
```bash
$ npm install url-loader --save-dev    # 安装url-loader
```
#### • 引入jquery
```bash
$ npm install jquery    # 安装jquery
```
在`.eslintrc.js`文件中添加配置：
```javascript
env: {
    node: true,
    jquery: true
  },
```
#### • 引入bootstrap
```bash
$ npm install popper.js --save    # 安装popper.js
```
```bash
$ npm install bootstrap    # 安装bootstrap
```
在`main.js`文件中调用：
```javascript
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap/dist/js/bootstrap.min.js'
```
#### • 引入fontawesome
```bash
$ npm install --save-dev @fortawesome/fontawesome-free    # 安装fontawesome-free
```
在`main.js`文件中调用：
```javascript
import '@fortawesome/fontawesome-free/css/all.css'
```
#### • 引入axios
```bash
$ npm install axios    # 安装axios
```
在`*.vue`文件中调用：
```javascript
import axios from 'axios'

export default {
  ...
}
```
#### • 引入webpack-dev-server
```bash
$ npm install webpack-dev-server --save-dev    # 安装webpack-dev-server
```

### Step 3: 图形化界面管理项目
在`package.json`文件中添加设置：
```javascript
"scripts": {
    "serve": "vue-cli-service serve --open",
    ...
  },
```
vue-project文件夹内右键选择 Git Bash Here：
```bash
$ vue ui    # 浏览器中打开图形化界面
```
图形化界面导入vue-project文件夹为项目，前往“任务”页运行项目

## 6. Others
![bits](https://github.com/shawxlee/study-notes/blob/master/md%E5%9B%BE%E7%89%87/bits.jpg?raw=true)
