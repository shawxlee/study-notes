# CSS 选择器|层叠|媒体查询参考手册
Cascading Style Sheets - 层叠样式表

---

## CSS选择器
### 1、**元素**选择器：文档内的元素就是最基本的选择器
`元素 {……}` （针对多个元素，共同作用）
```css
h1 {color: red;}   /* 文档内所有h1元素都被定义为红色 */
```
<br/>
### 2、**类**选择器：允许以一种独立于文档元素的方式来指定样式
`.类 {……}` / `元素.类 {……}` / `.类1.类2 {……}` （针对多个元素，共同作用）
- `class="class_name"` 规定元素的类名（自定义，不可用数字开头，多个类名用空格隔开）
```html
<head>
    <style type="text/css">          <!-- Step1：定义类选择器 -->
        .important {color: red;}
        p.secondary {color: blue;}
        .secondary.special {font-weight: bold;}
    </style>
</head>

<body>                               <!-- Step2：向元素添加类 -->
    <h1 class="important">我是红色！</h1>
    <p class="important">我是红色！</p>
    <p class="secondary special">我是蓝色且字体加粗！</p>
    <p class="secondary normal special">我是蓝色且字体加粗！</p>
</body>
```
<br/>
### 3、**ID**选择器：为标有特定id的HTML元素指定样式
`#ID {……}` （针对特定元素，独立作用）
- `id="idName"` 规定HTML元素的唯一的id名（自定义，不可用数字开头）
```html
<head>
    <style type="text/css">     <!-- Step2：向id选择器添加样式 -->
        #blueText {color: blue;}
    </style>
</head>

<body>                            <!-- Step1：定义唯一的id属性 -->
    <p id="blueText">只有我是蓝色！</p>
</body>
```
<br/>
### 4、**属性**选择器：根据元素的属性及属性值来选择元素
#### • 简单属性选择：选择有某个属性的元素，而不论属性值是什么
`[属性] {……}` / `元素[属性] {……}` / `元素[属性1][属性2] {……}` （针对多个元素，共同作用）
```html
<head>
    <style type="text/css">
        [title] {color: red;}   /* 包含title属性的所有元素变红 */
        a[href] {color: blue;}   /* 包含href属性的所有a元素变蓝 */
        a[title][href] {color: yellow;}   /* 同时包含title和href属性的所有a元素变黄 */
    </style>
</head>

<body>
    <h1 title="Hello world">我是红色！</h1>
    <a href="http://w3school.com.cn">我是蓝色！</a>
    <a title="W3School Home" href="http://w3school.com.cn">我是黄色！</a>
</body>
```
#### • 具体属性值选择：只选择有特定属性值的元素，完全匹配
`元素[属性=值] {……}` / `元素[属性1=值][属性2=值] {……}` （针对特定元素，独立作用）
```html
<head>
    <style type="text/css">
        p[class=important warning] {color: red;}
        a[title=W3School][target=_top] {color: blue;}
    </style>
</head>

<body>
    <p class="important warning">我是红色！</p>
    <a href="http://w3school.com.cn" title="W3School" target="_blank"></a>
    <a href="http://w3school.com.cn" title="W3School" target="_top">我是蓝色！</a>
</body>

<!-- 选择器与文档中的属性值必须完全匹配 -->
```
#### • 部分属性值选择：根据属性值中的某个词进行选择，不完全匹配
`元素[属性~=值1] {……}` （针对特定元素，独立作用）
```html
<head>
    <style type="text/css">
        p[class~=important] {color: red;}
        img[title~=Figure] {color: blue;}
    </style>
</head>

<body>
    <p class="important warning">我是红色！</p>
    <p class="important">我是红色！</p>
    <img title="Figure 1" src="/i/figure-1.gif"/>我是蓝色！
    <img title="Figure 2" src="/i/figure-2.gif"/>我是蓝色！
</body>
```
#### • 特定属性值选择：选择属性等于指定值或以该值开头的所有元素
`元素[属性|=值] {……}` （针对特定元素，独立作用）
```html
<head>
    <style type="text/css">
        [lang|=en] {color: red;}
    </style>
</head>

<body>
    <p lang="en">Hello我是红色！</p>
    <p lang="en-us">Greetings我是红色！</p>
    <p lang="cy-en">Jrooana</p>
    <p lang="fr">Bonjour</p>
</body>

<!-- 常用于匹配语言值 -->
```
    ·子串匹配属性选择器（以"def"为例）：
    [属性^="def"]  选择属性值以def开头的所有元素
    [属性$="def"]  选择属性值以def结尾的所有元素
    [属性*="def"]  选择属性值中包含子串def的所有元素
