# JS 属性|函数|方法|事件|运算符参考手册
JavaScript - 直译式脚本语言

---

## JavaScript 对象
### 1、**全局**：属性和函数可用于所有内建的JavaScript对象
**- 全局属性**
#### • `undefined`：存放 JavaScript 中未定义的值
```javascript
undefined    //一个未声明的变量，或已声明但没有赋值的变量，或一个并不存在的对象属性
```

**- 全局函数**
#### • `parseInt()`：解析一个字符串，并返回一个整数
```javascript
parseInt(string,radix);

//*string：要被解析的字符串
```
    *radix  要解析的数字的基数（介于2~36之间）
<br/>
### 2、**Array**：在单个的变量中存储多个值
```javascript
new Array();
new Array(size);
new Array(element0, element1, ..., elementn);

//*size：期望的数组元素个数
//*element：参数列表（新数组的元素）
```

**- Array对象方法**
#### • `concat()`：连接两个或多个数组
```javascript
arrayObject.concat(array1,array2,……);

//*arrayX：该参数可以是具体的值，也可以是数组对象，可以是任意多个
```

#### • `filter()`：筛选指定数组中符合条件的所有元素，创建一个新的数组
```javascript
arrayObject.filter(function(currentValue,index,arr), thisValue);

//function(currentValue,index,arr)：数组中的每个元素都会执行这个函数
//*currentValue：当前元素的值
```
    *index  当前元素的索引值
    *arr  当前元素属于的数组对象
    *thisValue  对象作为该执行回调时使用，传递给函数，用作 "this" 的值；如果省略了 thisValue ，"this" 的值为 "undefined"

#### • `join()`：把数组中的所有元素组合成一个字符串并返回
```javascript
arrayObject.join(separator);
```
    *separator  指定要使用的分隔符（默认使用逗号）

#### • `pop()`：删除并返回数组的最后一个元素
```javascript
arrayObject.pop();
```

#### • `push()`：向数组的末尾添加一个或多个元素，并返回新的长度
```javascript
arrayObject.push(newelement1, newelement2, ……);

//*newelement1：要添加到数组的第一个元素
```
    *newelementX  可添加多个元素

#### • `reverse()`：颠倒数组中元素的顺序并返回
```javascript
arrayObject.reverse();
```

#### • `shift()`：把数组的第一个元素从其中删除，并返回第一个元素的值
```javascript
arrayObject.shift();
```

#### • `slice()`：从已有的数组中返回选定的元素
```javascript
arrayObject.slice(start,end);

//*start：规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置
```
    *end  规定从何处结束选取。该参数是数组片断结束处的数组下标；如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素；如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素

#### • `sort()`：对数组的元素进行排序
```javascript
arrayObject.sort(sortby);
```
    *sortby  规定排序顺序的函数

#### • `splice()`：向/从数组中添加/删除项目，然后返回被删除的项目
```javascript
arrayObject.splice(index, howmany, item1, item2, ……);

//*index：整数，规定添加/删除项目的位置，使用负数可从数组结尾处规定位置
//*howmany：要删除的项目数量，如果设置为 0，则不会删除项目
```
    *itemX  向数组添加的新项目

#### • `unshift()`：向数组的开头添加一个或更多元素，并返回新的长度
```javascript
arrayObject.unshift(newelement1, newelement2, ……);

//*newelement1：要添加到数组的第一个元素
```
    *newelementX  可添加多个元素
<br/>
### 3、**Boolean**：仅表示两个值true/false
```javascript
new Boolean(value);    //构造函数
Boolean(value);    //转换函数

//*value：由对象存放的值或者要转换成布尔值的值
```
<br/>
### 4、**Date**：处理日期和时间
```javascript
new Date();    //当前日期和时间
new Date(milliseconds);    //返回从1970年1月1日至今的毫秒数
new Date(dateString);
new Date(year, month, day, hours, minutes, seconds, milliseconds);
```

**- Date对象方法**
#### • `getDay()`：返回表示星期的某一天的数字 (0~6)
```javascript
dateObject.getDay();
```

#### • `getTime()`：返回距 1970 年 1 月 1 日之间的毫秒数
```javascript
dateObject.getTime();
```
<br/>
### 5、**Math**：执行数学任务
```javascript
var x = Math.PI;    //返回PI
var y = Math.sqrt(16);    //返回16的平方根
```

