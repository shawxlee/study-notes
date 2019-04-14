# CSS 框架|属性|函数参考手册
Cascading Style Sheets - 层叠样式表

标签（空格分隔）： css 属性 

---

## CSS框架
### 1、元素框的类型
#### • 块级元素（block）
总是在新行上开始；height、line-height、margin、padding可设置；宽度缺省时为容器的100%；可容纳内联元素和块元素

    address  blockquote  center  dir  div  dl  fieldset  form  h1~h6  hr  isindex  menu  noframes  noscript  ol  p  pre  table  ul

#### • 内联元素（inline）
和其他元素排在一行上；height、line-height、margin、padding不可设置；宽度就是内容的宽度；只能容纳文本或内联元素

    a  abbr  acronym  b  bdo  big  br  cite  code  dfn  em  font  i  img  input  kbd  label  q  s  samp  select  small  span  strike  strong  sub  sup  textarea  tt  u  var

#### • 行内块元素（inline-block）
将块级元素内联在同一行排列显示，且保留其可以设置宽高的属性
<br>
### 2、CSS盒模型
#### • 块级盒子（block box）
    content-box：在设定宽高的区域之外绘制内边距和边框，元素的实际尺寸等于相加值
    border-box：在设定宽高的区域之内绘制内边距和边框，元素的实际尺寸等于设定值
    
    margin（外边距）：清除边框外的区域，颜色完全透明
    border（边框）：边框的填充，受盒子的背景颜色影响
    padding（内边距）：清除边框到内容的区域，受到框中填充的背景颜色影响
    content（内容）：盒子的内容，显示文本和图像
    
![block box][1]

#### • 行级盒子（line box）
**替换元素**：内容可替换，有自己的样式规则，如：`input` 等元素
**非替换元素**：内容不可替换，直接显示结果，如：`p` 等大多数元素
    
    containing box（包含盒子）：元素标签，由多个line box堆叠而成
    line box（行框盒子）：一行，包含所有inline box的最高点到最低点的最小框
    strut（起始字符）：每个line box的起点有一个宽度为0的字符，并影响盒子的高度
    inline box（内联盒子）：让内容排成一行显示
    vertical spacing（行间距）=H(line-height)-H(font-size)
    half-leading（半行距）=H(vertical spacing)/2
    context area（内容区域）：内容区域
    character box（字符盒子）：字符字形，高度由font-size的值决定

![line box][2]
<br/>
### 3、CSS单位
#### • 绝对单位
绝对长度单位是一个固定的值，它反应一个真实的物理尺寸，视输出介质而定，不依赖于环境（显示器、分辨率、操作系统等）
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>单位</th>
<th>描述</th>
<th>换算值</th>
</tr>
</thead>
<tbody>
<tr>
<td>cm</td>
<td>centimeter（厘米）</td>
<td></td>
</tr>
<tr>
<td>mm</td>
<td>millimeter（毫米）</td>
<td></td>
</tr>
<tr>
<td>in</td>
<td>inch（英寸）</td>
<td>1in = 96px = 2.54cm</td>
</tr>
<tr>
<td>px</td>
<td>pixel（像素）</td>
<td>1px = 1/96th of 1in</td>
</tr>
<tr>
<td>pt</td>
<td>point（磅）</td>
<td>1pt = 1/72in</td>
</tr>
<tr>
<td>pc</td>
<td>pica（派卡）</td>
<td>1pc = 12 pt</td>
</tr>
</tbody>
</table>

#### • 相对单位
相对长度单位指定了一个长度相对于另一个长度的属性，对于不同的设备相对长度更适用
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>单位</th>
<th>描述</th>
<th>换算值</th>
</tr>
</thead>
<tbody>
<tr>
<td>em</td>
<td>（当前浏览器默认字号的倍数）</td>
<td>1em = 16px</td>
</tr>
<tr>
<td>ex</td>
<td>（当前字体中字母 x 高度的倍数）</td>
<td>1ex = 1/2em = 8px</td>
</tr>
<tr>
<td>ch</td>
<td>（当前字体中数字 0 宽度的倍数）</td>
<td></td>
</tr>
<tr>
<td>rem</td>
<td>（html根元素字号的倍数）</td>
<td></td>
</tr>
<tr>
<td>vw</td>
<td>viewpoint width（视窗宽度）</td>
<td>1vw = 当前视窗宽度的1%</td>
</tr>
<tr>
<td>vh</td>
<td>viewpoint height（视窗高度）</td>
<td>1vh = 当前视窗高度的1%</td>
</tr>
<tr>
<td>vmin</td>
<td>（vw和vh中较小的那个）</td>
<td></td>
</tr>
<tr>
<td>vmax</td>
<td>（vw和vh中较大的那个）</td>
<td></td>
</tr>
<tr>
<td>%</td>
<td>percent（占父元素大小的百分比）</td>
<td></td>
</tr>
</tbody>
</table>
<br/>
### 4、浏览器兼容
#### Step 1、先检查哪些浏览器支持该属性，仅需列出不支持的私有前缀
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>属性前缀</th>
<th>内核</th>
<th>浏览器</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>-webkit-</code></td>
<td>Blink</td>
<td>新版Chrome、新版Opera</td>
</tr>
<tr>
<td><code>-webkit-</code></td>
<td>WebKit</td>
<td>旧版Chrome、中版Opera、Safari、Android</td>
</tr>
<tr>
<td><code>-moz-</code></td>
<td>Gecko</td>
<td>Firefox</td>
</tr>
<tr>
<td><code>-o-</code></td>
<td>Presto</td>
<td>旧版Opera</td>
</tr>
<tr>
<td><code>-ms-</code></td>
<td>Trident</td>
<td>IE、Edge</td>
</tr>
</tbody>
</table>

#### Step 2、各浏览器私有属性写在前面，标准属性写在最后一行

---

## CSS规范属性
### 1、设置所有的背景属性：`background`
```css
div {background: blue url(/image.jpg) cover fixed center;}
div {
    background-color: blue;
    background-clip: border-box;
    background-image: url(/image.jpg);
    background-size: cover;
    background-repeat: repeat;
    background-attachment: fixed;
    background-position: center;
    background-origin: padding-box;
}

书写顺序：颜色 区域 图像 尺寸 重复 滚动 位置 定位参照
/* 未设置的属性会使用其默认值 */
```
#### - 元素的背景颜色：`background-color`
    transparent  背景颜色为透明（默认值）
    *color_name  颜色名称
    *hex_number  十六进制值
    *rgb_number  rgb代码
#### - 背景的绘制区域：`background-clip`
    border-box	背景被裁剪到边框盒（默认值）
    padding-box  背景被裁剪到内边距框
    content-box  背景被裁剪到内容框
#### - 元素的背景图像：`background-image`
    none  不显示背景图像（默认值）
    url(……)  图像的相对路径