<br/>
### 5、**后代**选择器：选择作为某元素后代的元素
`元素 后代元素 {……}` （针对所有后代元素，共同作用）
```html
<head>
    <style type="text/css">
        p em {color: red;}  /* 所有p元素下的所有后代em元素都变红 */
    </style>
</head>

<body>
    <p>包含<em>一代子元素是红色！</em>的一段文本</p>
    <p>包含<strong>一代子元素<em>二代子元素是红色！</em>的</strong>一段文本</p>
</body>
```
<br/>
### 6、**子元素**选择器：只能选择作为某元素子元素的元素
`元素>子元素 {……}`（针对一代子元素，共同作用）
```html
<head>
    <style type="text/css">
        p>em {color: red;}   /* 所有p元素下的一代em子元素变红 */
    </style>
</head>

<body>
    <p>包含<em>一代子元素是红色！</em>的一段文本</p>
    <p>包含<strong>一代子元素<em>二代子元素</em>的</strong>一段文本</p>
</body>
```
<br/>
### 7、**相邻兄弟**选择器：匹配同一父元素下指定元素1之后紧跟的第一个元素2
`元素1+元素2 {……}`（针对特定元素，独立作用）
```html
<head>
    <style type="text/css">
        h1+p {color: red;}
        li+li {color: blue;}
    </style>
</head>

<body>
    <h1>This is a heading.</h1>
    <p>This is paragraph1.我是红色！</p>
    <p>This is paragraph2.</p>
    <ul>
        <li>List item 1.</li>
        <li>List item 2.我是蓝色！</li>
    </ul>
    <ol>
        <li>List item 1.</li>
        <li>List item 2.我是蓝色！</li>
        <li>List item 3.我是蓝色！</li>
    </ol>
</body>
```
<br/>
### 8、**普通兄弟**选择器：匹配同一父元素下指定元素1后面的所有元素2（包括相邻及不相邻）
`元素1~元素2 {……}`（针对多个元素，共同作用）
```html
<head>
    <style type="text/css">
        a~p {color: red;}
    </style>
</head>

<body>
    <h1>This is a heading.</h1>
    <p>This is paragraph1.</p>
    <a href="/index.html" target="_blank">W3Sschool</a>
    <p>This is paragraph2.我是红色！</p>
    <ol>
        <li>List item 1</li>
        <li>List item 2</li>
        <li>List item 3</li>
    </ol>
    <p>This is paragraph3.我是红色！</p>
</body>
```
<br/>
### 9、**伪类**选择器：向某些选择器添加特殊的效果，根据用户行为发生变化
`选择器:伪类 {……}` / `选择器.类:伪类 {……}`（针对特定元素，独立作用）