**- Math对象方法**
#### • `floor()`：返回小于或等于参数的最大整数
```javascript
Math.floor(x);

//*x：任意数值或表达式
```

#### • `round()`：把一个数字舍入为最接近的整数
```javascript
Math.round(x);

//*x：数字
```
<br/>
### 6、**Number**：原始数值的包装对象
```javascript
var myNum=new Number(value);
var myNum=Number(value);

//*value：要创建的数值或要转换成数字的值
```
<br/>
### 7、**String**：处理文本（字符串）
```javascript
new String(s);
String(s);

//*s：要存储在对象中或要转换成原始字符串的值
```

**- String对象方法**
#### • `match()`：在字符串内检索指定的值，或找到正则表达式的匹配
```javascript
stringObject.match(searchvalue);
stringObject.match(regexp);

//*searchvalue：规定要检索的字符串值
//*regexp：规定要匹配的模式的 RegExp 对象（如果该参数不是 RegExp 对象，则需要首先把它传递给 RegExp 构造函数，将其转换为 RegExp 对象）
```

#### • `replace()`：在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串
```javascript
stringObject.replace(regexp/substr, replacement);
stringObject.replace(/……/, "……");    //替换第一个匹配的子串
stringObject.replace(/……/g, "……");    //全局，替换所有匹配的子串

//*regexp/*substr：规定子字符串或要替换的模式的 RegExp 对象
//*replacement：一个字符串值，规定了替换文本或生成替换文本的函数
```
    $1$2……$99  与 regexp 中的第 1 到第 99 个子表达式相匹配的文本
    $&  与 regexp 相匹配的子串
    $`  位于匹配子串左侧的文本
    $'  位于匹配子串右侧的文本
    $$  直接量符号

#### • `split()`：把一个字符串分割成字符串数组并返回
```javascript
stringObject.split(separator,limit);    //参数皆为可选项
stringObject.split("");    //分割每个字符
stringObject.split("c");    //将某个字符转换为分隔符,
```
    *separator  字符串或正则表达式，从指定的地方分割字符串（string）
    *limit  限定返回的数组的最大长度（number）
<br/>
### 8、**RegExp**：正则表达式，匹配字符串的执行模式
```javascript
/pattern/attributes
new RegExp(pattern, attributes);

//*pattern：一个字符串，指定正则表达式的模式或其他正则表达式
```
    *attributes  一个可选的字符串，包含属性 "g"、"i" 和 "m"，分别用于指定全局匹配、区分大小写的匹配和多行匹配（如果 pattern 是正则表达式，而不是字符串，则必须省略该参数）

**- RegExp对象方法**
#### • `test()`：检测一个字符串是否匹配某个模式，并返回 true 或 false
```javascript
RegExpObject.test(string);

//*string：要检测的字符串
```

---

## Browser 对象
### 1、`history`：包含用户（在浏览器窗口中）访问过的 URL
**- history对象方法**
#### • `back()`：加载history列表中的前一个URL
```javascript
history.back();
```

#### • `forward()`：加载history列表中的下一个URL
```javascript
history.forward();
```

#### • `go()`：加载history列表中的某个具体页面
```javascript
history.go(number|URL);

//*number：要访问的URL在列表中的相对位置
//*URL：要访问的URL或子串
```
<br/>
### 2、`location`：包含有关当前 URL 的信息
**- location对象方法**
#### • `assign()`：加载一个新的文档
```javascript
location.assign(URL);
```
    *URL  要导航到的页面的URL

#### • `reload()`：重新加载当前文档
```javascript
location.reload(force);
```
    *force   true：始终从服务器重新加载  false|空：可以从浏览器缓存重新加载

#### • `replace()`：用一个新文档取代当前文档
```javascript
location.replace(newURL);
```
    *newURL  要导航到的页面的URL
<br/>
### 3、`window`：表示浏览器中打开的窗口
**- window对象方法**
#### • `alert()`：显示带有一条指定消息和一个OK按钮的警告框
```javascript
alert(message);