#### - 背景图像的尺寸：`background-size`
    auto  原始尺寸（默认值）
    *px *px  设置背景图像的高度和宽度
    *% *%  以父元素的百分比来设置背景图像的宽度和高度
    *px/*%  仅规定一个关键词时，另一个值默认auto
    cover  扩展图像至完全覆盖背景区域
    contain  在背景区域内扩展图像至最大尺寸
#### - 是否及如何重复背景图像：`background-repeat`
    repeat  在垂直方向和水平方向重复（默认值）
    repeat-x  在水平方向重复
    repeat-y  在垂直方向重复
    no-repeat  不重复
#### - 背景图像是否随页面滚动：`background-attachment`
    scroll  背景图像会随着页面其余部分的滚动而移动（默认值）
    fixed  背景图像在窗口位置固定
#### - 背景图像的起始位置：`background-position`
    *x% *y%  水平位置从左至右0~100 垂直位置从上至下0~100（默认值：0% 0%）
    *xpos *ypos  方位关键词（默认值：top left）
    *%|*pos  仅规定一个关键词时，另一个值默认居中（*% 与 *pos 可混合使用）
#### - 背景图像相对于什么位置来定位：`background-origin`
    padding-box  相对于内边距框来定位（默认值）
    border-box  相对于边框盒来定位
    content-box  相对于内容框来定位
<br/>
### 2、设置所有的边框属性：`border`
```css
h1 {border: 5px solid blue;}
h1 {
    border-width: 5px;
    border-style: solid;
    border-color: blue;
}

书写顺序：宽度 样式 颜色
/* 未设置的属性会使用其默认值 */
```
#### - 边框的宽度：`border-width`
    medium  默认
    thin  细边框
    thick  粗边框
    *px  自定义边框的宽度
#### - 边框的样式：`border-style`
    none  无边框
    hidden  无边框（应用于表时解决边框冲突）
    dotted  点状边框（实线）
    dashed  虚线（实线）
    solid  实线
    double  双线（宽度等于border-width的值）
    groove  3D凹槽边框（效果取决于border-color的值）
    ridge	3D垄状边框（效果取决于border-color的值）
    inset  3D inset边框（效果取决于border-color的值）
    outset  3D outset边框（效果取决于border-color的值）
#### - 边框的颜色：`border-color`
    transparent  透明（默认值）
    *color_name  颜色名称
    *hex_number  十六进制值
    *rgb_number  RGB代码
<br/>
### 3、允许将元素的边框替换为图片或形状：`border-image`
```css
h1 { 
    border: 10px solid blue;   /* 必须先设置边框属性 */
    border-image: url(/image.jpg) 30 stretch;
}
h1 { 
    border: 10px solid blue;
    border-image-source: url(/image.jpg);
    border-image-slice: 30;
    border-image-width: 1;
    border-image-outset: 0;
    border-image-repeat: stretch;
}

书写顺序：图像路径 裁剪位置 边框宽度 边框溢出 填充方式
/* 未设置的属性会使用其默认值 */
```
![效果示例][3]
#### - 要使用的图像：`border-image-source`
    none  不使用图像（默认值）
    url(……)  用作边框的图像的相对路径
#### - 图像裁剪的位置：`border-image-slice`
```css
p {border-image-slice: 30% 35% 40% 30%;}

书写顺序：上边框 右边框 下边框 左边框
```
![效果示例][4]

    *%	相对于图像尺寸的百分比值（默认值：100%）
    *number  图像中的像素（光栅图像）或矢量坐标（矢量图像）
    fill  不裁剪，保留图像的中间部分
#### - 图像边框的宽度：`border-image-width`
```css
p {border-image-width: 30% 35% 40% 30%;}

书写顺序：上边框 右边框 下边框 左边框
```
    *number  相对于border-width的倍数（默认值：1）
    *%  相对于图像切片尺寸的百分比值，高度影响水平偏移，宽度影响垂直偏移
    auto  宽度为对应的图像切片的固有宽度
#### - 边框图像超过边框盒的量：`border-image-outset`
```css
p {border-image-width: 10px 5px 2px 5px;}

书写顺序：上边框 右边框 下边框 左边框
```
    *px  设置边框图像与边框的距离（默认值：0）
    *number  相对于border-width的倍数
#### - 图像边框的填充方式：`border-image-repeat`
```css
h1 {border-image-repeat: stretch;}
p {border-image-repeat: stretch repeat;}

书写顺序：水平填充 垂直填充
```
![填充方式][5]

    stretch  拉伸图像来填充区域（默认值）
    repeat  平铺图像来填充区域
    round  如果无法完整平铺所有图像，则对图像进行缩放以适应区域
    space  如果无法完整平铺所有图像，扩展空间会分布在图像周围
<br/>
### 4、为元素添加圆角边框：`border-radius`
#### • 仅设置一个值（平滑的圆角边框）
```css
h1 {border-radius: 30px;}
h1 {
    border-top-left-radius: 30px;
    border-top-right-radius: 30px;
    border-bottom-right-radius: 30px;
    border-bottom-left-radius: 30px;
}
```
![示例效果][6]
#### • 设置两个值（两条对角线上的角不同）
```css
h2 {border-radius: 50px 0px;}
h2 {
    border-top-left-radius: 50px 50px;
    border-top-right-radius: 0px 0px;
    border-bottom-right-radius: 50px 50px;
    border-bottom-left-radius: 0px 0px;
}

书写顺序：左上角-右下角 右上角-左下角
```
![示例效果][7]
#### • 设置三/四个值（每个角不同）
```css
h3 {border-radius: 10px 20px 30px 40px;}
h3 {
    border-top-left-radius: 10px 10px;
    border-top-right-radius: 20px 20px;
    border-bottom-right-radius: 30px 30px;
    border-bottom-left-radius: 40px 40px;
}

书写顺序：左上角 右上角 右下角 左下角
```
![此处输入图片的描述][8]
#### • 设置多个值（四个方向的水平/垂直半径）
```css
h4 {border-radius: 2em 1em 4em / 0.5em 3em;}
h4 {border-radius: 2em 1em 4em 1em / 0.5em 3em 0.5em 3em;}
h4 {
    border-top-left-radius: 2em 0.5em;
    border-top-right-radius: 1em 3em;
    border-bottom-right-radius: 4em 0.5em;
    border-bottom-left-radius: 1em 3em;
}