#### • 锚伪类
`:link {……}` 向未访问的链接添加样式
`:visited {……}` 向访问过的链接添加样式
`:hover {……}` 当鼠标移到元素上时添加样式
`:active {……}` 当元素被激活时添加样式
```html
<head>
    <style type="text/css">
        a:link {color: blue;}
        a:visited {color: red;}
        a:hover {color: yellow;}
        a:active {color: green;}
    </style>
</head>

<body>
    <a href="/index.html" target="_blank">这是一个链接</a>
</body>

<!-- 书写顺序：link → visited → hover → active -->
```
#### • lang伪类
`:lang(语言代码|代码前缀) {……}` 匹配带有指定语言编码或前缀的元素
- `lang="language-code"` 规定元素内容的语言（[语言代码参考手册][1]）
```html
<head>
    <style type="text/css">
        p:lang(en) {color: red;}
    </style>
</head>

<body>
    <p lang="en">English我是红色！</p>
    <p lang="fr">French</p>
    <p lang="en-us">American我是红色！</p>
</body>

<!-- 元素的语言信息必须包含在文档中或与文档关联，不能从CSS指定 -->
```
#### • 其他伪类

    *:first-child  匹配作为某父元素下第一个子元素的*
    *:last-child  匹配作为某父元素下最后一个子元素的*
    *:nth-child(数字|关键字|公式)  匹配作为某父元素下第n个子元素的*
    *:nth-last-child(数字|关键字|公式)  匹配作为某父元素下倒数第n个子元素的*
    *:only-child  匹配作为某父元素下唯一一个子元素的*
    
    *:first-of-type  匹配同一父元素下所有*元素中的第一个
    *:last-of-type  匹配同一父元素下所有*元素中的最后一个
    *:nth-of-type(数字|关键字|公式)  匹配同一父元素下所有*元素中的第n个
    *:nth-last-of-type(数字|关键字|公式)  匹配同一父元素下所有*元素中倒数第n个
    *:only-of-type  匹配同一父元素下的唯一一个*元素
    
    *:checked  当元素*被选中时设置指定样式（仅用于单选按钮或复选框）
    *:focus  当元素*获得焦点时设置指定样式（主要用于接收用户输入的元素）
    
    *:enabled  匹配每个启用的元素*（主要用于表单元素）
    *:disabled  匹配每个禁用的元素*（主要用于表单元素）
    
    *:in-range  当元素*的值在指定区间时设置指定样式
    *:out-of-range  当元素*的值在指定区间以外时设置指定样式
    
    *:optional  当表单元素*是可选项时设置指定样式
    *:required  当表单元素*是必填项时设置指定样式
    
    *:read-only  选取设置了readonly属性的只读元素*
    *:read-write  匹配可读且可写的元素*
    
    *:valid  当表单元素*的值合法时设置指定样式
    *:invalid  当表单元素*的值非法时设置指定样式
    
    *:empty  选择所有没有任何子级的元素*
    *:target  选取当前活动的目标元素*（其id与当前URL片段匹配）
    :not(选择器)  匹配所有非指定选择器的元素
    :root  匹配文档的根元素（在HTML中根元素始终是HTML元素）

<br/>
### 10、**伪元素**选择器：向某些选择器设置特殊效果，伪造文档中没有的元素
`选择器::伪元素 {……}` / `选择器.类::伪元素 {……}` （针对特定元素，独立作用）
#### • 添加文本效果
`::first-letter {……}` 向文本的第一个字母添加特殊样式（只能用于块级元素）
    
    {font; color; background; margin; padding; border; text-decoration; vertical-align; text-transform; line-height; float; clear}

`::first-line {……}` 向文本的首行添加特殊样式（只能用于块级元素）

    {font; color; background; word-spacing; letter-spacing; text-decoration; vertical-align; text-transform; line-height; clear}

```html
<head>
    <style type="text/css">
        p::first-letter {
            color: #ff0000;
            font-size: xx-large;
        }
        p::first-line {
            color: #0000ff;
            font-variant: small-caps;
        }
    </style>
</head>

<body>
    <p>You can combine the :first-letter and :first-line pseudo-elements to add a special effect to the first letter and the first line of a text!</p>
</body>
```
![效果示例][2]

#### • 插入新内容
`::before {……}` 在元素头部添加内容
`::after {……}` 在元素尾部添加内容

    {content: "字符串"}  向元素内容中添加字符串
    {content: "(" attr(属性) ")"}  调用属性的值并打印在结果中
    {content: url(文件路径)}  插入外部资源文件
    {content: counter(计数器名 | 计数器名,标记类型)}  插入序号或有序标记
    {content: counters(计数器名,字符串 | 计数器名,字符串,标记类型)}  嵌套计数