//*message：要显示的纯文本（非HTML文本）
```

#### • `close()`：关闭浏览器窗口
```javascript
window.close();
```

#### • `open()`：打开一个新的浏览器窗口或查找一个已命名的窗口
```javascript
window.open(URL,name,features,replace);    //参数皆为可选项
```
    *URL  声明要在新窗口中显示的文档的URL（url）
    *name 声明新窗口的名称（name）
    *features  声明新窗口要显示的标准浏览器的特征（features）
    *replace  （true - URL:替换浏览历史中的当前条目 false - URL:在浏览历史中创建新的条目）

---

## DOM 对象
### 1、`console`：提供访问浏览器调试模式的信息到控制台
**- console对象方法**
#### • `log()`：在控制台输出信息（该方法对于开发过程进行测试很有帮助）
```javascript
console.log(message);    //在浏览器中按下 F12 或 Ctrl+Shift+i 打开控制台，可利用此方法对当前页面的源代码进行JS调试
```
<br/>
### 2、`document`：从脚本中对HTML页面的所有元素进行访问
**- document对象方法**
#### • `getElementById()`：返回对拥有指定ID的第一个对象的引用
```javascript
document.getElementById(id);

//*id：元素ID属性值
```

#### • `getElementsByName()`：返回带有指定名称的对象的集合
```javascript
document.getElementsByName(name);

//*name：元素的名称
```

#### • `write()`：向文档写入HTML表达式或JavaScript代码
```javascript
document.write(exp1,exp2,exp3,……);
```
    *exp  要写入的输出流，多个参数可以列出，他们将按出现的顺序被追加到文档中
<br/>
### 3、**Element**：代表着一个 HTML 元素
**- element对象属性**
#### • `innerHTML`：设置或返回表格行的开始和结束标签之间的 HTML
```javascript
elementObject.innerHTML=text;

//*text：返回到elementObject中的HTML文本
```

**- element对象方法**
#### • `getAttribute()`：返回指定属性名的属性值
```javascript
elementObject.getAttribute(attributename)