书写顺序：左上水平 右上水平 右下水平 左下水平 / 左上垂直 右上垂直 右下垂直 左下垂直
```
![示例效果][9]

    *px  定义圆角的半径值（默认值：0）
    *%  宽x百分比值=水平半径；高x百分比值=垂直半径
<br/>
### 5、向框添加一个或多个阴影：`box-shadow`
```css
.div1 {box-shadow: 10px 10px;}
.div2 {box-shadow: 10px 10px 5px #888888;}
.div3 {box-shadow: 10px 10px 5px 5px #888888 inset;}

书写顺序：水平偏移 垂直偏移 模糊距离 拓展尺寸 阴影颜色 内部阴影
*必需值：水平偏移 垂直偏移
```
![效果示例][10]

    *h-shadow  水平阴影的长度（必需，允许负值）
    *v-shadow  垂直阴影的长度（必需，允许负值）
    *blur  模糊距离
    *spread  拓展尺寸
    *color  阴影的颜色
    inset  将外部阴影改为内部阴影
<br/>
### 6、以特定方式定义元素以适应指定区域：`box-sizing`
```css
/* 在设定尺寸的区域之外绘制内边距和边框，相加为元素的实际尺寸 */
.div1 {
    box-sizing: content-box;    /* 默认值 */
    width: 100%;
    padding: 5px;
    border-width: 10px;
}

/* 在设定尺寸的区域之内绘制内边距和边框，元素的实际尺寸等于设定值*/
.div2 {
    box-sizing: border-box;
    width: 100%;
    padding: 5px;
    border-width: 10px;
}

/* box-sizing属性仅应用于block-box块级盒模型元素 */
```
![box-sizing效果示例][11]

<br/>
### 7、清除其他浮动元素：`clear`
```css
div {clear: none;}
```
    none  允许浮动元素出现在两侧（默认值）
    left  在左侧不允许浮动元素
    right  在右侧不允许浮动元素
    both  在左右两侧均不允许浮动元素

<br/>
### 8、规定文本的颜色：`color`
```css
h1 {color: red;}   /* 颜色名称 */
h2 {color: #00ff00;}   /* 十六进制值 */
h3 {color: rgb(0,0,255);}   /* RGB代码 */
```
<br/>
### 9、插入生成内容：`content`
```css
h1:before {content: url(/image.jpg)}
h1:after {content: "sometext"}

/* 与 :before 以及 :after 伪元素配合使用 */
```
    normal	默认值
    none  无内容
    counter  设定计数器内容
    attr(……)  返回指定属性的值
    "……"  插入字符串内容
    open-quote  插入开口引号
    close-quote  插入闭合引号
    no-open-quote  移除内容的开始引号
    no-close-quote  移除内容的闭合引号
    url(……)  插入媒体内容（图像，声音，视频等）
<br/>
### 10、鼠标指针放在一个元素边界范围内时的光标形状：`cursor`
```css
p {cursor: auto;}
```
![此处输入图片的描述][12]

    auto  浏览器设置的光标（默认值）
    *url  需使用的自定义光标的 URL
    default  箭头
    crosshair  十字线
    pointer  一只手
    wait  一只表或沙漏
    help  一个问号或气球
    text  指示文本
    move  指示某对象可被移动
    n-resize  指示矩形框的边缘可被向上（北）移动
    s-resize  指示矩形框的边缘可被向下（南）移动
    w-resize  指示矩形框的边缘可被向左（西）移动
    e-resize  指示矩形框的边缘可被向右（东）移动
    nw-resize  指示矩形框的边缘可被向上（北）及向左（西）移动
    ne-resize  指示矩形框的边缘可被向上（北）及向右（东）移动
    sw-resize  指示矩形框的边缘可被向下（南）及向左（西）移动
    se-resize  指示矩形框的边缘可被向下（南）及向右（东）移动
<br/>
### 11、规定元素应该生成的框的类型：`display`
```css
/* 无法设置宽高的内联元素 */
h1 {display: inline;}

/* 可设置宽高的块级元素 */
h2 {
    width: 100px;
    height: 100px;
    display: block;
}

/* 可设置宽高的行内块元素 */
h3 {
    width: 100px;
    height: 100px;
    display: inline-block;
}
```
    inline  内联元素，不换行（默认值）
    none  不显示
    block  块级元素，换行
    inline-block  行内块元素
    list-item  块级列表
    run-in  根据上下文作为块级元素或内联元素显示
    table  块级表格，换行（类似 <table>）
    inline-table  内联表格，不换行（类似 <table>）
    table-row-group  一个或多个行的分组（类似 <tbody>）
    table-header-group  一个或多个行的分组（类似 <thead>）
    table-footer-group  一个或多个行的分组（类似 <tfoot>）
    table-row  一个表格行（类似 <tr>）
    table-column-group  一个或多个列的分组（类似 <colgroup>）
    table-column  一个单元格列（类似 <col>）
    table-cell  一个表格单元格（类似 <td> 和 <th>）
    table-caption  一个表格标题（类似 <caption>）

### * 盒状模型的弹性布局：`display: flex | inline-flex`
```css
/* 任何一个容器都可以指定为Flex布局 */
h1 {display: flex;}
/* 行内元素也可以使用Flex布局 */
h2 {display: inline-flex;}

/* Flex布局下，子元素的float、clear、vertical-align属性将失效 */
```
采用Flex布局的元素称为**Flex容器**，子元素称为**Flex项目**：

![Flex容器和Flex项目1][13]
![Flex容器和Flex项目2][14]
#### ① Flex容器（父元素）的属性
##### • 项目的排列方式：`flex-flow`
```css
.box {
    display: flex;
    flex-flow: row nowrap;    /* 默认值 */
}
.box {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
}

书写顺序：方向 换行
```
##### - 项目的排列方向：`flex-direction`

    row  从左起水平排列（默认值）
    row-reverse  从右起水平排列
    column  从上起垂直排列
    column-reverse  从下起垂直排列
    
![项目的排列方向][15]

##### - 项目的换行方式：`flex-wrap`

    nowrap  不换行（默认值）
    wrap  换行到下方
    wrap-reverse  换行到上方

![换行方式][16]
##### • 项目在横轴方向上的对齐方式：`justify-content`
```css
.box {
    display: flex;
    justify-content: flex-start;
}
```
    flex-start  左对齐（默认值）
    flex-end  右对齐
    center  居中
    space-between  两端对齐，紧贴边框
    space-around  两端对齐，间隔边框
    space-evenly  均匀对齐，间隔相等
![横轴对齐方式][17]
##### • 项目在纵轴方向上的对齐方式：`align-items`
```css
.box {
    display: flex;
    align-items: stretch;
}
```
    stretch  拉伸项目占满容器高度（默认值）
    flex-start  容器起点对齐
    flex-end  容器终点对齐
    center  容器中心对齐
    baseline  项目内容沿基线对齐
![垂直对齐方式][18]
##### • 多根轴线在纵轴方向上的对齐方式：`align-content`
```css
.box {
    display: flex;
    align-content: stretch;
}

/* 如果项目只有一根轴线，则该属性无效 */
```
    stretch  拉伸轴线占满容器高度（默认值）
    flex-start  容器起点对齐
    flex-end  容器终点对齐
    center  容器中心对齐
    space-between  两端对齐，紧贴边框
    space-around  两端对齐，间隔边框
![多行垂直对齐方式][19]

#### ② Flex项目（子元素）的属性
##### • 项目出现的顺序：`order`
```css
.item {order: 3;}   /* 一个数字，规定项目出现的顺序（默认值：0） */
```
![项目出现的顺序][20]
##### • 项目如何分配空间：`flex`
```css
.item {flex: 0 1 auto;}   /* 默认值 */
.item {
    flex-grow: 0;
    flex-shrink: 1;
    flex-basis: auto;
}

书写顺序：放大 缩小 基准值
```
    auto == 1 1 auto
    none == 0 0 auto
    一个非负数值n == n 1 0%
    一个百分比值*% == 1 1 *%
    一个长度值*px == 1 1 *px
    两个非负数值a b == a b 0%
    一个非负数值和一个百分比值n *% == n 1 *%
    一个非负数值和一个长度值n *px == n 1 *px

##### - 项目扩展的比率：`flex-grow`

    *number  规定项目将相对于其他项目进行扩展的量（默认值：0）
![flex-grow][21]

##### - 当项目宽度之和大于容器宽度时，项目收缩的比率：`flex-shrink`

    *number  规定项目将相对于其他项目进行收缩的量（默认值：1）
![flex-shrink][22]

##### - 设置或检索项目基准值，计算剩余空间以伸缩项目：`flex-basis`

    auto  默认值等于项目的长度（如果该项目未指定长度，则长度将根据内容决定）
    *px  规定项目的初始长度
    *%  相对于容器尺寸的百分比值计算项目的初始长度
##### • 允许单个项目在纵轴方向上的不同对齐方式：`align-self`
```css
.item {align-self: auto;}
```
    auto  继承容器的align-items属性（默认值），如果没有则值为stretch
    stretch  拉伸项目占满容器高度
    center  容器中心对齐
    flex-start  容器起点对齐
    flex-end  容器终点对齐
    baseline  项目内容沿基线对齐
![单独对齐方式][23]
<br/>
### 12、定义元素在哪个方向浮动：`float`
```css
h1 {float: none;}

/* 元素被添加float属性后变成块级或行内块元素 */
```
    none  不浮动（默认值）
    left  元素向左浮动
    right  元素向右浮动

<br/>
### 13、设置所有字体属性：`font`
```css
h1 {font: italic bold 12px/30px Georgia,serif;}
h1 {
    font-style: italic;
    font-variant: normal;
    font-weight: bold;
    font-size: 12px;
    line-height: 30px;
    font-family: Georgia,serif;
}

书写顺序：风格 大写 粗细 字号/行高 字体
*必需值：字号 字体
/* 未设置的属性会使用其默认值 */
```
    caption  定义被标题控件（比如按钮、下拉列表等）使用的字体
    icon  定义被图标标记使用的字体
    menu  定义被下拉列表使用的字体
    message-box  定义被对话框使用的字体
    small-caption  caption 字体的小型版本
    status-bar  定义被窗口状态栏使用的字体
#### - 字体的风格：`font-style`
    normal  标准（默认值）
    italic  斜体
    oblique  倾斜
#### - 小型大写字母文本：`font-variant`
    normal	标准（默认值）
    small-caps  所有小写字母转换为大写，但字号较小
#### - 文本的粗细：`font-weight`
    normal	标准（默认值）
    bold  粗体
    bolder  更粗
    lighter  更细
    100|200|300|400|500|600|700|800|900  由细到粗（400:normal，700:bold）
#### - 字体的尺寸：`font-size`
    medium	标准（默认值）
    xx-small|x-small|small  小
    large|x-large|xx-large  大
    smaller  比父元素更小
    larger  比父元素更大
    *px  一个固定的值（浏览器默认字号16px）
    *%  基于父元素的一个百分比值
#### - 行高：`line-height`
    normal	标准（默认值）
    *number  font-size值的倍数
    *px  固定的行间距
    *%  相对于font-size值的百分比值
#### - 元素的字体系列：`font-family`
```css
h1 {font-family: 'Times New Roman', Georgia, serif;}

书写顺序：特定字体1, 特定字体2, ……, 通用字体;
/* 若字体名包含空格或符号，则需要添加引号 */
```
    • 特定字体：一个特定的字体系列（如"Times New Roman"、"Arial"等……）
    • 通用字体：拥有相似外观的字体系统组合（serif|sans-serif|monospace|cursive|fantasy）
    serif  成比例，有衬线
    sans-serif  成比例，无衬线
    monospace  不成比例
    cursive  模仿人的手写体
    fantasy  无法用特征定义
![此处输入图片的描述][24]
<table>
<thead>
<tr style="background: #555555; color: #fff;">
<th>serif 字体组合</th>
<th>文本示例</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Georgia, serif</code></td>
<td><p style="font-family: Georgia, serif;">Georgia</p></td>
</tr>
<tr>
<td><code>'Palatino Linotype', 'Book Antiqua', Palatino, serif</code></td>
<td><p style="font-family: 'Palatino Linotype', 'Book Antiqua', Palatino, serif;">Palatino Linotype<br>Book Antiqua<br> Palatino</p></td>
</tr>
<tr>
<td><code>'Times New Roman', Times, serif</code></td>
<td><p style="font-family: 'Times New Roman', Times, serif;">Times New Roman<br>Times</p></td>
</tr>
</tbody>
<thead>
<tr style="background: #555555; color: #fff;">
<th>sans-serif 字体组合</th>
<th>文本示例</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Arial, Helvetica, sans-serif</code></td>
<td><p style="font-family: Arial, Helvetica, sans-serif;">Arial<br>Helvetica</p></td>
</tr>
<tr>
<td><code>Arial Black, Gadget, sans-serif</code></td>
<td><p style="font-family: Arial Black, Gadget, sans-serif;">Arial Black<br>Gadget</p></td>
</tr>
<tr>
<td><code>'Comic Sans MS', cursive, sans-serif</code></td>
<td><p style="font-family: 'Comic Sans MS', cursive, sans-serif;">Comic Sans MS<br>cursive</p></td>
</tr>
<tr>
<td><code>Impact, Charcoal, sans-serif</code></td>
<td><p style="font-family: Impact, Charcoal, sans-serif;">Impact<br>Charcoal</p></td>
</tr>
<tr>
<td><code>'Lucida Sans Unicode', 'Lucida Grande', sans-serif</code></td>
<td><p style="font-family: 'Lucida Sans Unicode', 'Lucida Grande', sans-serif;">Lucida Sans Unicode<br>Lucida Grande</p></td>
</tr>
<tr>
<td><code>Tahoma, Geneva, sans-serif</code></td>
<td><p style="font-family: Tahoma, Geneva, sans-serif;">Tahoma<br>Geneva</p></td>
</tr>
<tr>
<td><code>'Trebuchet MS', Helvetica, sans-serif</code></td>
<td><p style="font-family: 'Trebuchet MS', Helvetica, sans-serif;">Trebuchet MS<br>Helvetica</p></td>
</tr>
<tr>
<td><code>Verdana, Geneva, sans-serif</code></td>
<td><p style="font-family: Verdana, Geneva, sans-serif;">Verdana<br>Geneva</p></td>
</tr>
</tbody>
<thead>
<tr style="background: #555555; color: #fff;">
<th>monospace 字体组合</th>
<th>文本示例</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>'Courier New', Courier, monospace</code></td>
<td><p style="font-family: 'Courier New', Courier, monospace;">Courier New<br>Courier</p></td>
</tr>
<tr>
<td><code>'Lucida Console', Monaco, monospace</code></td>
<td><p style="font-family: 'Lucida Console', Monaco, monospace;">Lucida Console<br>Monaco</p></td>
</tr>
</tbody>
</table>
<br/>
### 14、设置元素的高度：`height`
```css
h1 {height: auto;}   /* 根据内容自动调整（默认值） */
h2 {height: 500px;}   /* 使用单位定义高度 */
h3 {height: 100%;}   /* 基于父元素高度的百分比值 */
```
<br/>
### 15、增加或减少字符间距：`letter-spacing`
```css
h1 {letter-spacing: normal;}   /* 默认值 */
h2 {letter-spacing: 20px;}   /* 字符间的固定空间 */
h3 {letter-spacing: -0.5em;}   /* 允许使用负值，让字母挤得更紧 */
```
<br/>
### 16、设置所有的列表属性：`list-style`
```css
h1 {list-style: square inside url(/image.jpg);}
h1 {
    list-style-type: square;
    list-style-position: inside;
    list-style-image: url(/image.jpg);
}

书写顺序：标记类型 标记位置 图像标记
/* 未设置的属性会使用其默认值 */
```
#### - 列表项标记的类型：`list-style-type`
    disc  实心圆标记（默认值）
    none  无标记
    circle  空心圆标记
    square  实心方块标记
    decimal  数字标记
    decimal-leading-zero  0开头的数字标记(01，02，03……)
    lower-roman  小写罗马数字标记(i，ii，iii……)
    upper-roman  大写罗马数字标记(I，II，III……)
    lower-alpha  小写英文字母标记(a，b，c……)
    upper-alpha  大写英文字母标记 (A，B，C……)
    lower-latin  小写拉丁字母标记(a，b，c……)
    upper-latin  大写拉丁字母标记(A，B，C……)
    lower-greek  小写希腊字母标记(α，β，γ……)
    hebrew  传统的希伯来编号方式
    armenian  传统的亚美尼亚编号方式
    georgian  传统的乔治亚编号方式(an，ban，gan……)
    cjk-ideographic  简单的表意数字
    hiragana  日文平假名字符（あ，い，う……）
    katakana  日文片假名字符（ア，イ，ウ……）
    hiragana-iroha  日文平假名序号（い，ろ，は……）
    katakana-iroha	日文片假名序号（イ，ロ，ハ……）
#### - 在何处放置列表项标记：`list-style-position`
    outside  标记放置在文本以外的左侧，且环绕文本不根据标记对齐（默认值）
    inside  标记放置在文本以内，且环绕文本根据标记对齐
#### - 使用图像来替换列表项的标记：`list-style-image`
    none  无图像（默认值）
    url(……)  图像的相对路径
<br/>
### 17、设置所有外边距属性：`margin`
#### • 仅设置一个值（元素在父元素内居中）
```css
h1 {margin: 20px;}
h1 {
    margin-top: 20px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 20px;
}

/* 允许使用负值，不过使用时要小心 */
```
#### • 设置两个值（垂直方向和水平方向的外边距）
```css
h2 {margin: 20px 30px;}
h2 {
    margin-top: 20px;
    margin-right: 30px;
    margin-bottom: 20px;
    margin-left: 30px;
}

书写顺序：垂直方向 水平方向
/* 允许使用负值，不过使用时要小心 */
```
#### • 设置三/四个值（四个方向的外边距）
```css
h3 {margin: 10px 15px 20px;}   /* 值复制原则 */
h3 {margin: 10px 15px 20px 15px;}
h3 {
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 20px;
    margin-left: 10px;
}

书写顺序：上 右 下 左
/* 允许使用负值，不过使用时要小心 */
```
    auto  默认
    *px  以具体单位计的外边距值
    *% 基于父元素的宽度的百分比值
**值复制原则**：left<=right、bottom<=top、right<=top

![值复制原理图][25]
<br/>
### 18、定义元素的最大宽度：`max-width`
```css
h1 {max-width: none;}   /* 没有限制（默认值） */
h2 {max-width: 300px;}   /* 定义元素的最大宽度值 */
h3 {max-width: 50%;}   /* 基于包含它的块级对象的百分比值 */

/* 不允许指定负值 */
```
<br/>
### 19、设置元素的透明度：`opacity`
```css
h1 {opacity: 0.0;}   /* 完全透明 */
h2 {opacity: 0.5;}   /* 半透明 */
h3 {opacity: 1.0;}   /* 毫不透明 */

/* 取值范围：0.0 — 1.0 */
```
<br/>
### 20、当内容溢出元素框时发生的事情：`overflow`
```css
div {overflow: visible;}

/* 当行内块元素被设置overflow属性且值非visible时，其baseline被修改为元素的下外边沿 */
```
    visible  溢出部分自然显示（默认值）
    hidden  溢出部分被隐藏，不可查看
    scroll  始终显示滚动条，可查看被隐藏的溢出部分
    auto  如果溢出部分被隐藏，则显示滚动条查看

#### - 对内容的左/右边缘进行裁剪：`overflow-x`
    visible  不裁剪内容
    hidden  裁剪内容，不滚动
    scroll  裁剪内容，可滚动
    auto  如果溢出框则滚动
    no-display  如果内容不适合框则删除框
    no-content  如果内容不适合框则隐藏内容
#### - 对内容的上/下边缘进行裁剪：`overflow-y`
    visible  不裁剪内容
    hidden  裁剪内容，不滚动
    scroll  裁剪内容，可滚动
    auto  如果溢出框则滚动
    no-display  如果内容不适合框则删除框
    no-content  如果内容不适合框则隐藏内容
<br/>
### 21、设置所有内边距属性：`padding`
#### • 仅设置一个值（元素中的内容居中）
```css
h1 {padding: 20px;}
h1 {
    padding-top: 20px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 20px;
}

/* 禁止使用负值 */
```
#### • 设置两个值（垂直方向和水平方向的内边距）
```css
h2 {padding: 20px 30px;}
h2 {
    padding-top: 20px;
    padding-right: 30px;
    padding-bottom: 20px;
    padding-left: 30px;
}

书写顺序：垂直方向 水平方向
/* 禁止使用负值 */
```
#### • 设置三/四个值（四个方向的内边距）
```css
h3 {padding: 10px 15px 20px;}   /* 值复制原则 */
h3 {padding: 10px 15px 20px 15px;}
h3 {
    padding-top: 10px;
    padding-right: 15px;
    padding-bottom: 20px;
    padding-left: 10px;
}

书写顺序：上 右 下 左
/* 禁止使用负值 */
```
    auto  默认
    *px  以具体单位计的内边距值
    *%  基于父元素的宽度的百分比值
<br/>
### 22、规定元素的定位类型：`position`
```css
h1 {position: static;}   /* 没有定位，不移动（默认值） */
```
#### - 相对定位：`relative`
```css
h2 {
    position: relative;   /* 相对原位置偏移（不影响文档结构） */
    left: 100px;   /* 距原位置左边100px */
    top: 150px;   /* 距原位置上边150px */
}
```
![relative][26]
#### - 绝对定位：`absolute` / `fixed`
```css
h3 {
    position: absolute;   /* 相对父元素边框偏移（破坏文档结构） */
    left: 100px;   /* 距父元素左边框100px */
    top: 150px;   /* 距父元素上边框150px */
}

/* 元素被添加绝对定位后变成块级元素或行内块元素 */
```
![absolute][27]
```css
h4 {
    position: fixed;   /* 相对浏览器窗口偏移（破坏文档结构） */
    left: 100px;   /* 距窗口左边100px */
    top: 150px;   /* 距窗口顶部150px */
}

/* 元素被添加绝对定位后变成块级元素或行内块元素 */
```
![fixed][28]
#### - 粘性定位：`sticky`
```css
h5 {
    position: sticky;   /* 元素在阈值内滚动，到达阈值边缘时固定 */
    top: 0;   /* 滚动到浏览器窗口顶部时固定 */
    bottom: 10px;   /* 滚动到距浏览器窗口底部10px时固定 */
}

/* 必须设定top/right/bottom/left阈值，才可使粘性定位生效 */
```
![sticky][29]

<br/>
### 23、设置嵌套引用的引号类型：`quotes`
```css
q:lang(en) {quotes: "《" "》" "<" ">"}
```
    none  规定content属性的open-quote、close-quote的值不会产生任何引号
    "……" "……" "……" "……"  定义要使用的引号（前两个值规定第一级引用嵌套，后两个值规定下一级引号嵌套）
<br/>
### 24、规定元素中的文本的水平对齐方式：`text-align`
```css
h1 {text-align: left;}
```
    left  左对齐（默认）
    right  右对齐
    center  居中对齐
    justify  两端对齐
<br/>
### 25、规定添加到文本的修饰：`text-decoration`
```css
h1 {text-decoration: none;}
```
    none  无修饰（默认值）
    underline  下划线
    overline  上划线
    line-through  删除线
    blink  文本闪烁
<br/>
### 26、规定文本块中首行文本的缩进：`text-indent`
```css
h1 {text-indent: 32px;}   /* 固定的缩进 */
h2 {text-indent: 2em;}   /* 缩进两个字符 */
h3 {text-indent: 50%;}   /* 基于父元素宽度的百分比的缩进 */

/* 允许使用负值，首行会被缩进到左边 */
```
<br/>
### 27、规定当文本溢出包含元素时发生的事情：`text-overflow`
```css
h1 {text-overflow: clip;}
```
    clip  修剪文本
    ellipsis  溢出文本省略为...
    "……"  溢出文本省略为字符串内容（仅对Firefox有效）
<br/>
### 28、向文本设置阴影：`text-shadow`
```css
h1 {text-shadow: 5px 5px;}
h2 {text-shadow: 5px 5px 5px #FF0000;} 

书写顺序：水平偏移 垂直偏移 模糊距离 阴影颜色
*必需值：水平偏移 垂直偏移
```
![效果示例][30]

    *h-shadow  水平阴影的位置（必需，允许负值）
    *v-shadow  垂直阴影的位置（必需，允许负值）
    *blur  模糊距离
    *color  阴影的颜色
<br/>
### 29、向元素应用2D或3D转换：`transform`
```css
.div1 {transform: none;}   /* 不进行转换 */
.div2 {transform: matrix(1, 0, 0, 1, 0, 0);}   /* 2D转换 */
.div3 {transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);}   /* 3D转换 */
```
#### - 转换属性：`matrix()` / `matrix3d()`

    matrix(a,b,c,d,tx,ty)  定义2D转换，设置3*3矩阵中的6个值
    matrix3d(a1,b1,c1,d1,a2,b2,c2,d2,a3,b3,c3,d3,a4,b4,c4,d4)  定义3D转换，设置4*4矩阵中的16个值

$$
\begin{equation}
\left[
\begin{array}{ccc}
a & c & t_x\\
b & d & t_y\\
0 & 0 & 1
\end{array} 
\right]
\times{
\left[ \begin{array}{c}
x\\
y\\
1
\end{array} 
\right ]}={
\left[ \begin{array}{c}
ax+cy+t_x\\
bx+dy+t_y\\
1
\end{array}
\right ]}
\end{equation}
\tag{2D}
$$

$$
\begin{equation}
\left[
\begin{array}{cccc}
a_1 & a_2 & a_3 & a_4\\
b_1 & b_2 & b_3 & b_4\\
c_1 & c_2 & c_3 & c_4\\
d_1 & d_2 & d_3 & d_4
\end{array} 
\right]
\end{equation}
\tag{3D}
$$

#### - 平移属性：`translate()` / `translate3d()` / `translateX|Y|Z()`

    translate(tx,ty)  定义2D平移（*px）
    translate3d(tx,ty,tz)  定义3D平移（*px）
    translateX(tx)	定义平移，只用X轴的值（*px）
    translateY(ty)	定义平移，只用Y轴的值（*px）
    translateZ(tz)	定义3D平移，只用Z轴的值（*px）

<table>
<thead>
<tr>
<th>平移属性</th>
<th>转换属性</th>
</tr>
</thead>
<tbody>
<tr>
<td>translate(tx,ty)</td>
<td>matrix(1,0,0,1,tx,ty)</td>
</tr>
<tr>
<td>translate3d(tx,ty,tz)</td>
<td>matrix3d(1,0,0,0,0,1,0,0,0,0,1,0,tx,ty,tz,1)</td>
</tr>
<tr>
<td>translateX(tx)</td>
<td>matrix(1,0,0,1,tx,0)
matrix3d(1,0,0,0,0,1,0,0,0,0,1,0,tx,0,0,1)</td>
</tr>
<tr>
<td>translateY(ty)</td>
<td>matrix(1,0,0,1,0,ty)
matrix3d(1,0,0,0,0,1,0,0,0,0,1,0,0,ty,0,1)</td>
</tr>
<tr>
<td>translateZ(tz)</td>
<td>matrix3d(1,0,0,0,0,1,0,0,0,0,1,0,0,0,tz,1)</td>
</tr>
</tbody>
</table>

#### - 缩放属性：`scale()` / `scale3d()` / `scaleX|Y|Z()`

    scale(sx,sy)  定义2D缩放（倍数）
    scale3d(sx,sy,sz)  定义3D缩放（倍数）
    scaleX(sx)	通过设置X轴的值来定义缩放（倍数）
    scaleY(sy)	通过设置Y轴的值来定义缩放（倍数）
    scaleZ(sz)	通过设置Z轴的值来定义3D缩放（倍数）

<table>
<thead>
<tr>
<th>缩放属性</th>
<th>转换属性</th>
</tr>
</thead>
<tbody>
<tr>
<td>scale(sx,sy)</td>
<td>matrix(sx,0,0,sy,0,0)</td>
</tr>
<tr>
<td>scale3d(sx,sy,sz)</td>
<td>matrix3d(sx,0,0,0,0,sy,0,0,0,0,sz,0,0,0,0,1)</td>
</tr>
<tr>
<td>scaleX(sx)</td>
<td>matrix(sx,0,0,1,0,0)
matrix3d(sx,0,0,0,0,1,0,0,0,0,1,0,0,0,0,1)</td>
</tr>
<tr>
<td>scaleY(sy)</td>
<td>matrix(1,0,0,sy,0,0)
matrix3d(1,0,0,0,0,sy,0,0,0,0,1,0,0,0,0,1)</td>
</tr>
<tr>
<td>scaleZ(sz)</td>
<td>matrix3d(1,0,0,0,0,1,0,0,0,0,sz,0,0,0,0,1)</td>
</tr>
</tbody>
</table>

#### - 旋转属性：`rotate()` / `rotate3d()` / `rotateX|Y|Z()`

    rotate(α)  定义2D旋转（*deg）
    rotate3d(x,y,z,α)  定义3D旋转（*deg）
    rotateX(α)	定义沿着X轴的3D旋转（*deg）
    rotateY(α)	定义沿着Y轴的3D旋转（*deg）
    rotateZ(α)	定义沿着Z轴的3D旋转（*deg）

<table>
<thead>
<tr>
<th>旋转属性</th>
<th>转换属性</th>
</tr>
</thead>
<tbody>
<tr>
<td>rotate(α)</td>
<td>matrix(cos(α), sin(α), -sin(α), cos(α), 0, 0)</td>
</tr>
<tr>
<td>rotate3d(x,y,z,α)</td>
<td>……</td>
</tr>
<tr>
<td>rotateX(α)</td>
<td>matrix3d(1, 0, 0, 0, 0, cos(α), sin(α), 0, 0, -sin(α), cos(α), 0, 0, 0, 0, 1)</td>
</tr>
<tr>
<td>rotateY(α)</td>
<td>matrix3d(cos(α), 0, -sin(α), 0, 0, 1, 0, 0, sin(α), 0, cos(α), 0, 0, 0, 0, 1)</td>
</tr>
<tr>
<td>rotateZ(α)</td>
<td>matrix3d(cos(α), sin(α), 0, 0, -sin(α), cos(α), 0, 0, 0, 0, 1, 0, 0, 0, 0, 1)</td>
</tr>
</tbody>
</table>

#### - 扭曲属性：`skew()` / `skewX|Y()`

    skew(αx,αy)  定义沿着X和Y轴的2D扭曲（*deg）
    skewX(α)  定义沿着X轴的2D扭曲（*deg）
    skewY(α)  定义沿着Y轴的2D扭曲（*deg）

<table>
<thead>
<tr>
<th>扭曲属性</th>
<th>转换属性</th>
</tr>
</thead>
<tbody>
<tr>
<td>skew(αx,αy)</td>
<td>matrix(1, tan(αy), tan(αx), 1, 0, 0)</td>
</tr>
<tr>
<td>skewX(α)</td>
<td>matrix(1, 0, tan(α), 1, 0, 0)</td>
</tr>
<tr>
<td>skewY(α)</td>
<td>matrix(1, tan(α), 0, 1, 0, 0)</td>
</tr>
</tbody>
</table>

#### - 透视属性：`perspective()`

    perspective(……)  通过设置镜头到3D元素的距离定义透视效果（*number/*px）

### • 设置元素转换的基准点：`transform-origin`
```css
/* 定义2D转换 */
.div1 {
    transform: rotate(45deg);
    transform-origin: 20% 40%;
}

/* 定义3D转换 */
.div2 {
    transform: rotateY(70deg);
    transform-origin: 50% 50% 100px;
}
```
    *x-axis  定义X轴上的位置（left/center/right/*length/*%）
    *y-axis  定义y轴上的位置（top/center/bottom/*length/*%）
    *z-axis  定义z轴上的位置（*length）
<br/>
### 30、设置元素的垂直对齐方式：`vertical-align`
```css
h1 {vertical-align: baseline;}

/* vertical-align属性仅应用于行内或行内块元素 */
```
![基线释义][31]

    baseline  元素的基线与父元素的基线对齐（默认值）
    middle  元素的基线放置在父元素的中部
    text-top  把元素的顶端与父元素字体的顶端对齐
    text-bottom  把元素的底端与父元素字体的底端对齐
    super  元素的基线垂直对齐文本的上标
    sub  元素的基线垂直对齐文本的下标
    top  把元素的顶端与行中最高元素的顶端对齐
    bottom  把元素的底端与行中最低的元素的底端对齐
    *px  元素偏移的距离，正值向上，负值向下
    *%  相对于line-height的百分比值来计算元素偏移的距离
<br/>
### 31、指定元素内的空白怎样处理：`white-space`
```css
p {white-space: normal;}
```
    normal  忽略空白（默认值）
    pre  保留空白
    nowrap  文本不换行，直到 <br> 为止
    pre-wrap  保留空白符序列，但要换行
    pre-line  合并空白符序列，但保留换行符
<br/>
### 32、设置元素的宽度：`width`
```css
h1 {width: auto;}   /* 根据内容自动调整（默认值） */
h2 {width: 500px;}   /* 使用单位定义宽度 */
h3 {width: 100%;}   /* 基于父元素宽度的百分比值 */
```
<br/>
### 33、指定一个元素的堆叠顺序：`z-index`
```css
img {
    position: absolute;   /* 必须先设置定位 */
	left: 0;
	top: 0;
	z-index: 1;   /* z-index属性值为正, 此元素将覆盖在上个元素前 */
}
```
    auto  堆叠顺序与父元素相等（默认值）
    *number  设置元素的堆叠顺序（负值向后堆叠，正值向前堆叠）

---

## CSS特殊属性
### 1、指定一个box子元素的排列方式：`-webkit-box-orient`
```css
div {
    display: -webkit-box;   /* 必须结合的属性 */
    -webkit-box-orient: inline-axis;
}
```
    inline-axis  子元素沿着内联坐标轴排列（默认值）
    block-axis  子元素沿着块坐标轴排列
    horizontal  指定子元素在一个水平线上从左至右排列
    vertical  从顶部向底部垂直布置子元素
<br/>
### 2、限制在一个块元素内文本可显示的行数：`-webkit-line-clamp`
```css
div {
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;   /* 必须结合的属性 */
    -webkit-box-orient: vertical;   /* 必须结合的属性 */
    -webkit-line-clamp: 3;
}
```
    *number  块元素显示的文本的行数

---

## CSS规范函数
### 1、返回选择元素的属性值：`attr()`
```css
attr(attribute-name)
/* attribute-name：HTML元素的属性名（必需） */
```
```html
<head>
    <style>
        a:after {content: " (" attr(href) ")";}
    </style>
</head>

<body>
    <p><a href="http://www.runoob.com/css/">CSS教程</a></p>
</body>
```
![此处输入图片的描述][32]
<br/>
### 2、动态计算长度值：`calc()`
```css
calc(expression)
/* expression：一个数学表达式，结果将采用运算后的返回值（必需） */
```
```html
<style>
    div {width: calc(100% - 100px);}
</style>

<!-- 表达式中运算符前后都必须有一个空格，任何长度和运算都可以计算 -->
```
![此处输入图片的描述][33]
<br/>
### 3、创建一个线性渐变的 "图像"：`linear-gradient()`
```css
background: linear-gradient(direction, start-color, transit-color, ……, stop-color);
/* start-color：指定渐变的起始颜色（必需） */
/* stop-color：指定渐变的终止颜色（必需） */
```
    *direction  指定渐变的方向（默认值：bottom）或角度（默认值：180deg）
    *transit-color  过渡颜色，可指定多个以创建更复杂的渐变效果
```html
<style>
    div {
        width: 200px;
        height: 200px;
        background: linear-gradient(red, yellow, blue);
    }
</style>
```
![此处输入图片的描述][34]
<br/>
### 4、创建一个径向渐变的 "图像"：`radial-gradient()`
```css
background: radial-gradient(shape size at position, start-color, transit-color, ……, stop-color);
/* start-color：指定渐变的起始颜色（必需） */
/* stop-color：指定渐变的终止颜色（必需） */
```
    *shape  确定圆的类型（ellipse|circle）
    *size  定义渐变的大小（farthest-corner|closest-side|closest-corner|farthest-side）
    *position  定义渐变的中心坐标。两个关键字：横坐标（left|center|right） 纵坐标（top|center|bottom）
    *transit-color  过渡颜色，可指定多个以创建更复杂的渐变效果
```html
<style>
    div {
        width: 200px;
        height: 200px;
        background: radial-gradient(red, yellow, blue);
    }
</style>
```
![此处输入图片的描述][35]
<br/>
### 5、创建重复的线性渐变 "图像"：`repeating-linear-gradient()`
```css
background: repeating-linear-gradient(angle | to position, start-color, transit-color, ……, stop-color);
/* start-color：指定渐变的起始颜色（必需） */
/* stop-color：指定渐变的终止颜色（必需） */
```
    *angle  定义渐变的角度方向（默认值：180deg）
    *position  指定线性渐变的起始位置。两个关键字：水平位置（left|right） 垂直位置（top|bottom）
    *transit-color  过渡颜色，可指定多个以创建更复杂的渐变效果
```html
<style>
    div {
        width: 200px;
        height: 200px;
        background: repeating-linear-gradient(red, yellow 10%, green 20%);
    }
</style>
```
![此处输入图片的描述][36]
<br/>
### 6、创建重复的径向渐变 "图像"：`repeating-radial-gradient()`
```css
background: repeating-linear-gradient(shape size at position | at position, start-color, transit-color, ……, stop-color);
/* start-color：指定渐变的起始颜色（必需） */
/* stop-color：指定渐变的终止颜色（必需） */
```
    *shape  确定圆的类型（ellipse|circle）
    *size  定义渐变的大小（closest-side|closest-corner|farthest-side|farthest-corner）
    *position  定义渐变的中心坐标。两个关键字：横坐标（left|center|right） 纵坐标（top|center|bottom）
    *transit-color  过渡颜色，可指定多个以创建更复杂的渐变效果
```html
<style>
    div {
        width: 200px;
        height: 200px;
        background: repeating-radial-gradient(circle closest-side, red, yellow 10%, green 20%);
    }
</style>
```
![此处输入图片的描述][37]

---

  [1]: http://wx1.sinaimg.cn/large/7de6638dly1fw2p79m20jj20nh0a2aak.jpg
  [2]: http://wx1.sinaimg.cn/large/7de6638dly1fw2p5mm9n6j20sx0mz3zq.jpg
  [3]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvs5nxutsxj20mo07ljs0.jpg
  [4]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvs3ut1afyj20wd08st9l.jpg
  [5]: https://wx1.sinaimg.cn/mw690/7de6638dly1fvs5v2mil7j20nb0dzmzo.jpg
  [6]: https://wx1.sinaimg.cn/mw690/7de6638dly1fvcrgq5avxj20io02dt8m.jpg
  [7]: https://wx2.sinaimg.cn/mw690/7de6638dly1fvcrix1wdcj20iq02c3yf.jpg
  [8]: https://wx2.sinaimg.cn/mw690/7de6638dly1fx0b9i2ozfj20ha02j3yi.jpg
  [9]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvcrm6qg1lj20ir02eq2w.jpg
  [10]: https://wx2.sinaimg.cn/mw690/7de6638dly1fvs07g90rij20hk0ev74n.jpg
  [11]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvjxckbu78j20re0cnaaw.jpg
  [12]: http://wx2.sinaimg.cn/large/7de6638dly1fxg85y3bdvg20nz0erq4m.gif
  [13]: https://www.runoob.com/wp-content/uploads/2015/07/3791e575c48b3698be6a94ae1dbff79d.png
  [14]: https://wx4.sinaimg.cn/mw690/7de6638dly1fvs7t1g81ij215t07xdg0.jpg
  [15]: https://wx2.sinaimg.cn/mw690/7de6638dly1fvs7xag3vfj20ko055q2v.jpg
  [16]: https://www.runoob.com/wp-content/uploads/2015/07/903d5b7df55779c03f2687a7d4d6bcea.png
  [17]: https://wx2.sinaimg.cn/mw690/7de6638dly1fvs84ejj17j20en0kywez.jpg
  [18]: https://www.runoob.com/wp-content/uploads/2015/07/2b0c39c7e7a80d5a784c8c2ca63cde17.png
  [19]: https://www.runoob.com/wp-content/uploads/2015/07/f10918ccb8a13247c9d47715a2bd2c33.png
  [20]: https://www.runoob.com/wp-content/uploads/2015/07/59e399c72daafcfcc20ede36bf32f266.png
  [21]: https://www.runoob.com/wp-content/uploads/2015/07/f41c08bb35962ed79e7686f735d6cd78.png
  [22]: https://www.runoob.com/wp-content/uploads/2015/07/240d3e960043a729bb3ff5e34987904f.jpg
  [23]: http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071016.png
  [24]: http://www.runoob.com/images/serif.gif
  [25]: http://www.w3school.com.cn/i/ct_css_margin_value.gif
  [26]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvctat85s1j20iw04hwef.jpg
  [27]: https://wx3.sinaimg.cn/mw690/7de6638dly1fvctct26xij20o50e4aah.jpg
  [28]: https://wx2.sinaimg.cn/mw690/7de6638dly1fvctc8u16aj20lp05zglj.jpg
  [29]: https://cloud.githubusercontent.com/assets/8554143/22967003/97af8828-f39f-11e6-82db-55405160eea3.gif
  [30]: https://wx1.sinaimg.cn/mw690/7de6638dly1fvs0p38dz5j20pi04ndga.jpg
  [31]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw11gar8y8j20pu05qjrp.jpg
  [32]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwwxv82uuvj20nt01dwef.jpg
  [33]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwwy0klrtgj20nq01qweg.jpg
  [34]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwy8r9vtl6j20nj08n744.jpg
  [35]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwy8shs85ej20nm08q754.jpg
  [36]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwy92vssazj20nw096wea.jpg
  [37]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwy9nrm4haj20no08qgn5.jpg