```html
<head>
    <style type="text/css">
        h1::before {content: "123";}
        a::after {content: "(" attr(href) ")";}
        h2::after {content: url(/i/w3school_logo_white.gif);}
    </style>
</head>

<body>
    <h1>：在本行内容前插入文本</h1>
    <a href="http://www.w3school.com.cn">W3School</a>
    <h2>在本行内容后插入图片：</h2>
</body>

<!-- ::before和::after对替换元素应用无效 -->
```
![效果示例][3]

```html
<head>
    <style type="text/css">
        h1 {
            counter-reset: countA;   /* 默认起始值为0 */
            counter-increment: countA;   /* 默认增量为1 */
        }
        h1::before {content: counter(countA);}   /* 默认插入数字编号 */
        
        h2 {
            counter-reset: countB 1;   /* 设定起始值为1 */
            counter-increment: countB 2;   /* 设定增量为2 */
        }
        h2::before {content: counter(countB, lower-roman);}   /* 插入小写罗马编号 */
        
        h3 {
            counter-reset: countC 3 countD 4;/* 命名多个计数器 */
            counter-increment: countC countD -1; /* 负值为递减 */
        }
        h3::before {content: counter(countC);}
        h3::after {content: counter(countD); counter-increment: countD -1;}   /* 叠加一次增量为-2 */
    </style>
</head>

<body>
    <h1>：本行内容前将出现序号1</h1>
    <h2>：本行内容前将出现序号ⅲ</h2>
    <h3>：本行内容前是序号4后是序号2：</h3>
</body>

<!-- ::before和::after对替换元素应用无效 -->
```
![效果示例][4]

```html
<head>
    <style type="text/css">
        .reset {counter-reset: _count; padding-left: 20px;}
        /* 计数源只能设在各级父元素.reset上；设定padding-left的值可叠加各级缩进距离以形成阶梯效果 */
        .count::before {content: counters(_count, '-')'. '; counter-increment: _count;}
    </style>
</head>

<body>
    <div class="reset">
        <div class="count">一级标题第1项
            <div class="reset">
                <div class="count">二级标题第1-1项</div>
                <div class="count">二级标题第1-2项
                    <div class="reset">
                        <div class="count">三级标题1-2-1项</div>
                        <div class="count">三级标题1-2-2项</div>
                        <div class="count">三级标题1-2-3项</div>
                    </div>
                </div>
                <div class="count">二级标题第1-3项</div>
            </div>
        </div>
        <div class="count">一级标题第2项</div>
        <div class="count">一级标题第3项</div>
            <div class="reset">
                <div class="count">二级标题第3-1项</div>
            </div>
    </div>
</body>

<!-- ::before和::after对替换元素应用无效 -->
```
![效果示例][5]

#### • 匹配选中内容
`::selection {……}` 匹配元素中被用户选中或高亮的部分

    {color; background; cursor; outline}
```html
<head>
    <style type="text/css">
        ::selection {color: yellow;}
        a::selection {background: grey;}
    </style>
</head>

<body>
    <h1>尝试选中文本的某些部分</h1>
    <a href="http://www.runoob.com/">这是一条链接</a>
</body>
```
![效果示例][6]

<br/>
### 11、**分组**选择器：将任意多个相同样式的选择器分组在一起
`选择器1, 选择器2, ……, 选择器n {……}` （针对多个元素，共同作用）
```css
h1, p {color: red;}   /* 所有h1、p元素都变红 */
.important, p::first-letter {font-size: xx-large;}   /* 所有类名为important的元素、所有p元素的首字母都加大字号 */
```
<br/>
### 12、**通配符**选择器：选择所有元素
`* {……}` （针对所有元素，共同作用）
```css
* {color: red;}      /* 文档内所有元素都被定义为红色 */
```

---