//*attributename：需要获得属性值的属性名称
```
<br/>
### 4、**Event**：代表事件的状态，通常与函数结合使用
```javascript
eventObject.eventHandler=function(){……};
```

#### ① 鼠标事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onclick</code></td>
<td>当对象被点击时发生</td>
</tr>
<tr>
<td><code>oncontextmenu</code></td>
<td>当对象被右击时触发并打开上下文菜单</td>
</tr>
<tr>
<td><code>ondblclick</code></td>
<td>当对象被双击时发生</td>
</tr>
<tr>
<td><code>onmousedown</code>/<code>onmouseup</code></td>
<td>当在对象上按下/松开鼠标按键时发生</td>
</tr>
<tr>
<td><code>onmouseenter</code>/<code>onmouseleave</code></td>
<td>当鼠标指针移到/移出对象时发生（不冒泡）</td>
</tr>
<tr>
<td><code>onmouseover</code>/<code>onmouseout</code></td>
<td>当鼠标指针移到/移出对象时发生</td>
</tr>
<tr>
<td><code>onmousemove</code></td>
<td>当鼠标指针在对象内移动时发生</td>
</tr>
</tbody>
</table>

#### ② 键盘事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onkeydown</code></td>
<td>当键盘按键被按下时发生（不区分大小写）</td>
</tr>
<tr>
<td><code>onkeypress</code></td>
<td>当键盘按键被按下并松开时发生（仅识别数字/字母键）</td>
</tr>
<tr>
<td><code>onkeyup</code></td>
<td>当已按下的键盘按键被松开时发生</td>
</tr>
</tbody>
</table>

#### ③ 框架事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onabort</code></td>
<td>当图像的加载被中断时触发</td>
</tr>
<tr>
<td><code>onbeforeunload</code></td>
<td>当将要离开当前页面时触发</td>
</tr>
<tr>
<td><code>onerror</code></td>
<td>当加载外部文件发生错误时触发</td>
</tr>
<tr>
<td><code>onhashchange</code></td>
<td>当当前 URL 的锚 "#……" 发生改变时触发</td>
</tr>
<tr>
<td><code>onload</code></td>
<td>当页面或图像首次加载完成后触发（读取缓存不触发）</td>
</tr>
<tr>
<td><code>onunload</code></td>
<td>当离开当前页面时触发（无法缓存页面）</td>
</tr>
<tr>
<td><code>onpageshow</code></td>
<td>当页面或图像每次加载完成后触发</td>
</tr>
<tr>
<td><code>onpagehide</code></td>
<td>当离开当前页面时触发</td>
</tr>
<tr>
<td><code>onresize</code></td>
<td>当窗口或框架被调整大小时发生</td>
</tr>
<tr>
<td><code>onscroll</code></td>
<td>当文档被滚动时触发</td>
</tr>
</tbody>
</table>

#### ④ 表单事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onchange</code></td>
<td>当表单元素的内容改变时发生</td>
</tr>
<tr>
<td><code>onfocus</code></td>
<td>当对象获得焦点时发生</td>
</tr>
<tr>
<td><code>onblur</code></td>
<td>当对象失去焦点时发生</td>
</tr>
<tr>
<td><code>onfocusin</code></td>
<td>当元素即将获得焦点时触发（不冒泡）</td>
</tr>
<tr>
<td><code>onfocusout</code></td>
<td>当元素即将失去焦点时触发（不冒泡）</td>
</tr>
<tr>
<td><code>oninput</code></td>
<td>当用户输入时触发</td>
</tr>
<tr>
<td><code>onreset</code></td>
<td>当表单被重置后触发</td>
</tr>
<tr>
<td><code>onsearch</code></td>
<td>当向搜索域输入文本时触发</td>
</tr>
<tr>
<td><code>onselect</code></td>
<td>当文本框中的文本被选中时发生</td>
</tr>
<tr>
<td><code>onsubmit</code></td>
<td>当表单被提交时触发</td>
</tr>
</tbody>
</table>

#### ⑤ 剪贴板事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>oncopy</code></td>
<td>当用户拷贝元素的内容时触发</td>
</tr>
<tr>
<td><code>oncut</code></td>
<td>当用户剪切元素的内容时触发</td>
</tr>
<tr>
<td><code>onpaste</code></td>
<td>当用户粘贴元素的内容时触发</td>
</tr>
</tbody>
</table>

#### ⑥ 打印事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onafterprint</code></td>
<td>当页面已经开始打印时，或打印窗口已经关闭时触发</td>
</tr>
<tr>
<td><code>onbeforeprint</code></td>
<td>当页面即将开始打印时触发</td>
</tr>
</tbody>
</table>

#### ⑦ 拖动事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>ondragstart</code></td>
<td>当元素或者选取的文本开始拖动时触发（作用于拖动目标）</td>
</tr>
<tr>
<td><code>ondrag</code></td>
<td>当元素或者选取的文本正在拖动时触发（作用于拖动目标）</td>
</tr>
<tr>
<td><code>ondragend</code></td>
<td>当用户完成拖动时触发（作用于拖动目标）</td>
</tr>
<tr>
<td><code>ondragenter</code></td>
<td>当拖动对象进入有效的放置目标时触发（作用于放置目标）</td>
</tr>
<tr>
<td><code>ondragleave</code></td>
<td>当拖动对象离开放置目标时触发（作用于放置目标）</td>
</tr>
<tr>
<td><code>ondragover</code></td>
<td>当拖动对象在放置目标内拖动时触发（作用于放置目标）</td>
</tr>
<tr>
<td><code>ondrop</code></td>
<td>当拖动对象完成放置时触发（作用于放置目标）</td>
</tr>
</tbody>
</table>

#### ⑧ 多媒体事件
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>eventHandler</th>
<th>事件描述</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>onabort</code></td>
<td>当视频/音频终止加载时触发</td>
</tr>
<tr>
<td><code>onloadstart</code></td>
<td>当浏览器开始寻找指定视频/音频触发</td>
</tr>
<tr>
<td><code>ondurationchange</code></td>
<td>当视频/音频的时长发生变化时触发</td>
</tr>
<tr>
<td><code>onloadedmetadata</code></td>
<td>当指定视频/音频的元数据加载后触发</td>
</tr>
<tr>
<td><code>onloadeddata</code></td>
<td>当浏览器加载视频/音频当前帧时触发</td>
</tr>
<tr>
<td><code>onprogress</code></td>
<td>当浏览器下载指定的视频/音频时触发</td>
</tr>
<tr>
<td><code>oncanplay</code></td>
<td>当用户可以开始播放视频/音频时触发</td>
</tr>
<tr>
<td><code>oncanplaythrough</code></td>
<td>当视频/音频可以正常播放且无需停顿和缓冲时触发</td>
</tr>
<tr>
<td><code>onended</code></td>
<td>当视频/音频播放结束时触发</td>
</tr>
<tr>
<td><code>onerror</code></td>
<td>当视频/音频数据加载期间发生错误时触发</td>
</tr>
<tr>
<td><code>onpause</code></td>
<td>当视频/音频暂停时触发</td>
</tr>
<tr>
<td><code>onplay</code></td>
<td>当视频/音频开始播放时触发</td>
</tr>
<tr>
<td><code>onplaying</code></td>
<td>当视频/音频暂停或者在缓冲后准备重新开始播放时触发</td>
</tr>
<tr>
<td><code>onratechange</code></td>
<td>当视频/音频的播放速度发生改变时触发</td>
</tr>
<tr>
<td><code>onseeking</code></td>
<td>当用户开始重新定位视频/音频时触发</td>
</tr>
<tr>
<td><code>onseeked</code></td>
<td>当用户重新定位视频/音频的播放位置后触发</td>
</tr>
<tr>
<td><code>onstalled</code></td>
<td>当浏览器获取媒体数据但媒体数据不可用时触发</td>
</tr>
<tr>
<td><code>onsuspend</code></td>
<td>当浏览器读取媒体数据中止时触发</td>
</tr>
<tr>
<td><code>ontimeupdate</code></td>
<td>当视频/音频当前的播放位置发送改变时触发</td>
</tr>
<tr>
<td><code>onvolumechange</code></td>
<td>当视频/音频的音量发生改变时触发</td>
</tr>
<tr>
<td><code>onwaiting</code></td>
<td>当视频由于要播放下一帧而需要缓冲时触发</td>
</tr>
</tbody>
</table>

---

## HTML 对象
### 1、`style`：一个单独的样式声明
```javascript
document.getElementById("id").style.property="value";

