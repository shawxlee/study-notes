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
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css">
    <link rel="stylesheet" type="text/css" href="……">

    <link rel="icon" type="image/x-icon" href="favicon.ico">
    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
    <title>……</title>
</head>
<body>
    <!-- HTML属性建议书写顺序： -->
    <div class="" id="" name="" data-*="" src="" for="" type="" href="" title="" alt="" aria-*="" role="" disabled></div>
    <!-- 减少标签的数量，尽量避免多余的父元素；尽量避免通过 JavaScript 生成标签 -->

    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>
    <script type="text/javascript" src="……"></script>
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

- 初次加载后显示的tab-pane初始页面不要fade，会一片空白

- 因导航栏固定需向body添加padding，但会影响锚点定位，所以建议用设置了高度的空div撑开页面内容

- bootstrap组件居中对齐：

调整属性 | 组件名称
--- | ---
line-height | headings、display、input-btn、btn、input、custom-select、custom-file、pagination、form-feedback-tooltip、modal-title
margin | paragraph、headings、hr、label、form-text、form-check-input、form-check-inline、form-check-inline-input、form-group、form-feedback、nav-divider、dropdown-divider、card-group、card-deck、card-columns、tooltip、modal-dialog、alert、breadcrumb
padding | mark、list-inline、table-cell、input-btn、btn、input、custom-select、custom-select-indicator、custom-select-feedback-icon、custom-file、nav-link、navbar、navbar-nav-link、navbar-brand、navbar-toggler、dropdown、dropdown-item、pagination、jumbotron、card-img-overlay、tooltip、form-feedback-tooltip、popover-header、popover-body、toast、badge、badge-pill、modal-inner、modal-header、alert、list-group-item、thumbnail、breadcrumb、breadcrumb-item、kbd

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

- 调整按钮尺寸：
```css
button {
    margin: 0;
    padding: 0;
    width: 3.5rem;   /* 设置宽高 */
    height: 2rem;
    font-size: 0.9rem;   /* 设置字号 */
}
```

- 调整图标尺寸：
```css
i {
    font-size: 1.5rem;
}
```

- 元素尺寸填满当前窗口（写在该元素上）：
```css
body {
    width: 100vw; 
    height: 100vh;
}
```

- 圆形边框：
```css
div {
    border-radius: 50%;
}
```

- 背景颜色透明度：
```css
div {
    background-color: rgba(190,190,190,.6);    /* R,G,B,透明度 */
}
```

- 首行缩进两个字符：
```css
p {
    text-indent: 2em;
}
```

- 溢出部分显示滚动条查看：
```css
div {
    height: 100vh;
    overflow: auto;
}
```

- 元素高度始终为当前窗口高度减去固定高度：
```css
div {
    height: calc(100vh - 100px);     /* 运算符前后都必需有空格 */
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

- CSS画直角箭头：
```css
div {
    display: inline-block;
    width: 15px;
    height: 15px;
    border-top: 1px solid;
    border-right: 1px solid;
    transform: rotate(45deg);
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

- 使input与其他元素内联（写在该元素上）：
```css
input {
    float: left;   /* 其他元素可能也需要一起浮动 */
}
```

- 内联元素中的文本内容居中（写在该元素上）：
```css
a {
    height: 3rem;
    line-height: 3rem;
    text-align: center;
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
b = !b;    //对t取反并赋值给t
alert(b);    //此时b = false，再次执行变为true，再次执行变为false……
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
num = num>9 ? num : "0"+num;   //三元运算符简单实现条件语句
```

- 所有jQuery代码包裹：
```javascript
$(document).ready(function(){……})
$().ready(function(){……})
$(function(){……})
```

- jQuery自定义全局函数:
```javascript
$.funcName = function(){……};
```

- 事件触发顺序：

click事件 | focus事件
--- | ---
mousedown → mouseup → click | mousedown → focus → mouseup → click


## 4. Vue.js

- 单选切换效果：
```html
<button :class="{active: order == 0}" @click="order = 0">单选框</button>
```

- v-for循环中，给style动态绑定函数，根据条件改变样式：
```html
<p :style="{color: scoreColor(item)}">{{ item.score }}</p>
```
```javascript
changeColor: function (item) {
    if (item.score >= 9) {
        return '#551A8B';
    }
    else if (item.score < 9 && item.score >= 8) {
        return '#00008B';
    }
    else {
        return '#8B0000';
    }
}
```

- v-for循环中尽量不使用id，因为id是唯一的，无法循环！但如果非要使用id，可利用index动态绑定不同的id值~

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

- 实例中选项的顺序：
```javascript
components
props
data
created
mounted
activited
update
beforeRouteUpdate
methods
filter
computed
watch
```

- v-for中计算时间差：
```html
<div v-for="item in items">{{ getDiff(item) }}</div>
```
```javascript
getDiff: function (item) {
    var st = new Date(item.startTime);
    var et = new Date(item.endTime);
    var millDiff = et.getTime() - st.getTime();
    var dayDiff = Math.floor(millDiff / (1000*60*60*24));
    var dayRem = millDiff % (1000*60*60*24);
    var hourDiff = Math.floor(dayRem / (1000*60*60));
    var hourRem = dayRem % (1000*60*60);
    var minDiff = Math.floor(hourRem / (1000*60));
    var minRem = hourRem % (1000*60);
    var secDiff = Math.round(minRem / 1000);
    return dayDiff + "天" + hourDiff + "时" + minDiff + "分" + secDiff + "秒";
}
```

- 一个事件中调用多个方法：
```html
<a @eventName="methA();methB();methC()"></a>
```

## 5. Others
![bits](https://github.com/shawxlee/study-notes/blob/master/md%E5%9B%BE%E7%89%87/bits.jpg?raw=true)