## CSS层叠
层叠是CSS的一个基本特征，定义了如何合并来自多个源的属性值
### 1、CSS声明的源：挑选CSS声明来给属性设置正确的值
• **用户代理**：浏览器的基本样式表，给网页设置默认样式，不可被检测
• **网页作者**：定义多个样式表，构成网站的主题
• **读者**：作为浏览器的用户，可以使用自定义样式表定制使用体验
<br/>
### 2、层叠顺序：找出要应用到每个文档元素的每个属性上的值
#### Step1、过滤来自不同源的全部规则，保留匹配到指定元素上的规则

#### Step2、依据重要性和来源对这些规则进行优先级排序：
<table>
   <thead>
    <tr style="background: #555555; color: #fff;">
     <th>+重要性</th>
     <th>+来源</th>
     <th>=优先级</th>
    </tr>
   </thead>
   <tbody>
    <tr>
     <td><code>!important</code></td>
     <td>读者</td>
     <td>1</td>
    </tr>
    <tr>
     <td><code>!important</code></td>
     <td>网页作者</td>
     <td>2</td>
    </tr>
    <tr>
     <td></td>
     <td>CSS动画</td>
     <td>3</td>
    </tr>
    <tr>
     <td>普通</td>
     <td>网页作者</td>
     <td>4</td>
    </tr>
    <tr>
     <td>普通</td>
     <td>读者</td>
     <td>5</td>
    </tr>
    <tr>
     <td><code>!important</code></td>
     <td>用户代理</td>
     <td>6</td>
    </tr>
    <tr>
     <td>普通</td>
     <td>用户代理</td>
     <td>7</td>
    </tr>
   </tbody>
  </table>

#### Step3、若优先级相等，则再比较规则的特殊性（a,b,c,d）进行排序：
<table>
   <thead>
    <tr style="background: #555555; color: #fff;">
     <th>选择器类型</th>
     <th>特殊性</th>
     <th>优先级</th>
    </tr>
   </thead>
   <tbody>
    <tr>
     <td>内联样式（a）</td>
     <td>+1，0，0，0</td>
     <td>1</td>
    </tr>
    <tr>
     <td>ID选择器（b）</td>
     <td>0，+1，0，0</td>
     <td>2</td>
    </tr>
    <tr>
     <td>类/属性/伪类选择器（c）</td>
     <td>0，0，+1，0</td>
     <td>3</td>
    </tr>
    <tr>
     <td>元素/伪元素选择器（d）</td>
     <td>0，0，0，+1</td>
     <td>4</td>
    </tr>
    <tr>
     <td>通配符选择器（0）</td>
     <td>0，0，0，0</td>
     <td>5</td>
    </tr>
    <tr>
     <td>结合符选择器/从父元素继承</td>
     <td>无</td>
     <td>6</td>
    </tr>
   </tbody>
  </table>
>**比较方法：**统计每个规则中每种选择器的数量，在对应的特殊性上加成 → 将这些规则的特殊性从左向右依次比较，加成值越大的优先级越高

>★ 可以多用id选择器以增加权重，但要尽量减少一个规则中选择器的数量

#### Step4、若优先级仍相等，则后声明的规则会覆盖先声明的规则
<br/>
### 3、`!important` ：使这个属性及所在规则获得更大的权重
```css
.example {
    color: red !important;   /* !important必须写在末尾的分号前 */
}
.container .example {
    color: blue;
}

/* 若只比较特殊性，第二个规则的权重大于第一个，但因为第一个规则添加了!important，所以权重逆袭了，元素将被渲染为红色 */
```

```css
.example {margin: 0 !important;}   /* 一个简写属性添加!important，等价于展开的每个属性都添加了!important */
.example {
    margin-top: 0 !important; 
    margin-right: 0 !important; 
    margin-bottom: 0 !important; 
    margin-left: 0 !important;
}
```