//*property：CSS属性（需转换为camelCase命名）
//*value：设置对应的属性值
```

---

## JavaScript 语句
### 1、条件语句：基于不同的条件来执行不同的动作
#### • `if`：只有当指定条件为true时，使用该语句来执行代码
```javascript
if (条件) {
	只有当条件为 true 时执行的代码块
}
```

#### • `if……else`：在条件为true时执行代码，在条件为false时执行其他代码
```javascript
if (条件) {
	当条件为 true 时执行的代码块
}
else {
	当条件为 false 时执行的代码块
}
```

#### • `if……else if……else`：选择多个代码块之一来执行
```javascript
if (条件1) {
    当条件1为 true 时执行的代码块
}
else if (条件2) {
    当条件2为 true 时执行的代码块
}
else {
    当条件1和条件2都为 false 时执行的代码块
}
```

#### • `switch`：选择要执行的多个代码块之一
```javascript
switch (变量) {
    case 值1:
    若变量等于值1则执行的代码块
    break;
    case 值2:
    若变量等于值2则执行的代码块
    break;
    ……
    default:
    当匹配不存在时执行的代码块
}
```
```flow
st=>start: 开始
op1=>operation: 获取变量的值
cond1=>condition: 等于第一个case的值
sub1=>subroutine: 执行该case的代码块
sub2=>subroutine: 执行 `break;` 停止匹配
e=>end: 结束
cond2=>condition: 等于下一个case的值
op2=>operation: 所有case均不匹配
sub3=>subroutine: 执行default的代码块

st->op1->cond1
cond1(yes)->sub1->sub2->e
cond1(no)->cond2
cond2(yes)->sub1
cond2(no)->op2->sub3->e
```
<br/>
### 2、循环语句：将代码块执行指定的次数
#### • `for`：循环代码块一定的次数
```javascript
for (变量; 条件; 增值) {
    被执行的代码块
}
```
    *变量：在循环开始前执行（可选，可初始化任意或多个值）
    *条件：定义运行循环的条件（可选，若省略则需提供break）
    *增值：在循环已被执行之后执行（可选）
```flow
st=>start: 开始
op1=>operation: 获取变量的值
cond=>condition: 当条件为 `true`
sub=>subroutine: 执行代码块
op2=>operation: 变量增值
op3=>operation: 跳出循环（必须步骤）
e=>end: 结束

st->op1->cond
cond(yes)->sub->op2(left)->cond
cond(no)->op3->e
```

#### • `for……in`：循环遍历数组或者对象的属性
```javascript
for (变量 in 对象) {
    在此执行代码
}