#### • `!important` 使用场合及限制
P1: **永不使用** - 非到万不得已不要用!important
P2: **用户帮助** - 允许用户根据自己的需求添加!important以修改样式
P3: **紧急修复** - 在无法调试的浏览器上快速修复CSS bug，之后再用完整的解决方案替换掉线上的!important部分
P4: **开发者调试** - 使用Firebug或其他开发者工具进行调试时，可以给已经被覆盖的样式添加!important以重新启用
P5: **避免覆盖** - 开发者写好!important以避免用户修改或生成内容覆盖样式
P6: **独立页面** - 如果需要创建一个独一无二的页面，可以利用!important轻松覆盖默认的样式而不必担心原本的权重
<br/>
### 4、CSS继承：子元素可以从父元素继承特定的CSS属性
#### • 无法传递给后代的属性
元素框属性：`display` `overflow`
尺寸属性：`width` `height` `min-` `max-` `size`
边框属性：`border` `padding` `margin` `outline`
背景属性：`background`
定位属性：`float` `clear` `position` `top` `right` `bottom` `left` `clip` `z-index`
插入属性：`content` `counter-` `page-`
文本属性：`vertical-align` `text-decoration`
听觉属性：`pause` `cue` `play-`

#### • 不能从父元素继承的属性
`<a>`的颜色和下划线
`<h1>`~`<h6>`的字体大小

#### • 强制从父元素继承：`inherit`
```html
<head>
    <style type="text/css">
        div {
	        color: red;
        }
        .aColor a {
	        color: inherit;   /* 强制元素从父元素继承color属性 */
	    }
    </style>
</head>

<body>
    <div>
        <a href="https://www.runoob.com/">我是普通颜色的链接</a>
    </div>
    
    <div class="aColor">
        <a href="https://www.runoob.com/">我是继承红色的链接</a>
    </div>
</body>
```
![效果示例][7]

---

## CSS高级样式表
### 1、内联样式：将css样式写在原文档标签的`style`属性内
```html
<body>
    <p style="color:red;">这段文字是红色的</p>
</body>
```

### 2、内部样式表：将css样式写在原文档的`<style>`标签内
```html
<head>
    <style type="text/css">
        h1 {color:red;}
        p {color:blue;}
    </style>
</head>
```

### 3、外部样式表：将css样式单独保存为`.css`文件，在HTML文档中引入
• **公共样式表**：不同的文档可引入同一个样式表
• **独立样式表**：除公共样式之外，每个文档可单独修改
```html
<head>
    <link rel="stylesheet" type="text/css" href="common.css"/>
    <link rel="stylesheet" type="text/css" href="private.css"/>
</head>

<!-- 书写顺序：先公后私 -->
```

---

## CSS媒体查询
### 1、屏幕尺寸
@media查询可以针对不同的屏幕尺寸设置不同的样式，特别用于响应式页面
#### • 内部样式表
`@media (媒体功能) {选择器 {……}}`
`@media (媒体功能1) and (媒体功能2) {选择器 {……}}`
```html
<head>
    <style type="text/css">
        p {color:black;}      ——默认样式写在媒体查询之前
        @media (min-width:701px) and (max-width:1100px) {p {color:red;}}
        @media (max-width:700px) {p {color:blue;}}
    </style>
</head>

<body>
    <p>
    文档内容默认为黑色（最大值时）；
    当701px≤页面宽度≤1100px时，文档内容变为红色（中间值时）；
    当页面宽度≤700px时，文档内容变为蓝色（最小值时）。
    </p>
</body>
```