//*变量：指定的变量，可以是数组元素或对象的属性
```

#### • `while`：当指定的条件为true时循环指定的代码块
```javascript
while (条件) {
    需要执行的代码
}
```

#### • `do……while`：先执行一次代码块，当条件为true时再重复这个循环
```javascript
do {
    需要执行的代码
}
while (条件);
```

---

## JavaScript 运算符
>**※** 建议在运算符前后都空一格
### 1、**算术**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center">符号</th>
        <th style="text-align:center">含义</th>
        <th style="text-align:center">示例（x=5）</th>
        <th style="text-align:center">结果</th>
        <th style="text-align:center">优先级</th>
    </tr>
    <tr>
        <td rowspan="2" style="text-align:center;vertical-align:middle;"><code>++</code></td>
        <td style="text-align:center;vertical-align:middle;">后置递增 ...++（先赋值后自增）</td>
        <td style="text-align:center;vertical-align:middle;">y=x++</td>
        <td style="text-align:center">y=5<br>x=6</td>
        <td style="text-align:center;vertical-align:middle;">1</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;">前置递增 ++...（先自增后赋值）</td>
        <td style="text-align:center;vertical-align:middle;">y=++x</td>
        <td style="text-align:center">x=6<br>y=6</td>
        <td style="text-align:center;vertical-align:middle;">2</td>
    </tr>
    <tr>
        <td rowspan="2" style="text-align:center;vertical-align:middle;"><code>--</code></td>
        <td style="text-align:center;vertical-align:middle;">后置递减 ...--（先赋值后自减）</td>
        <td style="text-align:center;vertical-align:middle;">y=x--</td>
        <td style="text-align:center">y=5<br>x=4</td>
        <td style="text-align:center;vertical-align:middle;">1</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;">前置递减 --...（先自减后赋值）</td>
        <td style="text-align:center;vertical-align:middle;">y=--x</td>
        <td style="text-align:center">x=4<br>y=4</td>
        <td style="text-align:center;vertical-align:middle;">2</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>**</code></td>
        <td style="text-align:center">幂</td>
        <td style="text-align:center">y=x**2</td>
        <td style="text-align:center">y=25</td>
        <td style="text-align:center">3</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>*</code></td>
        <td style="text-align:center">乘</td>
        <td style="text-align:center">y=x*3</td>
        <td style="text-align:center">y=15</td>
        <td style="text-align:center">4</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>/</code></td>
        <td style="text-align:center">除</td>
        <td style="text-align:center">y=x/2</td>
        <td style="text-align:center">y=2.5</td>
        <td style="text-align:center">4</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>%</code></td>
        <td style="text-align:center">求余（保留整数）</td>
        <td style="text-align:center">y=x%3</td>
        <td style="text-align:center">y=2</td>
        <td style="text-align:center">4</td>
    </tr>
    <tr>
        <td rowspan="2" style="text-align:center;vertical-align:middle;"><code>+</code></td>
        <td style="text-align:center">加</td>
        <td style="text-align:center">y=x+3</td>
        <td style="text-align:center">y=8</td>
        <td rowspan="2" style="text-align:center;vertical-align:middle;">5</td>
    </tr>
    <tr>
        <td style="text-align:center">连接</td>
        <td style="text-align:center">"5"+"5"</td>
        <td style="text-align:center">55</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>-</code></td>
        <td style="text-align:center">减</td>
        <td style="text-align:center">y=x-3</td>
        <td style="text-align:center">y=2</td>
        <td style="text-align:center">5</td>
    </tr>
</table>
<br>
### 2、**二进制位**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center;vertical-align:middle;">符号</th>
        <th style="text-align:center;vertical-align:middle;">含义</th>
        <th style="text-align:center;vertical-align:middle;width:9rem;">示例</th>
        <th style="text-align:center;vertical-align:middle;">转换</th>
        <th style="text-align:center;vertical-align:middle;">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>~</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制位非（占位数值取反）</td>
        <td style="text-align:center;vertical-align:middle;">~9=6</td>
        <td style="text-align:right">9→00001001<br>6←00000110</td>
        <td style="text-align:center;vertical-align:middle;">2</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>&lt;&lt;</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制数左移n位</td>
        <td style="text-align:center">9&lt;&lt;3=72<br>（左移3位）</td>
        <td style="text-align:right">9→00001001<br>72←01001000</td>
        <td style="text-align:center;vertical-align:middle;">6</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>&gt;&gt;</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制数带符号右移n位</td>
        <td style="text-align:center">21&gt;&gt;3=2<br>（带符号右移3位）</td>
        <td style="text-align:right;">21→00010101<br>2←00000010</td>
        <td style="text-align:center;vertical-align:middle;">6</td>
    </tr>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>&gt;&gt;&gt;</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制数无符号右移n位</td>
        <td style="text-align:center">21&gt;&gt;&gt;3=2<br>（无符号右移3位）</td>
        <td style="text-align:right;">21→00010101<br>2←00000010</td>
        <td style="text-align:center;vertical-align:middle;">6</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>&</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制位与（仅当对应位均为1时，结果位才为1）</td>
        <td style="text-align:center;vertical-align:middle;">9&21=1</td>
        <td style="text-align:right">9→00001001<br>21→00010101<br>1←00000001</td>
        <td style="text-align:center;vertical-align:middle;">9</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>^</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制位异或（对应位相异结果位为1，相同为0）</td>
        <td style="text-align:center;vertical-align:middle;">9^21=28</td>
        <td style="text-align:right">9→00001001<br>21→00010101<br>28←00011100</td>
        <td style="text-align:center;vertical-align:middle;">10</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>|</code></td>
        <td style="text-align:center;vertical-align:middle;">二进制位或（当对应位有1时，结果位即为1）</td>
        <td style="text-align:center;vertical-align:middle;">9|21=29</td>
        <td style="text-align:right">9→00001001<br>21→00010101<br>29←00011101</td>
        <td style="text-align:center;vertical-align:middle;">11</td>
    </tr>
</table>
<br>
### 3、**逻辑**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center;vertical-align:middle;">符号</th>
        <th style="text-align:center;vertical-align:middle;">含义</th>
        <th style="text-align:center;vertical-align:middle;">示例</th>
        <th style="text-align:center;vertical-align:middle;">结果</th>
        <th style="text-align:center;vertical-align:middle;">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;"><code>!</code></td>
        <td style="text-align:center">逻辑非（取反）</td>
        <td style="text-align:center">!true</td>
        <td style="text-align:center">false</td>
        <td style="text-align:center">2</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>&&</code></td>
        <td style="text-align:center;vertical-align:middle;">逻辑与（仅当都为truthy时，结果才为truthy）</td>
        <td style="text-align:center">true&&true<br>true&&false</td>
        <td style="text-align:center">true<br>false</td>
        <td style="text-align:center;vertical-align:middle;">12</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>||</code></td>
        <td style="text-align:center;vertical-align:middle;">逻辑或（当有truthy时，结果即为truthy）</td>
        <td style="text-align:center">true||false<br>false||false</td>
        <td style="text-align:center">true<br>false</td>
        <td style="text-align:center;vertical-align:middle;">13</td>
    </tr>
</table>
<br>
### 4、**比较**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center">符号</th>
        <th style="text-align:center">含义</th>
        <th style="text-align:center">示例（x=5）</th>
        <th style="text-align:center">结果</th>
        <th style="text-align:center">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&gt;</code></td>
        <td style="text-align:center">大于</td>
        <td style="text-align:center">x&gt;8</td>
        <td style="text-align:center">false</td>
        <td style="text-align:center">7</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&lt;</code></td>
        <td style="text-align:center">小于</td>
        <td style="text-align:center">x&lt;8</td>
        <td style="text-align:center">true</td>
        <td style="text-align:center">7</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&gt;=</code></td>
        <td style="text-align:center">大于或等于</td>
        <td style="text-align:center">x&gt;=8</td>
        <td style="text-align:center">false</td>
        <td style="text-align:center">7</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&lt;=</code></td>
        <td style="text-align:center">小于或等于</td>
        <td style="text-align:center">x&lt;=8</td>
        <td style="text-align:center">true</td>
        <td style="text-align:center">7</td>
    </tr>
</table>
<br>
### 5、**相等**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center">符号</th>
        <th style="text-align:center">含义</th>
        <th style="text-align:center">示例（x=5）</th>
        <th style="text-align:center">结果</th>
        <th style="text-align:center">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;"><code>==</code></td>
        <td style="text-align:center">等于</td>
        <td style="text-align:center">x==8</td>
        <td style="text-align:center">false</td>
        <td style="text-align:center">8</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>===</code></td>
        <td style="text-align:center;vertical-align:middle;">全等（值和类型）</td>
        <td style="text-align:center">x===5<br>x==="5"</td>
        <td style="text-align:center">true<br>false</td>
        <td style="text-align:center;vertical-align:middle;">8</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>!=</code></td>
        <td style="text-align:center">不等于</td>
        <td style="text-align:center">x!=8</td>
        <td style="text-align:center">true</td>
        <td style="text-align:center">8</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>!==</code></td>
        <td style="text-align:center;vertical-align:middle;">不全等（值和类型）</td>
        <td style="text-align:center">x!==3<br>x!=="5"</td>
        <td style="text-align:center">true<br>true</td>
        <td style="text-align:center;vertical-align:middle;">8</td>
    </tr>
</table>
<br>
### 6、**条件**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center">符号</th>
        <th style="text-align:center">含义</th>
        <th style="text-align:center">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;"><code>condition ? value1 : value2</code></td>
        <td style="text-align:center">条件为ture时赋值1，否则赋值2</td>
        <td style="text-align:center">14</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>condition ? expr1 : expr2</code></td>
        <td style="text-align:center">条件为ture时运行1，否则运行2</td>
        <td style="text-align:center">14</td>
    </tr>
</table>
<br>
### 7、**赋值**运算
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center;vertical-align:middle;">符号</th>
        <th style="text-align:center;vertical-align:middle;">含义</th>
        <th style="text-align:center;vertical-align:middle;width:8rem;">示例</th>
        <th style="text-align:center;vertical-align:middle;">等价于</th>
        <th style="text-align:center;vertical-align:middle;">优先级</th>
    </tr>
    <tr>
        <td style="text-align:center;"><code>=</code></td>
        <td style="text-align:center">赋值</td>
        <td style="text-align:center">x=5</td>
        <td style="text-align:center">x=5</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>+=</code></td>
        <td style="text-align:center">赋值和</td>
        <td style="text-align:center">x+=y</td>
        <td style="text-align:center">x=x+y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>-=</code></td>
        <td style="text-align:center">赋值差</td>
        <td style="text-align:center">x-=y</td>
        <td style="text-align:center">x=x-y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>*=</code></td>
        <td style="text-align:center">赋值积</td>
        <td style="text-align:center">x*=y</td>
        <td style="text-align:center">x=x*y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>/=</code></td>
        <td style="text-align:center">赋值商</td>
        <td style="text-align:center">x/=y</td>
        <td style="text-align:center">x=x/y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>%=</code></td>
        <td style="text-align:center">赋值余（保留整数）</td>
        <td style="text-align:center">x%=y</td>
        <td style="text-align:center">x=x%y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&lt;&lt;=</code></td>
        <td style="text-align:center">赋值左移</td>
        <td style="text-align:center">x&lt;&lt;=y</td>
        <td style="text-align:center">x=x&lt;&lt;y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&gt;&gt;=</code></td>
        <td style="text-align:center">赋值带符号右移</td>
        <td style="text-align:center">x&gt;&gt;=y</td>
        <td style="text-align:center">x=x&gt;&gt;y</td>
        <td style="text-align:center">15</td>
    </tr>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&gt;&gt;&gt;=</code></td>
        <td style="text-align:center">赋值无符号右移</td>
        <td style="text-align:center">x&gt;&gt;=y</td>
        <td style="text-align:center">x=x&gt;&gt;y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>&=</code></td>
        <td style="text-align:center">赋值与</td>
        <td style="text-align:center">x&=y</td>
        <td style="text-align:center">x=x&y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>|=</code></td>
        <td style="text-align:center">赋值或</td>
        <td style="text-align:center">x|=y</td>
        <td style="text-align:center">x=x|y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>^=</code></td>
        <td style="text-align:center">赋值异或</td>
        <td style="text-align:center">x^=y</td>
        <td style="text-align:center">x=x^y</td>
        <td style="text-align:center">15</td>
    </tr>
    <tr>
        <td style="text-align:center;vertical-align:middle;"><code>[]=[]<br>{}={}</code></td>
        <td style="text-align:center;vertical-align:middle;">解构赋值（给数组或对象中的元素赋值）</td>
        <td style="text-align:center">[a, b] = [1, 2]<br>{a, b} = {a:1, b:2}</td>
        <td style="text-align:center;vertical-align:middle;">a=1<br>b=2</td>
        <td style="text-align:center;vertical-align:middle;">15</td>
    </tr>
</table>

---