#### • 链接外部样式表
`<link …… media="(媒体功能) ……/>"`
```html
<head>
    <link rel="stylesheet" type="text/css" href="外部样式1.css"/>
    <link rel="stylesheet" type="text/css" media="(max-width:900px)" href="外部样式2.css"/>
</head>

<body>
    <p>
    文档内容默认应用样式1（最大值时）；
    当页面宽度≤900px时，应用样式2（最小值时）。
    </p>
</body>
```

    aspect-ratio  输出设备中的页面可见区域宽度与高度的比率
    color  输出设备每一组彩色原件的个数
    color-index  在输出设备的彩色查询表中的条目数
    device-aspect-ratio  输出设备的屏幕可见宽度与高度的比率
    device-height  输出设备的屏幕可见高度
    device-width  输出设备的屏幕可见宽度
    grid  查询输出设备是否使用栅格或点阵
    height  输出设备中的页面可见区域高度
    max-aspect-ratio  输出设备的屏幕可见宽度与高度的最大比率
    max-color  输出设备每一组彩色原件的最大个数
    max-color-index  在输出设备的彩色查询表中的最大条目数
    max-device-aspect-ratio  输出设备的屏幕可见宽度与高度的最大比率
    max-device-height  输出设备的屏幕可见的最大高度
    max-device-width  输出设备的屏幕最大可见宽度
    max-height  输出设备中的页面最大可见区域高度
    max-monochrome  在一个单色框架缓冲区中每像素包含的最大单色原件个数
    max-resolution  设备的最大分辨率
    max-width  输出设备中的页面最大可见区域宽度
    min-aspect-ratio  输出设备中的页面可见区域宽度与高度的最小比率
    min-color  输出设备每一组彩色原件的最小个数
    min-color-index  在输出设备的彩色查询表中的最小条目数
    min-device-aspect-ratio  输出设备的屏幕可见宽度与高度的最小比率
    min-device-width  输出设备的屏幕最小可见宽度
    min-device-height  输出设备的屏幕的最小可见高度
    min-height  输出设备中的页面最小可见区域高度
    min-monochrome  在一个单色框架缓冲区中每像素包含的最小单色原件个数
    min-resolution  设备的最小分辨率
    min-width  输出设备中的页面最小可见区域宽度
    monochrome  在一个单色框架缓冲区中每像素包含的单色原件个数
    orientation  输出设备中的页面可见区域高度是否大于或等于宽度
    resolution  设备的分辨率
    scan  电视类设备的扫描工序
    width  输出设备中的页面可见区域宽度
<br/>
### 2、媒体类型
@media查询可以针对不同的媒体类型设置不同的样式
#### • 内部样式表
`@media 媒体类型 and|not|only (媒体功能) {选择器 {……}}`
```html
<head>
    <style type="text/css">
        p {color:black;}
        @media screen and (max-width:300px) {p {color:red;}}
    </style>
</head>

<body>
    <p>
    文档内容默认为黑色（最大值时）；
    当屏幕宽度≤300px时，文档内容变为红色（最小值时）。
    </p>
</body>
```

#### • 链接外部样式表
`<link …… media="媒体类型 and|not|only (媒体功能)" ……/>`
```html
<head>
    <link rel="stylesheet" type="text/css" href="外部样式1.css"/>
    <link rel="stylesheet" type="text/css" media="screen and (max-width:300px)" href="外部样式2.css"/>
</head>

<body>
    <p>
    文档内容默认应用样式1（最大值时）；
    当屏幕宽度≤300px时，应用样式2（最小值时）。
    </p>
</body>
```

    all  用于所有设备
    print  用于打印机和打印预览
    screen  用于电脑屏幕，平板电脑，智能手机等
    speech  应用于屏幕阅读器等发声设备

---


  [1]: http://www.w3school.com.cn/tags/html_ref_language_codes.asp
  [2]: https://wx1.sinaimg.cn/mw690/7de6638dly1fvph3yojekj20o503gq2y.jpg
  [3]: https://wx2.sinaimg.cn/mw690/7de6638dly1fw2je6cypmj20ph06s0ta.jpg
  [4]: https://wx1.sinaimg.cn/mw690/7de6638dly1fw2jtmsfstj20nz06o3z0.jpg
  [5]: https://wx1.sinaimg.cn/mw690/7de6638dly1fw2mbnex6jj20o409udgv.jpg
  [6]: http://wx4.sinaimg.cn/large/7de6638dly1fwfeqpt689g20mh044mxt.gif
  [7]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwikntepqaj20dl02fjrf.jpg