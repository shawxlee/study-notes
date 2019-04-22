# Bootstrap4 - 用于HTML、CSS和JS开发的开源工具包
Latest: v4.3.x

---

## Bootstrap4 布局
### 1、移动设备优先
为了让 Bootstrap 开发的网站对移动设备友好，确保适当的绘制和触屏缩放，需要在网页的 head 之中添加 viewport meta 标签：
```html
<!DOCTYPE html>
<html>
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

    <title>……</title>
</head>
<body>
    ……

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
</body>
</html>
```
    width=device-width  宽度是设备屏幕的宽度
    initial-scale=1  初始的缩放比例为1
    shrink-to-fit=no  自动适应手机屏幕的宽度

<br/>
### 2、容器类：`.container` / `.container-fluid`
Bootstrap 4 需要一个容器元素来包裹网站的内容

- `.container`：用于固定宽度并支持响应式布局的容器
```html
<div class="container">
  …… 
</div>
```
![此处输入图片的描述][1]

- `.container-fluid`：用于100%宽度，占据全部viewport的容器
```html
<div class="container-fluid">
  …… 
</div>
```
![此处输入图片的描述][2]

<br/>
### 3、网格系统
Bootstrap 提供了一套响应式、移动设备优先的流式网格系统，随着屏幕或viewport尺寸的增加，系统会自动分为最多 12 列：

![此处输入图片的描述][3]
<br/>
#### • 网格的基本结构：`.row` > `.col-①`/`.col-②-①`
>`.row` 行 &nbsp;&nbsp;&nbsp;`.col` 列
① `1~12` 当前div在当前行中占据的列数（每行共12列） &nbsp;&nbsp;&nbsp;`auto` 适应内容
② `sm` 小屏幕 &nbsp;&nbsp;&nbsp;`md` 中等屏幕 &nbsp;&nbsp;&nbsp;`lg` 大屏幕 &nbsp;&nbsp;&nbsp;`xl` 超大屏幕

<table>
<tr>
<th></th>
<th style="text-align:center">超小屏幕</th>
<th style="text-align:center">小屏幕</th>
<th style="text-align:center">中等屏幕</th>
<th style="text-align:center">大屏幕</th>
<th style="text-align:center">超大屏幕</th>
</tr>
<tr>
<th style="text-align:center">设备尺寸</th>
<td style="text-align:center">＜576px</td>
<td style="text-align:center">≥ 576px</td>
<td style="text-align:center">≥ 768px</td>
<td style="text-align:center">≥ 992px</td>
<td style="text-align:center">≥ 1200px</td>
</tr>
<tr>
<th style="text-align:center">class前缀</th>
<td style="text-align:center;"><code>.col-*</code></td>
<td style="text-align:center;"><code>.col-sm-*</code></td>
<td style="text-align:center;"><code>.col-md-*</code></td>
<td style="text-align:center;"><code>.col-lg-*</code></td>
<td style="text-align:center;"><code>.col-xl-*</code></td>
</tr>
<tr>
<th style="text-align:center">容器宽度</th>
<td style="text-align:center">auto</td>
<td style="text-align:center">540px</td>
<td style="text-align:center">720px</td>
<td style="text-align:center">960px</td>
<td style="text-align:center">1140px</td>
</tr>
</table>

```html
<!-- 首先创建一行row -->
<div class="row">
    <!-- 然后给每个div添加网格类 -->
    <div class="col-*-*"></div>
    <div class="col-*-*"></div>
    ……
</div>
```

##### - 等宽布局：`.col`
不在col上添加数字，自动调整为等宽布局，即同一行的每个div宽度相等
```html
<div class="row">
    <div class="col">第1块（占4列）</div>
    <div class="col">第2块（占4列）</div>
    <div class="col">第3块（占4列）</div>
</div>
<div class="row">
    <div class="col">第1块（占3列）</div>
    <!-- 若设置了一个div的宽度，其他div将自动均分剩余宽度 -->
    <div class="col-6">第2块（占6列）</div>
    <div class="col">第3块（占3列）</div>
</div>
```
![此处输入图片的描述][4]

##### - 内容布局：`.col-auto` `.col-*-auto`
使div的宽度跟随内容调整，且固定为内容的宽度，不受其他div影响
```html
<div class="row">
    <div class="col-2">……</div>
    <div class="col-auto">.col-*-auto使div的宽度跟随内容</div>
    <div class="col">……</div>
	<div class="col">……</div>
</div>
```
![此处输入图片的描述][5]

##### - 响应式布局：`.col-sm|md|lg|xl-*`
适应不同屏幕尺寸的布局，而在移动设备上，多个列将会上下堆叠排版
```html
<div class="row">
    <div class="col-md-3">……</div>
    <div class="col-md-3">……</div>
    <div class="col-md-3">……</div>
    <div class="col-md-3">……</div>
</div>
<!-- 并排显示四个div，当屏幕为md时每个div占3列 -->
    
<div class="row">
    <div class="col-md-4">……</div>
    <div class="col-md-8">……</div>
</div>
<!-- 并排显示两个div，当屏幕为md时，第一个占4列，第二个占8列 -->

<div class="row">
    <div class="col-md-3 col-lg-6">……</div>
    <div class="col-md-9 col-lg-6">……</div>
</div>
<!-- 并排显示两个div，md时分别占比25%、75%，lg时分别占比50%、50% -->

<div class="row">
    <div class="col-sm-12 col-md-9 col-lg-6 col-xl-3">……</div>
    ……
</div>
<!-- 随着屏幕尺寸的变化，应用不同的布局 -->
```

##### - 嵌套布局：`.col` > `.row`
在现有列中添加一组新row，最多可添加12个或更少的列
```html
<div class="row">
    <div class="col">一级div</div>
    <div class="col">一级div
        <div class="row">
            <div class="col-5">二级div</div>
            <div class="col">二级div</div>
            <div class="col">二级div</div>
        </div>
    </div>
</div>
```
![此处输入图片的描述][6]
<br>
#### • 网格的排列方式
##### - row垂直对齐：`.align-items-start|center|end`
```html
<div class="container">
    <div class="row align-items-start">
        <div class="col">start顶端对齐</div>
        ……
    </div>
    <div class="row align-items-center">
        <div class="col">center垂直居中</div>
        ……
    </div>
    <div class="row align-items-end">
        <div class="col">end底端对齐</div>
        ……
    </div>
</div>
```

##### - row水平对齐：`.justify-content-start|center|end|around|between`
```html
<div class="container">
    <div class="row justify-content-start">
        <div class="col-3">start左对齐</div>
        ……
    </div>
    <div class="row justify-content-center">
        <div class="col-3">center水平居中</div>
        ……
    </div>
    <div class="row justify-content-end">
        <div class="col-3">end右对齐</div>
        ……
    </div>
    <div class="row justify-content-around">
        <div class="col-3">around分散对齐</div>
        ……
    </div>
    <div class="row justify-content-between">
        <div class="col-3">between两端对齐</div>
        ……
    </div>
</div>
```
![此处输入图片的描述][7]

##### - col垂直对齐：`.align-self-start|center|end`
```html
<div class="container">
    <div class="row">
        <div class="col align-self-start">……</div>
        <div class="col align-self-center">……</div>
        <div class="col align-self-end">……</div>
    </div>
</div>
```

##### - 清除内外边距：`.no-gutters`
```html
<div class="container">
    <div class="row no-gutters">
        <div class="col">……</div>
        <div class="col">……</div>
        <div class="col">……</div>
    </div>
</div>
```
![此处输入图片的描述][8]

##### - 强制换行：`.w-100`
```html
<div class="row">
    <div class="col">……</div>
    <div class="col">……</div>
    <!-- 插入一个带.w-100的空div可强制换行 -->
    <div class="w-100"></div>
    <div class="col">……</div>
    <div class="col">……</div>
</div>

<!-- 若一行中div的总宽度超过12列，则会自动换行 -->
```
![此处输入图片的描述][9]

##### - 重新排序：`.order-*|first|last` `.order-sm|md|lg|xl-*`
按照*的大小重新排列div的显示顺序，其中1≤ * ≤12
>优先级：**.order-first|last** ＞ **无order** ＞ **.order-* / .order-sm|md|lg|xl-***
```html
<div class="row">
	<div class="col">这是第一个div，无order，所以排在第二个</div>
    <div class="col order-12">这是第二个div，但添加了.order-12，所以排在第六个</div>
    <div class="col order-1">这是第三个div，但添加了.order-1，所以排在第四个</div>
    <div class="col order-last">这是第四个div，但添加了.order-last，所以排在最后</div>
	<div class="col">这是第五个div，无order，所以排在第三个</div>
	<div class="col order-3">这是第六个div，但添加了.order-3，所以排在第五个</div>
	<div class="col order-first">这是最后一个div，但添加了.order-first，所以排在最前</div>
</div>
```
![此处输入图片的描述][10]

##### - 偏移列：`.offset-sm|md|lg|xl-*`
在规定屏幕尺寸上使用偏移，会把一个div的左外边距增加*列，其中1≤ * ≤11
```html
<div class="row" >
      <div class="col-md-6 offset-md-3">……</div>
</div>
<!-- 当屏幕为md时，div向右偏移3列（此时为居中显示） -->

<!-- 或可使用外边距工具.m*-*-*调整div之间的距离 -->
```

---

## Bootstrap4 样式
>**全局默认样式：**
font-size: 16px;
line-height: 1.5;
font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;

### 1、标签/属性样式重启
- `<abbr>`
```html
<p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>
```
![此处输入图片的描述][11]

- `<address>`
```html
<address>
Written by <strong>Shaw</strong><br>
Email: <a href="mailto:shaw@example.com">shaw@example.com</a>
</address>
```
![此处输入图片的描述][12]

- `<blockquote>`
```html
<h1>About WWF</h1>
<p>Here is a quote from WWF's website:</p>
<blockquote cite="https://www.worldwildlife.org/about">
    For nearly 60 years, WWF has been protecting the future of nature.
    The world’s leading conservation organization, WWF works in 100 countries and is supported by more than one million members in the United States and close to five million globally. WWF's unique way of working combines global reach with a foundation in science, involves action at every level from local to global, and ensures the delivery of innovative solutions that meet the needs of both people and nature.
</blockquote>
```
![此处输入图片的描述][13]

- `<button>`
```html
<button type="button">button按钮（IE默认值）</button>
<button type="submit">submit按钮（其他浏览器默认值）</button>
```
![此处输入图片的描述][14]

- `<code>`
```html
<p>HTML元素 <code>&lt;span&gt;</code>, <code>&lt;section&gt;</code>, <code>&lt;div&gt;</code> 用于定义部分文档内容。</p>
```
![此处输入图片的描述][15]

- `<del>` `<em>` `<ins>` `<mark>` `<s>` `<small>` `<strong>` `<u>`
```html
<del>This line of text is meant to be treated as deleted text.</del>
<em>This line rendered as italicized text.</em>
<ins>This line of text is meant to be treated as an addition to the document.</ins>
You can use the mark tag to <mark>highlight</mark> text.
<s>This line of text is meant to be treated as no longer accurate.</s>
<small>This line of text is meant to be treated as fine print.</small>
<strong>This line rendered as bold text.</strong>
<u>This line of text will render as underlined</u>
```
![此处输入图片的描述][16]

- `<details>` > `<summary>`
```html
<details>
    <summary>点击展开详情</summary>
    <p>这是被折叠隐藏的详情内容，展开后才可见</p>
</details>
<br>
<details open>
    <summary>详情设置为可见，点击折叠</summary>
    <p>这是被折叠隐藏的详情内容，展开后才可见</p>
</details>
```
![此处输入图片的描述][17]

- `<dl>` > `<dt>` `<dd>`

>★ 可使用网格系统布局
```html
<dl>
	<dt>项目一名称</dt>
	<dd>这是对项目一的描述</dd>
	<dt>项目二名称</dt>
	<dd>这是对项目二的描述</dd>
	……
</dl>
```
![此处输入图片的描述][18]

- `<form>` > `<fieldset>` > `<legend>` `<label>` `<input>`
```html
<form>
	<fieldset>
		<legend>Personal Information</legend>
		<p>What's your name?
		<input type="text" name="name" placeholder="My name is..."></p>
		<p>What's your gender?
		<label for="male"></label>
	    <input id="male" type="radio" name="sex" checked>Male
	    <label for="female"></label>
	    <input id="female" type="radio" name="sex">Female</p>
		<input type="submit" value="Submit">
	</fieldset>
</form>
```
![此处输入图片的描述][19]

- `<h1>`~`<h6>` `<p>`
```html
<h1>h1标题（2.5rem = 40px）</h1>
<h2>h2标题（2rem = 32px）</h2>
<h3>h3标题（1.75rem = 28px）</h3>
<h4>h4标题（1.5rem = 24px）</h4>
<h5>h5标题（1.25rem = 20px）</h5>
<h6>h6标题（1rem = 16px）</h6>
<p>p文字段落（1rem = 16px）</p>
```
![此处输入图片的描述][20]

- `<kbd>`
```html
使用快捷键 <kbd>Ctrl</kbd> + <kbd>C</kbd> 进行复制
```
![此处输入图片的描述][21]

- `<ol>` > `<li>`
```html
<ol>
	<li>第1项</li>
	    <ol>
	    	<li>第1.1项</li>
	    	<li>第1.2项</li>
			    <ol>
	    	        <li>第1.2.1项</li>
	    	        <li>第1.2.2项</li>
	            </ol>
	    </ol>
	<li>第2项</li>
	<li>第3项</li>
	    <ol>
	    	<li>第3.1项</li>
	    </ol>
</ol>
```
![此处输入图片的描述][22]

- `<pre>`
```html
<pre>
<code>&lt;p&gt;Sample text here&lt;/p&gt;
&lt;p&gt;And another line of sample text here&lt;/p&gt;</code>
</pre>
```
![此处输入图片的描述][23]

- `<samp>`
```html
字符序列 <samp>ae</samp> 可能会被转换为 &aelig; 连字字符
```
![此处输入图片的描述][24]

- `<select>` > `<optgroup>` > `<option>`
```html
<select>
	<optgroup label="Junior">
		<option value="junior1">junior 1</option>
		<option value="junior2">junior 2</option>
		<option value="junior3">junior 3</option>
	</optgroup>
	<optgroup label="Senior">
		<option value="senior1">senior 1</option>
		<option value="senior2">senior 2</option>
		<option value="senior3">senior 3</option>
	</optgroup>
</select>
```
![此处输入图片的描述][25]

- `<table>` > `<caption>` `<tr>` > `<th>`/`<td>`
```html
<table border="1">
    <caption>caption元素不再作为表格标题，而是位于下方的一段描述文本</caption>
    <tr>
        <th>表头：1行1列</th>
        <th>表头：1行2列</th>
    </tr>
    <tr>
        <td>内容：2行1列</td>
        <td>内容：2行2列</td>
    </tr>
</table>
```
![此处输入图片的描述][26]

- `textarea`
```html
<textarea>这是一个多行文本框，只能垂直调整大小</textarea>
```
![此处输入图片的描述][27]

- `<ul>` > `<li>`
```html
<ul>
	<li>第1项</li>
	    <ul>
	    	<li>第1.1项</li>
	    	<li>第1.2项</li>
			    <ul>
	    	        <li>第1.2.1项</li>
	    	        <li>第1.2.2项</li>
	            </ul>
	    </ul>
	<li>第2项</li>
	<li>第3项</li>
	    <ul>
	    	<li>第3.1项</li>
	    </ul>
</ul>
```
![此处输入图片的描述][28]

- `<var>`
```html
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>
```
![此处输入图片的描述][29]

- `display: none` → `hidden`
```html
<p hidden>这个元素会被隐藏</p>
```

<br/>
### 2、排版样式类
#### • 标题类：`.h1|h2|h3|h4|h5|h6`
当想要匹配标题的字体样式但不能使用关联的HTML元素时
```html
<p class="h1">.h1标题（2.5rem = 40px）</p>
<p class="h2">.h2标题（2rem = 32px）</p>
<p class="h3">.h3标题（1.75rem = 28px）</p>
<p class="h4">.h4标题（1.5rem = 24px）</p>
<p class="h5">.h5标题（1.25rem = 20px）</p>
<p class="h6">.h6标题（1rem = 16px）</p>
<p>p文字段落（1rem = 16px）</p>
```
![此处输入图片的描述][30]
<br/>
#### • 扩大标题：`.display-1|2|3|4`
```html
<h1 class="display-1">display-1标题</h1>
<h1 class="display-2">display-2标题</h1>
<h1 class="display-3">display-3标题</h1>
<h1 class="display-4">display-4标题</h1>

<!-- display-*的样式是固定的，与标签类型无关 -->
```
![此处输入图片的描述][31]
<br/>
#### • 突出段落：`.lead`
```html
<p>这是一段普通文本</p>
<p class="lead">这是一段突出文本</p>
<p>这是一段普通文本</p>
```
![此处输入图片的描述][32]
<br/>
#### • 高亮文本：`.mark`
```html
<p class="mark">这是一行高亮的文本</p>
<p>文本中插入<span class="mark">带.mark的span</span>高亮局部</p>
```
![此处输入图片的描述][33]
<br/>
#### • 缩小文本字号：`.small`
缩小文本字号为父元素字号的85%
```html
<p>这是一段普通文本，字号为16px</p>
<p class="small">这是一段.small文本，字号为13.6px</p>

<div style="font-size: 30px;">
    <p>这是父元素设定字号30px下的普通文本</p>
    <p class="small">这是30px下的.small文本，字号为25.5px</p>
</div>
```
![此处输入图片的描述][34]
<br/>
#### • 小号大写字母缩写：`.initialism`
显示在abbr元素中的文本以小号字体展示，且可以将小写字母转换为大写字母
```html
<p>The <abbr class="initialism" title="World Health Organization">who</abbr> was founded in 1948.</p>
```
![此处输入图片的描述][35]
<br/>
#### • 突出引用内容：`.blockquote` > `.blockquote-footer`
```html
<h1>About WWF</h1>
<!-- 向<blockquote>标签添加.blockquote可突出引用内容 -->
<blockquote class="blockquote">
    <p>For nearly 60 years, WWF has been protecting the future of nature.
        The world’s leading conservation organization, WWF works in 100 countries and is supported by more than one million members in the United States and close to five million globally. WWF's unique way of working combines global reach with a foundation in science, involves action at every level from local to global, and ensures the delivery of innovative solutions that meet the needs of both people and nature.</p>
    <!-- 向<footer>标签添加.blockquote-footer生成引用注脚，将引用源包裹在cite标签内，通过title属性备注源信息 -->
    <footer class="blockquote-footer">Quote from <cite title="https://www.worldwildlife.org/about">WWF</cite>'s website</footer>
</blockquote>
```
![此处输入图片的描述][36]
<br/>
#### • 清除列表样式：`.list-unstyled`
```html
<!-- 向父元素添加.list-unstyled，只对一级列表项有效 -->
<ul class="list-unstyled">
	<li>第1项</li>
	    <ul>
	    	<li>第1.1项</li>
	    	<li>第1.2项</li>
			    <ul>
	    	        <li>第1.2.1项</li>
	    	        <li>第1.2.2项</li>
	            </ul>
	    </ul>
	<li>第2项</li>
	<li>第3项</li>
	    <ul>
	    	<li>第3.1项</li>
	    </ul>
</ul>
```
![此处输入图片的描述][37]
<br/>
#### • 行内并排列表项：`.list-inline` > `.list-inline-item`
```html
<ul class="list-inline">
    <li class="list-inline-item">第一项</li>
    <li class="list-inline-item">第二项</li>
    <li class="list-inline-item">第三项</li>
</ul>
```
![此处输入图片的描述][38]

<br/>
### 3、代码样式类：`.pre-scrollable`
使 pre 元素可滚动，代码块高度超出 340px 时，就会在 Y 轴出现滚动条
```html
<pre class="pre-scrollable">
使 pre 元素可滚动
代码块区域最大高度为 340px
一旦超出这个高度
就会在 Y 轴出现滚动条
</pre>
```
![此处输入图片的描述][39]

<br/>
### 4、图片样式类
#### • 响应式图像：`.img-fluid`
```html
<img src="/image.jpg" class="img-fluid" alt="响应式图像">

<!-- max-width:100% 和 height:auto 使图像适应父元素缩放比例 -->
```
![此处输入图片的描述][40]
<br/>
#### • 1px圆角边框：`.img-thumbnail`
```html
<img src="/image.jpg" class="img-thumbnail" alt="1px圆角">
```
![此处输入图片的描述][41]

<br/>
### 5、表格样式类：`.table`
```html
<table class="table">
  <thead>
    <tr>
      <th>#</th>
      <th>First</th>
      <th>Last</th>
      <th>Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
  </tbody>
</table>
```
![此处输入图片的描述][42]
<br/>
#### • 表格颜色：`.table-active|primary|secondary|success|danger|warning|info|light|dark`
```html
<!-- 表格整体背景色 -->
<table class="table table-active">
  <!-- 行背景色 -->
  <tr class="table-primary">
    <!-- 单元格背景色 -->
    <th class="table-secondary">1</th>
    <td class="table-success">Mark</td>
    ……
  </tr>
</table>
```
![此处输入图片的描述][43]
<br/>
#### • 斑马纹：`.table-striped`
```html
<table class="table table-striped">
    ……
</table>
```
![此处输入图片的描述][44]
<br/>
#### • 单元格边框：`.table-bordered`
```html
<table class="table table-bordered">
    ……
</table>
```
![此处输入图片的描述][45]
<br/>
#### • 清除表格边框：`.table-borderless`
```html
<table class="table table-borderless">
    ……
</table>
```
![此处输入图片的描述][46]
<br/>
#### • 悬停行：`.table-hover`
```html
<table class="table table-hover">
    ……
</table>
```
![此处输入图片的描述][47]
<br/>
#### • 小尺寸表格：`.table-sm`
```html
<table class="table table-sm">
    ……
</table>
```
![此处输入图片的描述][48]
<br/>
#### • 表头颜色：`.thead-light|dark`
```html
<table class="table">
  <thead class="thead-light">
    ……
  </thead>
  <tbody>
    ……
  </tbody>
</table>
```
![此处输入图片的描述][49]
<br/>
#### • 响应式表格：`.table-responsive`/`.table-responsive-sm|md|lg|xl` > `.table`
```html
<div class="table-responsive">
  <table class="table">
    ……
  </table>
</div>
```
![此处输入图片的描述][50]

<br/>
### 6、数据样式类：`.figure` > `.figure-img`+`.figure-caption`
```html
<p>这是一段主要内容这是一段主要内容这是一段主要内容</p>
<figure class="figure">
    <p>这是一段附加内容：</p>
    <img src="/img.jpg" alt="附加图片" class="figure-img" width="50%">
    <figcaption class="figure-caption">附加内容的小标题</figcaption>
</figure>
```
![此处输入图片的描述][51]

---

## Bootstrap4 组件
### 1、路径导航：`.breadcrumb` > `.breadcrumb-item` `.active`
路径导航表示当前页面在导航层次结构内的位置，可以显示日期、类别或标签等
```html
<!-- 以一个nav标签开始 -->
<nav>
    <!-- 创建一个带.breadcrumb的有序列表ol -->
    <ol class="breadcrumb">
        <!-- 向每个li添加.breadcrumb-item，父级项内包裹a链接 -->
	    <li class="breadcrumb-item"><a href="#">2018</a></li>
	    <li class="breadcrumb-item"><a href="#">Nov.</a></li>
	    <!-- 当前项li用.active标记 -->
	    <li class="breadcrumb-item active">08th</li>
    </ol>
</nav>

<!-- 各路径间的分隔符已经自动通过CSS设置好了 -->
```
![此处输入图片的描述][52]

<br/>
### 2、卡片：`.card`
>★ 可使用网格系统布局

#### • 主体内容：`.card-body` > `.card-title`/`.card-subtitle`/`.card-text`/`.card-link`
```html
<div class="card" style="width: 18rem;">
    <div class="card-body">
        <!-- 在.card-body下创建标题/文本/链接 -->
        <h3 class="card-title">这是卡片的标题</h3>
        <h5 class="card-subtitle">这是卡片的副标题</h5>
        <p class="card-text">这是卡片的文本内容</p>
        <a href="#" class="card-link">这是一条链接</a>
    </div>
</div>
```
![此处输入图片的描述][53]
<br/>
#### • 封面图：`.card-img-top`
```html
<div class="card" style="width: 18rem;">
    <!-- 在.card下插入带.card-img-top的img标签 -->
    <img src="/img1.jpg" class="card-img-top">
    <div class="card-body">这是卡片的主体内容</div>
    <!-- .card-img-top的位置即图片的位置 -->
    <img src="/img2.jpg" class="card-img-top">
</div>

<!-- 图片默认填充，按原始比例缩放 -->
```
![此处输入图片的描述][54]
<br/>
#### • 图片背景：`.card-img` + `.card-img-overlay`
将图像转换为卡片背景，并在背景中添加文本内容
```html
<div class="card" style="width: 18rem;">
    <img src="/img.jpg" class="card-img">
    <!-- 在.card-img后插入带.card-img-overlay的div -->
	<div class="card-img-overlay">这是.card-img-overlay中的内容</div>
    <div class="card-body">这是.card-body中的内容</div>
</div>

<!-- 图片默认填充，按原始比例缩放 -->
```
![此处输入图片的描述][55]
<br/>
#### • 列表组：`.list-group` `.list-group-flush` > `.list-group-item`
```html
<div class="card" style="width: 10rem;">
    <!-- 在.card下插入带.list-group和.list-group-flush的ul标签 -->
    <ul class="list-group list-group-flush">
        <!-- 在li标签内添加.list-group-item -->
        <li class="list-group-item">列表项1</li>
        <li class="list-group-item">列表项2</li>
        <li class="list-group-item">列表项3</li>
    </ul>
</div>
```
![此处输入图片的描述][56]
<br/>
#### • 页眉和页脚：`.card-header` + `.card-footer`
```html
<div class="card" style="width: 18rem;">
    <!-- 在.card下开头插入带.card-header的div/h*标签 -->
    <div class="card-header">这是卡片的页眉</div>
    <div class="card-body">这是卡片的主体</div>
    <!-- 在.card下末尾插入带.card-footer的div/h*标签 -->
    <div class="card-footer">这是卡片的页脚</div>
</div>

<!-- .card-header和.card-footer可添加到h*标签中强调文本 -->
```
![此处输入图片的描述][57]
<br/>
#### • 卡片导航：( `.card-header` > `.nav` `.nav-tabs|pills` `.card-header-tabs|pills` > `.nav-item` ) + ( `.card-body` > `.tab-content` )
```html
<div class="card" style="width: 30rem;">
	<div class="card-header">
		<!-- 在.card-header下创建tab导航组件，添加.card-header-tabs -->
		<ul class="nav nav-tabs card-header-tabs">
		    <!-- 当前选项卡用.active标记 -->
			<li class="nav-item"><a href="#part1" class="nav-link active" data-toggle="tab">导航链接1</a></li>
			<li class="nav-item"><a href="#part2" class="nav-link" data-toggle="tab">导航链接2</a></li>
			<li class="nav-item"><a href="#part3" class="nav-link" data-toggle="tab">导航链接3</a></li>
		</ul>
	</div>
	<div class="card-body">
	    <!-- 在.card-body下创建对应的选项卡组件 -->
		<div class="tab-content">
		    <!-- 当前页面用.active标记 -->
			<div class="tab-pane active" id="part1">这是第一部分</div>
			<div class="tab-pane" id="part2">这是第二部分</div>
			<div class="tab-pane" id="part3">这是第三部分</div>
		</div>
	</div>
</div>
```
![此处输入图片的描述][58]
```html
<div class="card" style="width: 30rem;">
	<div class="card-header">
		<!-- 在.card-header下创建pill导航组件，添加.card-header-pills -->
		<ul class="nav nav-pills card-header-pills">
			……
		</ul>
	</div>
	<div class="card-body">
		<div class="tab-content">
			……
		</div>
	</div>
</div>
```
![此处输入图片的描述][59]
<br/>
### C2、卡片组
#### 紧邻卡片组：`.card-group`
将一系列卡片从左到右排列在一行显示，默认等宽且等高，卡片之间无间距紧邻
```html
<!-- 将多个卡片包裹在一个带.card-group的div里 -->
<div class="card-group">
    <div class="card">
        <img class="card-img" src="/image1.jpg" alt="image1">
        <div class="card-body">卡片1主体内容</div>
    </div>
    <div class="card">
        <div class="card-header">卡片2页眉内容</div>
        <img class="card-img" src="/image2.jpg" alt="image2">
        <div class="card-body">卡片2主体内容</div>
        <div class="card-footer">卡片2页脚内容</div>
    </div>
    <div class="card">
        <div class="card-header">卡片3页眉内容</div>
        <img class="card-img" src="/image3.jpg" alt="image3">
        <div class="card-body">卡片3主体内容</div>
        <div class="card-footer">卡片3页脚内容</div>
    </div>
    ……
</div>

<!-- 顶部按顶端对齐，底部按底端对齐，各部分高度随内容调整 -->
```
![此处输入图片的描述][60]

#### 间隔卡片组：`.card-deck`
将一系列卡片从左到右排列在一行显示，默认等宽且等高，卡片之间等间距间隔
```html
<!-- 将多个卡片包裹在一个带.card-deck的div里 -->
<div class="card-deck">
    <div class="card">
        ……
    </div>
    <div class="card">
        ……
    </div>
    <div class="card">
        ……
    </div>
    ……
</div>

<!-- 顶部按顶端对齐，底部按底端对齐，各部分高度随内容调整 -->
```
![此处输入图片的描述][61]

#### 堆砌卡片组：`.card-columns`
将一系列卡片从上到下堆砌成三列，默认等宽，每个卡片的高度根据内容调整
```html
<!-- 将多个卡片包裹在一个带.card-columns的div里 -->
<div class="card-columns">
    <div class="card">
        ……
    </div>
    <div class="card">
        ……
    </div>
    <div class="card">
        ……
    </div>
    ……
</div>
```
![此处输入图片的描述][62]

<br/>
### 3、下拉菜单
#### • 基础下拉/弹出菜单：`.dropdown` > [ `.dropdown-toggle` `data-toggle="dropdown"` + ( `.dropdown-menu` > `.dropdown-item` ) ]
```html
<!-- 将触发器和菜单包裹在带.dropdown的div里，指定一个下拉菜单 -->
<div class="dropdown">
    <!-- 向触发器添加.dropdown-toggle和data-toggle="dropdown" -->
	<button class="dropdown-toggle" type="button" data-toggle="dropdown">下拉菜单</button>
	<!-- 添加带.dropdown-menu的div标签，创建一个下拉菜单 -->
	<div class="dropdown-menu">
	    <!-- 添加带.dropdown-item的a标签，创建菜单列表 -->
		<a class="dropdown-item" href="#">链接1</a>
		<a class="dropdown-item" href="#">链接2</a>
		<a class="dropdown-item" href="#">链接3</a>
	</div>
</div>
```
![此处输入图片的描述][63]
<br/>
#### • 按钮下拉/弹出菜单：`.btn-group` > [ `.dropdown-toggle` `data-toggle="dropdown"` + ( `.dropdown-menu` > `.dropdown-item` ) ]
```html
<!-- 将按钮和菜单包裹在带.btn-group的div里，创建按钮下拉菜单 -->
<div class="btn-group">
    <!-- 任何按钮颜色和按钮尺寸的类都适用于按钮下拉菜单 -->
	<button class="dropdown-toggle" type="button" data-toggle="dropdown">按钮下拉菜单</button>
	<div class="dropdown-menu">
		<a class="dropdown-item" href="#">链接1</a>
		<a class="dropdown-item" href="#">链接2</a>
		<a class="dropdown-item" href="#">链接3</a>
	</div>
</div>
```
![此处输入图片的描述][64]

##### - 菜单弹出方向：`.dropup`/`.dropright`/`.dropleft`
```html
<!-- 在.btn-group后添加方向类，使触发的下拉菜单向上/右/左打开 -->
<div class="btn-group dropup">
	……
</div>

<!-- 仅当弹出方向有足够空间显示菜单时才能正确弹出 -->
```
![此处输入图片的描述][65]

##### - 菜单的位置：`data-offset="……"`/`data-reference="……"`
```html
<div class="dropdown">
    <!-- 在触发按钮中添加data-offset="……" -->
    <button type="button" class="dropdown-toggle" data-toggle="dropdown" data-offset="10,20">Offset </button>
    <div class="dropdown-menu">
      ……
    </div>
</div>
```
```html
<div class="dropdown">
    <!-- 在触发按钮中添加data-reference="……" -->
    <button type="button" class="dropdown-toggle" data-toggle="dropdown" data-reference="parent">Reference </button>
    <div class="dropdown-menu">
      ……
    </div>
</div>
```
![此处输入图片的描述][66]

##### - 分裂式按钮菜单：`.dropdown-toggle-split`
```html
<div class="btn-group">
    <!-- 将按钮的button与下拉菜单触发器的button分开书写 -->
	<button class="btn btn-outline-primary" type="button">按钮下拉菜单</button>
	<button class="btn btn-primary dropdown-toggle dropdown-toggle-split" type="button" data-toggle="dropdown">
    </button>
	<div class="dropdown-menu">
		……
	</div>
</div>
```
![此处输入图片的描述][67]

##### - 菜单右对齐：`.dropdown-menu-right`
下拉菜单默认沿着父元素的上沿和左侧被定位为100%宽度，可以改为右对齐
```html
<div class="btn-group">
	<button class="dropdown-toggle" type="button" data-toggle="dropdown">菜单右对齐</button>
	<!-- 向.dropdown-menu添加.dropdown-menu-right使菜单右对齐 -->
	<div class="dropdown-menu dropdown-menu-right">
        ……
    </div>
</div>

<!-- 仅当div左侧有足够空间显示下拉菜单时才能右对齐 -->
```
![此处输入图片的描述][68]

##### - 菜单响应式对齐：`data-display="static"` > `.dropdown-menu-sm|md|lg|xl-right` `.dropdown-menu-sm|md|lg|xl-left`
```html
<div class="btn-group">
    <button type="button" class="dropdown-toggle" data-toggle="dropdown" data-display="static">Left-aligned but right aligned when large screen </button>
    <!-- 大屏幕时右对齐 -->
    <div class="dropdown-menu dropdown-menu-lg-right">
        ……
    </div>
</div>
```
```html
<div class="btn-group">
    <button type="button" class="dropdown-toggle" data-toggle="dropdown" data-display="static">Right-aligned but left aligned when large screen </button>
    <!-- 大屏幕时左对齐 -->
    <div class="dropdown-menu dropdown-menu-right dropdown-menu-lg-left">
        ……
    </div>
</div>
```

##### - 菜单中的文本/标题/分割线：`.dropdown-item-text`/`.dropdown-header`/`.dropdown-divider`
```html
<div class="btn-group">
	<button class="dropdown-toggle" type="button" data-toggle="dropdown">Dropdown</button>
	<!-- .dropdown-menu下可包含丰富的文本或表单内容 -->
	<div class="dropdown-menu">
	    <!-- 在菜单项之间添加带.dropdown-item-text的文本标签 -->
	    <span class="dropdown-item-text">Dropdown item text</span>
	    <!-- 在菜单项之间添加带.dropdown-header的文本标签 -->
	    <h6 class="dropdown-header">Dropdown header</h6>
	    <a class="dropdown-item" href="#">Action</a>
	    <a class="dropdown-item" href="#">Another action</a>
	    <!-- 在菜单项之间添加带.dropdown-divider的空div -->
		<div class="dropdown-divider"></div>
	    <a class="dropdown-item" href="#">Something else here</a>
	</div>
</div>
```
![此处输入图片的描述][69]

<br/>
### 4、表单
>★ 可使用网格系统布局

#### • 输入表单：`.form-group` > `.form-control`/`.form-control-file|range`
```html
<!-- 以一个form标签开始 -->
<form>
    <!-- 在form下创建带.form-group的块，作为一组 -->
	<div class="form-group">
		<label for="input1">input - .form-control</label>
		<!-- 向input添加.form-control -->
		<input type="text" class="form-control" id="input1">
	</div>
	
	<div class="form-group">
		<label for="select1">select - .form-control</label>
		<!-- 向select添加.form-control -->
		<select class="form-control" id="select1">
			<option>1</option>
			<option>2</option>
			<option>3</option>
		</select>
	</div>
	
	<div class="form-group">
		<label for="textarea1">textarea - .form-control</label>
		<!-- 向textarea添加.form-control -->
		<textarea class="form-control" id="textarea1" rows="3"></textarea>
	</div>
	
	<div class="form-group">
		<label for="file1">input[type="file"] - .form-control-file</label>
		<!-- 向type="file"添加.form-control-file -->
		<input type="file" class="form-control-file" id="file1">
	</div>
	
	<div class="form-group">
		<label for="range1">input[type="range"] - .form-control-range</label>
		<!-- 向type="range"添加.form-control-range -->
		<input type="range" class="form-control-range" id="range1">
	</div>
</form>
```
![此处输入图片的描述][70]

##### - 输入框尺寸：`.form-control-sm|lg`
```html
<!-- 在.form-control后添加.form-control-sm|lg -->
<input type="text" class="form-control form-control-sm">
```
![此处输入图片的描述][71]

##### - 纯文本：`.form-control-plaintext`
```html
<!-- .form-control-plaintext可清除边框样式，显示纯文本 -->
<input type="text" class="form-control-plaintext" placeholder=".form-control-plaintext" readonly>
```
![此处输入图片的描述][72]

##### - 自定义下拉框样式：`.custom-select`
```html
<!-- 向select元素添加.custom-select -->
<select class="custom-select">
    <option selected>.custom-select</option>
    <option value="1">option 1</option>
    <option value="2">option 2</option>
    <option value="3">option 3</option>
</select>

<!-- select元素无法用br隔开，需用设置上/下外边距 -->
```
![此处输入图片的描述][73]

##### - 自定义下拉框尺寸：`.custom-select-sm|lg`
```html
<!-- 在.custom-select后添加.custom-select-sm|lg，可改变尺寸 -->
<select class="custom-select custom-select-sm">
    ……
</select>
```
![此处输入图片的描述][74]

##### - 自定义区间条样式：`.custom-range`
```html
<label for="range1">.custom-range</label>
<!-- 向type="range"添加.custom-range -->
<input type="range" id="range1" class="custom-range">

<label for="range2">区间0~5，每步0.5</label>
<input type="range" id="range2" class="custom-range" min="0" max="5" step="0.5">
```
![此处输入图片的描述][75]

##### - 帮助文本：`.form-text`
```html
<label for="password1">设置密码：</label>
<input type="password" class="form-control" id="password1">
<!-- 插入内联文本元素，添加.form-text -->
<small class="form-text text-muted" id="password1">您的密码长度必须为8-20个字符，包含字母和数字，且不得包含空格，特殊字符或表情符号。</small>
```
![此处输入图片的描述][76]
<br/>
#### • 自定义文件浏览框：`.custom-file` > `.custom-file-input`+`.custom-file-label`
```html
<!-- 将.form-group替换为.custom-file -->
<div class="custom-file">
    <!-- 将.form-control-file替换为.custom-file-input -->
    <input type="file" id="file1" class="custom-file-input">
    <!-- 向label添加.custom-file-label -->
    <label class="custom-file-label" for="file1">Choose file</label>
</div>

<div class="custom-file">
    <input type="file" id="file2" class="custom-file-input">
    <!-- 添加 data-browse="……" 来修改浏览键的文本 -->
    <label class="custom-file-label" for="file2" data-browse="浏览">选择文件</label>
</div>
```
![此处输入图片的描述][77]
<br/>
#### • 选框表单：`.form-check` > `.form-check-input`+`.form-check-label`
```html
<form>
    <!-- 在form下创建带.form-check的div，作为一组 -->
    <div class="form-check">
        <!-- 向checkbox、radio类型添加.form-check-input -->
        <input type="checkbox" id="checkbox1" class="form-check-input">
        <!-- 向label元素添加.form-check-label -->
        <label class="form-check-label" for="checkbox1">复选框1</label>
    </div>
    <div class="form-check">
        <input type="checkbox" id="checkbox2" class="form-check-input">
        <label class="form-check-label" for="checkbox2">复选框2</label>
    </div>
</form>
```
![此处输入图片的描述][78]

##### - 内联选框：`.form-check-inline`
```html
<!-- 每个.form-check后添加.form-check-inline，可将选项排成一行 -->
<div class="form-check form-check-inline">
    ……
</div>
<div class="form-check form-check-inline">
    ……
</div>
……
```
![此处输入图片的描述][79]

##### - 无标签选框：`.position-static`
```html
<div class="form-check">
    <!-- 若无标签，需在.form-check-input后添加.position-static -->
    <input type="checkbox" class="form-check-input position-static" id="checkbox1">
</div>
<div class="form-check">
    <input type="radio" class="form-check-input position-static" name="blankRadio" value="radio1">
</div>
……
```
![此处输入图片的描述][80]
<br/>
#### • 自定义选框样式：`.custom-control` `.custom-checkbox|switch|radio` > `.custom-control-input`+`.custom-control-label`
```html
<form>
    <!-- 将.form-check替换为.custom-control加.custom-checkbox -->
    <div class="custom-control custom-checkbox">
        <!-- 将.form-check-input替换为.custom-control-input -->
        <input type="checkbox" id="checkbox1" class="custom-control-input">
        <!-- 将.form-check-label替换为.custom-control-label -->
        <label class="custom-control-label" for="checkbox1">.custom-checkbox</label>
    </div>
    
    <!-- 将.custom-checkbox替换为.custom-switch -->
    <div class="custom-control custom-switch">
        <input type="checkbox" id="checkbox2" class="custom-control-input">
        <label class="custom-control-label" for="checkbox2">.custom-switch</label>
    </div>
</form>
```
```html
<form>
    <!-- 将.form-check替换为.custom-control，并添加.custom-radio -->
    <div class="custom-control custom-radio">
        <input type="radio" name="group" id="radio1" class="custom-control-input">
        <label class="custom-control-label" for="radio1">.custom-radio 1</label>
    </div>
    <div class="custom-control custom-radio">
        <input type="radio" name="group" id="radio2" class="custom-control-input">
        <label class="custom-control-label" for="radio2">.custom-radio 2</label>
    </div>
</form>
```
![此处输入图片的描述][81]

##### - 内联自定义选框：`.custom-control-inline`
```html
<div class="custom-control custom-radio custom-control-inline">
    ……
</div>
<div class="custom-control custom-radio custom-control-inline">
    ……
</div>
……
```
![此处输入图片的描述][82]
<br/>
#### • 表单网格：`.form-row` > `.col-*`/`.form-group|check` > `.form-control`
```html
<form>
    <!-- 在form下创建.form-row网格系统 -->
    <div class="form-row">
        <div class="col">
            <input type="text" class="form-control" placeholder="First name">
        </div>
        <div class="col">
            <input type="text" class="form-control" placeholder="Last name">
        </div>
    </div>
    
    <div class="form-row">
        <!-- 在.col-*后添加.form-group|check创建表单分组 -->
        <div class="col-8 form-group">
            <label for="inputEmail">Email:</label>
            <input type="email" class="form-control" id="inputEmail" placeholder="Email">
        </div>
        <div class="col-4 form-group">
            <label for="inputPassword">Password:</label>
            <input type="password" class="form-control" id="inputPassword" placeholder="Password">
        </div>
    </div>
</form>
```
![此处输入图片的描述][83]

##### - 标签对齐：`.col-form-label`
使用网格创建水平表单时，使标签与相关的表单控件垂直居中
```html
<div class="form-group row">
    <!-- 在label的.col-*后添加.col-form-label -->
    <label class="col-2 col-form-label" for="text1">lable: </label>
    <div class="col-10">
        <input type="text" id="text1" class="form-control">
    </div>
</div>
    
<fieldset class="form-group">
    <div class="row">
        <!-- 在legend的.col-*后添加.col-form-label -->
        <legend class="col-3 col-form-label">legend: </legend>
        <div class="col-9">
            <label class="col-form-label" for="text2">lable: </label>
            <input type="text" id="text2" class="form-control">
        </div>
    </div>
</fieldset>
```
![此处输入图片的描述][84]

##### - 标签尺寸：`.col-form-label-sm|lg`
```html
<div class="form-group row">
    <!-- 在.col-form-label后添加.col-form-label-sm|lg以配合控件尺寸 -->
    <label class="col-2 col-form-label col-form-label-sm" for="text1">label</label>
    <div class="col-10">
        <input type="text" id="text1" class="form-control form-control-sm">
    </div>
 </div>
```
![此处输入图片的描述][85]
<br/>
### C4、表单项
#### • 内联表单：`.form-inline`
```html
<!-- 向form添加.form-inline，使表单内所有元素排成一行 -->
<form class="form-inline">
    ……
</form>
```
![此处输入图片的描述][86]
<br/>
#### • 表单验证：`.was-validated` > `required`+`.invalid-feedback`
```html
<!-- 向form添加.was-validated，默认表单已验证（未通过） -->
<form class="was-validated">
    <div class="form-group">
        <label for="text1">输入框：</label>
        <!-- 向表单控件添加required属性，关联为必填项 -->
        <input type="text" id="text1" class="form-control" required>
        <!-- 控件后插入.invalid-feedback，设置验证未通过时的提示文本 -->
        <div class="invalid-feedback">必填项，请输入内容！</div>
    </div>
    
    <div class="form-check">
        <input type="radio" name="group" id="radio1" class="form-check-input" required>
        <label class="form-check-label" for="radio1">单选框1</label>
    </div>
    <div class="form-check">
        <input type="radio" name="group" id="radio2" class="form-check-input" required>
        <label class="form-check-label" for="radio2">单选框2</label>
        <!-- 单选框组的提示文本写在最后一项结尾 -->
        <div class="invalid-feedback">必填项，请选择一项！</div>
    </div>
    
    <div class="form-group">
        <select class="form-control" required>
            <!-- 需预设一个非选项，向第一个option添加value="" -->
            <option value="">预显示文本（非选项）</option>
            <option value="1">选项1</option>
            <option value="2">选项2</option>
        </select>
        <div class="invalid-feedback">必填项，请选择一项！</div>
    </div>
</form>
```
![此处输入图片的描述][87]

##### - 服务器验证：`.is-valid|invalid`+`.valid|invalid-feedback`
```html
<label for="text1">请输入：</label>
<!-- 在.form-control后添加.is-valid，预设验证通过 -->
<input type="text" id="text1" class="form-control is-valid" required>
<!-- .valid-feedback设置验证通过时的提示文本 -->
<div class="valid-feedback">验证通过！</div>

<label for="text2">请输入：</label>
<!-- 在.form-control后添加.is-invalid，预设验证未通过 -->
<input type="text" id="text2" class="form-control is-invalid" required>
<!-- .invalid-feedback设置验证未通过时的提示文本 -->
<div class="invalid-feedback">验证未通过！</div>
```
![此处输入图片的描述][88]

<br/>
### 5、输入框组：`.input-group` > `.input-group-prepend|append` > `.input-group-text`
```html
<!-- 以一个带.input-group的div开始，作为一组 -->
<div class="input-group">
    <!-- 创建.input-group-prepend，显示为前缀区域 -->
    <div class="input-group-prepend">
        <!-- 在带.input-group-text的span里设置文本内容 -->
        <span class="input-group-text">文本前缀</span>
    </div>
    <input type="text" class="form-control">
</div>

<div class="input-group">
    <input type="text" class="form-control">
    <!-- 创建.input-group-append，显示为后缀区域 -->
    <div class="input-group-append">
        <div class="input-group-text">
            <!-- 在.input-group-text里嵌入其他元素 -->
            <input type="checkbox">选框后缀
        </div>
    </div>
</div>

<!-- .input-group下可内联多个控件，前后缀中可内联多项内容 -->
```
![此处输入图片的描述][89]
![此处输入图片的描述][90]
<br/>
#### • 输入组的尺寸：`.input-group-lg|sm`
```html
<!-- 在.input-group后添加.input-group-lg|sm -->
<div class="input-group input-group-lg">
    ……
</div>
```
![此处输入图片的描述][91]

<br/>
### 6、超大屏幕：`.jumbotron`
创建一个大的灰色背景框，里面可以设置HTML标签等一些特殊的内容和信息
```html
<div class="jumbotron">
    ……
</div>
```
![此处输入图片的描述][92]
<br/>
#### • 全屏幕：`.jumbotron-fluid` > `.container`/`.container-fluid`
创建一个没有圆角的全屏幕
```html
<!-- 在.jumbotron后添加.jumbotron-fluid -->
<div class="jumbotron jumbotron-fluid">
    <!-- 将内容包裹在一个带容器类的div里 -->
    <div class="container">
        ……
    </div>
</div>
```
![此处输入图片的描述][93]

<br/>
### 7、模态框：`data-toggle="modal"` `data-target="#……"` + ( `.modal` `id="……"` `tabindex="-1"` > `.modal-dialog` > `.modal-content` > `.modal-header`+`.modal-body`+`.modal-footer` )
>★ 可使用网格系统布局

```html
<!-- 触发按钮，关键插件：data-toggle="modal" data-target="#……" -->
<button data-toggle="modal" data-target="#modal1">点击显示对话框</button>
<!-- .modal创建模态框组件，标记id，并添加tabindex="-1" -->
<div class="modal" id="modal1" tabindex="-1">
    <!-- .modal-dialog创建对话框 -->
    <div class="modal-dialog">
        <!-- .modal-content设置对话框内容 -->
        <div class="modal-content">
            <!-- .modal-header为页眉部分 -->
            <div class="modal-header">这是页眉</div>
            <!-- .modal-body为主体部分（必需项） -->
            <div class="modal-body">这是主体内容</div>
            <!-- .modal-footer为页脚部分，内容自动右对齐 -->
            <div class="modal-footer">这是页脚</div>
        </div>
    </div>
</div>

<!-- 默认点击页面其他位置可关闭对话框，向触发器添加data-backdrop="static"可禁止这一动作 -->
```
![此处输入图片的描述][94]
<br/>
#### • 对话框可滚动：`.modal-dialog-scrollable`
```html
<div class="modal" id="modal2" tabindex="-1">
    <!-- 在.modal-dialog后添加.modal-dialog-scrollable -->
    <div class="modal-dialog modal-dialog-scrollable">
        <div class="modal-content">
            <div class="modal-body">
                ……
            </div>
        </div>
    </div>
</div>
```
![此处输入图片的描述][95]
<br/>
#### • 对话框居中显示：`.modal-dialog-centered`
```html
<div class="modal" id="modal3" tabindex="-1">
    <!-- 在.modal-dialog后添加.modal-dialog-centered -->
    <div class="modal-dialog modal-dialog-centered">
        ……
    </div>
</div>
```
![此处输入图片的描述][96]
<br/>
#### • 对话框尺寸：`.modal-sm|lg|xl`
<table>
<tr>
<th></th>
<th style="text-align:center">Small</th>
<th style="text-align:center">Default</th>
<th style="text-align:center">Large</th>
<th style="text-align:center">Extra large</th>
</tr>
<tr>
<th style="text-align:center">Class</th>
<td style="text-align:center;"><code>.modal-sm</code></td>
<td style="text-align:center;"></td>
<td style="text-align:center;"><code>.modal-lg</code></td>
<td style="text-align:center;"><code>.modal-xl</code></td>
</tr>
<tr>
<th style="text-align:center">Max-width</th>
<td style="text-align:center">300px</td>
<td style="text-align:center">500px</td>
<td style="text-align:center">800px</td>
<td style="text-align:center">1140px</td>
</tr>
</table>

```html
<div class="modal" id="modal3" tabindex="-1">
    <!-- 在.modal-dialog后添加.modal-sm|lg|xl -->
    <div class="modal-dialog modal-sm">
        ……
    </div>
</div>
```
![此处输入图片的描述][97]
<br/>
#### • 页眉与页脚
##### - 对话框标题：`.modal-title`
```html
<div class="modal-header">
    <!-- 在.modal-header下创建.modal-title文本 -->
    <h5 class="modal-title">这是标题</h5>
</div>
```
![此处输入图片的描述][98]

##### - 关闭对话框：`data-dismiss="modal"`
```html
<div class="modal-content">
    <div class="modal-header">
        <!-- 在.modal-header下创建关闭按钮，可使用.close小工具 -->
        <button type="button" class="close" data-dismiss="modal">
            <span>&times;</span>
        </button>
    </div>
    
    <div class="modal-body">
        ……
    </div>
    
    <div class="modal-footer">
        <!-- 在.modal-footer下创建关闭按钮 -->
        <button type="button" class="btn btn-secondary" data-dismiss="modal">关闭</button>
    </div>
</div>

<!-- 默认点击页面其他位置可关闭对话框，向触发器添加data-backdrop="static"可禁止这一动作 -->
```
![此处输入图片的描述][99]

<br/>
### 8、导航列表
#### • 基础导航：`.nav` > `.nav-link`
```html
<!-- 以一个带.nav的nav标签开始 -->
<nav class="nav">
    <!-- 直接在nav下创建导航链接.nav-link -->
	<a href="#" class="nav-link">导航链接1</a>
	<a href="#" class="nav-link">导航链接2</a>
	……
</nav>
```
![此处输入图片的描述][100]
<br/>
#### • 项目导航：`.nav` > `.nav-item` > `.nav-link`
```html
<!-- 以一个带.nav的ul/ol标签开始 -->
<ul class="nav">
    <!-- 向li添加.nav-item，创建导航列表项 -->
	<li class="nav-item">
	    <!-- 在li下创建导航链接.nav-link -->
	    <a href="#" class="nav-link">导航链接1</a>
	</li>
	<li class="nav-item">
	    <a href="#" class="nav-link">导航链接2</a>
	</li>
	……
</ul>

<!-- 若导航项的顺序很重要，建议使用ul/ol标签 -->
```
![此处输入图片的描述][101]

##### - 导航样式：`.nav-tabs|pills`
```html
<!-- 在.nav后添加.nav-tabs|pills，可创建标签式/胶囊式导航 -->
<ul class="nav nav-tabs">
	<li class="nav-item">
	    <!-- 当前项用.active标记 -->
	    <a href="#" class="nav-link active">导航链接1</a>
	</li>
	<li class="nav-item">
	    <a href="#" class="nav-link">导航链接2</a>
	</li>
	……
</ul>
```
![此处输入图片的描述][102]
![此处输入图片的描述][103]

##### - 排列方式：`.nav-fill|justified`
```html
<!-- 在.nav后添加.nav-fill，使导航项填充排列，每项宽度自适应内容 -->
<ul class="nav nav-pills nav-fill">
	<li class="nav-item"><a href="#" class="nav-link active">导航链接1</a></li>
	<li class="nav-item"><a href="#" class="nav-link">导航链接2</a></li>
	……
</ul>

<!-- 在.nav后添加.nav-justified，使导航项等宽排列，每项宽度均等 -->
<ul class="nav nav-pills nav-justified">
	<li class="nav-item"><a href="#" class="nav-link active">导航链接1</a></li>
	<li class="nav-item"><a href="#" class="nav-link">导航链接2</a></li>
	……
</ul>

<!-- 必须要有.nav-item才能使排列生效 -->
```
![此处输入图片的描述][104]
![此处输入图片的描述][105]

##### - 带下拉菜单的导航：`.nav-item` `.dropdown` > `.nav-link` `.dropdown-toggle`
```html
<ul class="nav">
	<li class="nav-item"><a href="#" class="nav-link active">Active</a></li>
	<!-- 在.nav-item后添加.dropdown，创建下拉菜单组件 -->
	<li class="nav-item dropdown">
	    <!-- 在.nav-link后添加.dropdown-toggle、data-toggle="dropdown" -->
	    <a href="#" class="nav-link dropdown-toggle" data-toggle="dropdown">Dropdown</a>
	    <!-- 创建下拉菜单 -->
	    <div class="dropdown-menu">
	        ……
	    </div>
	</li>
	<li class="nav-item"><a href="#" class="nav-link">Link</a></li>
	……
</ul>
```
![此处输入图片的描述][106]
<br/>
#### • 选项卡切换
>★ 可使用网格系统布局

##### - 标签式选项卡切换：( `.nav` `.nav-tabs` > `.nav-item` > `.nav-link` `data-toggle="tab"` `href="#……"` ) + ( `.tab-content` > `.tab-pane` `id="……"` )
```html
<ul class="nav nav-tabs">
    <!-- nav-tabs下，向a添加data-toggle="tab"，绑定对应页面id -->
	<li class="nav-item"><a href="#tab1" class="nav-link active" data-toggle="tab">Tab 1</a></li>
	<li class="nav-item"><a href="#tab2" class="nav-link" data-toggle="tab">Tab 2</a></li>
	……
</ul>

<!-- 所有页面需包裹在.tab-content里 -->
<div class="tab-content">
    <!-- .tab-pane创建页面，标记唯一id，.active标记当前页面 -->
	<div class="tab-pane active" id="tab1">这是Tab 1的页面内容</div>
	<div class="tab-pane" id="tab2">这是Tab 2的页面内容</div>
	……
</div>
```
```html
<!-- nav标签的标签式选项卡切换样式 -->
<nav>
    <div class="nav nav-tabs">
        <a href="#tab1" class="nav-item nav-link active"data-toggle="tab">Tab 1</a>
        <a href="#tab2" class="nav-item nav-link" data-toggle="tab">Tab 2</a>
        ……
    </div>
</nav>
<div class="tab-content">
	<div class="tab-pane active" id="tab1">这是Tab 1的页面内容</div>
	<div class="tab-pane" id="tab2">这是Tab 2的页面内容</div>
	……
</div>
```
![此处输入图片的描述][107]

##### - 胶囊式选项卡切换：( `.nav` `.nav-pills` > `.nav-item` > `.nav-link` `data-toggle="pill"` `href="#……"` ) + ( `.tab-content` > `.tab-pane` `id="……"` )
```html
<ul class="nav nav-pills">
    <!-- nav-pills下，向a添加data-toggle="pill"，绑定对应页面id -->
	<li class="nav-item"><a href="#tab1" class="nav-link active" data-toggle="pill">Tab 1</a></li>
	<li class="nav-item"><a href="#tab2" class="nav-link" data-toggle="pill">Tab 2</a></li>
	……
</ul>

<div class="tab-content">
	<div class="tab-pane active" id="tab1">这是Tab 1的页面内容</div>
	<div class="tab-pane" id="tab2">这是Tab 2的页面内容</div>
	……
</div>
```
```html
<!-- nav标签的胶囊式选项卡切换样式 -->
<nav>
    <div class="nav nav-pills">
        <a href="#tab1" class="nav-item nav-link active" data-toggle="pill">Tab 1</a>
        <a href="#tab2" class="nav-item nav-link" data-toggle="pill">Tab 2</a>
        ……
    </div>
</nav>
<div class="tab-content">
	<div class="tab-pane active" id="tab1">这是Tab 1的页面内容</div>
	<div class="tab-pane" id="tab2">这是Tab 2的页面内容</div>
	……
</div>
```
![此处输入图片的描述][108]

<br/>
### 9、导航栏
#### • 响应式导航栏：`.navbar` `navbar-expand-*` > ( `.navbar-toggler` `data-toggle="collapse"` `data-target="#……"` > `.navbar-toggler-icon` )+( `.collapse` `.navbar-collapse` `id="……"` > `.navbar-nav` > `.nav-item` > `.nav-link` )
```html
<!-- 以一个带.navbar和.navbar-expand-*的nav标签开始 -->
<nav class="navbar navbar-expand-lg">
	<!-- 创建一个带.navbar-toggler、data-toggle="collapse"、data-target="#……"的响应式折叠按钮，仅折叠时可见 -->
	<button type="button" class="navbar-toggler" data-toggle="collapse" data-target="#collapseDiv">
		<!-- 用带.navbar-toggler-icon的span内置按钮样式图标 -->
		<span class="navbar-toggler-icon"></span>
	</button>
	<!-- 创建导航菜单 -->
	<div class="collapse navbar-collapse" id="collapseDiv">
		<!-- 创建导航列表 -->
		<ul class="navbar-nav">
			<li class="nav-item active"><a href="#" class="nav-link">导航链接1</a></li>
			<li class="nav-item"><a href="#" class="nav-link">导航链接2</a></li>
			……
		</ul>
		<!-- 导航栏上的其他元素 -->
		<form class="form-inline">
			<input type="search" class="form-control">
			<button type="submit" class="btn btn-primary">搜索</button>
		</form>
		……
	</div>
</nav>
```
```html
<div class="collapse navbar-collapse" id="collapseDiv">
	<!-- 也可不使用列表标签创建导航菜单 -->
	<div class="navbar-nav">
		<a href="#" class="nav-item nav-link active">导航链接1</a>
		<a href="#" class="nav-item nav-link">导航链接2</a>
		……
	</div>
	……
</div>
```
![此处输入图片的描述][109]

##### - 品牌标志：`.navbar-brand`
```html
<nav class="navbar navbar-expand-lg">
    <!-- 在nav下添加带.navbar-brand的a标签，生成品牌链接 -->
	<a href="#" class="navbar-brand">Brand</a>
</nav>

<nav class="navbar navbar-expand-lg">
    <!-- 使用span生成品牌文本 -->
	<span class="navbar-brand">Brand</span>
</nav>
```
```html
<nav class="navbar navbar-expand-lg">
	<a href="#" class="navbar-brand">
	    <!-- 在.navbar-brand中插入图片作为品牌logo，需调整尺寸 -->
	    <img src="/image.jpg" height="30">
	</a>
</nav>

<nav class="navbar navbar-expand-lg">
	<a href="#" class="navbar-brand">
	    <!-- 添加.align-top使图片与文字对齐 -->
	    <img src="/image.jpg" height="30" class="align-top"> Brand
	</a>
</nav>
```
![此处输入图片的描述][110]

```html
<nav class="navbar bg-light navbar-light">
    <!-- nav下的所有元素呈两端对齐方式显示 -->
    <a class="navbar-brand" href="#">Brand</a>
    <form class="form-inline">……</form>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navDiv">……</button>
    <!-- 仅折叠杆中的内容在小屏时总是被折叠 -->
    <div class="collapse navbar-collapse" id="navDiv">
        ……
    </div>
</nav>

<!-- 此外，折叠杆中的id属性也可匹配网页其他内容 -->
```

##### - 输入表单：`.form-inline` > `.form-control`
```html
<nav class="navbar bg-light navbar-light">
    <!-- 在nav下添加带.form-inline的form标签，创建表单组件 -->
	<form class="form-inline">
	    <input class="form-control" type="search" placeholder="Search">
	    <button class="btn btn-info" type="submit">Search</button>
	</form>
</nav>
```
`.form-inline` > `.input-group` > `.form-control`
```html
<nav class="navbar bg-light navbar-light">
	<form class="form-inline">
	    <!-- 在form下添加带.input-group的div，创建输入组 -->
	    <div class="input-group">
	        <input class="form-control" type="text" placeholder="sometext">
	        <div class="input-group-append">
	            <button class="btn btn-info" type="button">GO!</button>
	        </div>
	    </div>
	</form>
</nav>
```
![此处输入图片的描述][111]

##### - 文本：`.navbar-text`
导航栏上的非链接文本，保证水平对齐，颜色与内边距一样
```html
<nav class="navbar navbar-light bg-light">
    <!-- 在nav下添加带.navbar-text的span -->
    <span class="navbar-text">sometext</span>
</nav>
```
![此处输入图片的描述][112]
<br/>
#### • 带下拉菜单：`.nav-item` `.dropdown|dropdown` > `.nav-link` `.dropdown-toggle` > `data-toggle="dropdown"` + （`.dropdown-menu` > `.dropdown-item`）
```html
<nav class="navbar navbar-expand-lg bg-light navbar-light">
    <a class="navbar-brand" href="#">Brand</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navDiv"><span class="navbar-toggler-icon"></span></button>
    <div class="collapse navbar-collapse" id="navDiv">
        <ul class="navbar-nav">
	        <li class="nav-item"><a class="nav-link" href="#">Link</a></li>
	        <!-- 向li添加.dropdown/.dropup，创建下拉/弹出菜单 -->
	        <li class="nav-item dropdown">
	            <a class="nav-link dropdown-toggle" href="#" data-toggle="dropdown">Dropdown</a>
	            <div class="dropdown-menu">
	                <a class="dropdown-item" href="#">link 1</a>
	                <a class="dropdown-item" href="#">link 2</a>
	            </div>
            </li>
        </ul>
    </div>
</nav>
```
![此处输入图片的描述][113]
<br/>
#### • 颜色搭配：`.bg-背景颜色` `.navbar-light|dark`

    .navbar-light  深色文本        .navbar-dark  浅色文本
```html
<!-- 向nav添加背景颜色类和导航栏文本颜色类 -->
<nav class="navbar bg-light navbar-light">
    ……
</nav>

<!-- 浅色面板搭配.navbar-light，深色面板搭配.navbar-dark -->
```
![此处输入图片的描述][114]
<br/>
#### • 定位方式：`.fixed-top`/`.fixed-bottom`/`.sticky-top`
```html
<head>
    <style type="text/css">
        /* 向body添加样式padding-top ≥ 50px */
		body {padding-top: 70px;}
	</style>
</head>

<body>
    <!-- 向nav添加.fixed-top，使导航栏固定在窗口顶部 -->
    <nav class="navbar bg-light navbar-light fixed-top">
        <a class="navbar-brand" href="#">Brand</a>
    </nav>
    <div>需为body设置padding-top，页面内容才不会被导航栏遮挡。</div>
</body>
```
![此处输入图片的描述][115]

```html
<head>
    <style type="text/css">
        /* 向body添加样式padding-bottom ≥ 50px */
		body {padding-bottom: 70px;}
	</style>
</head>

<body>
    <!-- 向nav添加.fixed-bottom，使导航栏固定在窗口底部 -->
    <nav class="navbar bg-light navbar-light fixed-bottom">
        <a class="navbar-brand" href="#">Brand</a>
    </nav>
    <div>为body设置padding-bottom，页面内容不会被导航栏遮挡。</div>
</body>
```
![此处输入图片的描述][116]

```html
<!-- 向nav添加.sticky-top，使导航栏磁铁在窗口顶部 -->
<nav class="navbar bg-light navbar-light sticky-top">
    <a class="navbar-brand" href="#">Brand</a>
</nav>
```

<br/>
### 10、弹出框
>**※** 要使弹出框生效，需在 jQuery 里初始化所有弹出框
#### • 基础弹出框：`data-toggle="popover"` `data-content="……"`
鼠标点击到元素后，在旁边显示弹出框，需再次点击该元素才能关闭
```html
<!-- 向a元素添加data-toggle="popover"和data-content="……" -->
<a data-toggle="popover" data-content="这是弹出框中的文本内容！">点击显示弹出框</a>
```
```javascript
$(document).ready(function(){
    //初始化弹出框，在指定元素上调用popover()方法
    $('[data-toggle="popover"]').popover();
})
```
![此处输入图片的描述][117]
##### - focus弹出框：`data-trigger="focus"` `tabindex="0"`
点击元素显示弹出框后，再点击该元素之外的其他任意位置都可以关闭弹出框
```html
<!-- 向基础弹出框再添加data-trigger="focus"和tabindex属性 -->
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-trigger="focus" tabindex="0">点击显示弹出框</a>
```
![此处输入图片的描述][118]
##### - hover弹出框：`data-trigger="hover"`
显示弹出框后，再点击除了该元素之外的其他任意位置都可以关闭弹出框
```html
<!-- 向基础弹出框再添加data-trigger="hover" -->
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-trigger="hover">点击显示弹出框</a>
```
![此处输入图片的描述][119]
<br/>
#### • 弹出框中的标题：`title="……"`
```html
<a data-toggle="popover" title="这是标题" data-content="这是弹出框中的文本内容！">点击显示弹出框</a>
```
![此处输入图片的描述][120]
<br/>
#### • 指定弹出方向：`data-placement="top|right|bottom|left"`
```html
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-placement="top">向上弹出框</a>
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-placement="right">向右弹出框</a>
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-placement="bottom">向下弹出框</a>
<a data-toggle="popover" data-content="这是弹出框中的文本内容！" data-placement="left">向左弹出框</a>

<!-- 仅当元素与页面边框间距足够时，该方向才能弹出，否则反方向弹出 -->
```
![此处输入图片的描述][121]

---

## Bootstrap4 通用
### 1、边框
#### • 添加边框：`.border`/`.border-top|right|bottom|left`
```html
<div class="border"></div>
<div class="border-top"></div>
```
![此处输入图片的描述][122]

#### • 清除边框：`.border-0`/`.border-top|right|bottom|left-0`
```html
<div class="border-0"></div>
<div class="border-top-0"></div>
```
![此处输入图片的描述][123]

#### • 边框颜色：`.border-primary|secondary|success|danger|warning|info|light|dark|white`
```html
<div class="border border-primary"></div>
```
![此处输入图片的描述][124]
![此处输入图片的描述][125]

#### • 边框圆角：`.rounded`/`.rounded-top|right|bottom|left|circle|pill|0`
```html
<div class="rounded"></div>
<div class="rounded-top"></div>
```
![此处输入图片的描述][126]

#### • 圆角尺寸：`.rounded-sm|lg`
```html
<div class="rounded-sm"></div>
```
![此处输入图片的描述][127]
<br>
### 2、颜色
#### • 文本颜色：`.text-primary|secondary|success|danger|warning|info|light|dark|body|muted|white|black-50|white-50`
```html
<p class="text-primary">.text-primary</p>
```
![此处输入图片的描述][128]

#### • 背景颜色：`.bg-primary|secondary|success|danger|warning|info|light|dark|white|transparent`
```html
<p class="bg-primary">.bg-primary</p>
```
![此处输入图片的描述][129]
<br>
### 3、显示
#### • 元素框的类型：`.d-①`/`.d-②-①`
>`.d` display
① `none` 不显示 &nbsp;&nbsp;&nbsp;`inline` 内联元素 &nbsp;&nbsp;&nbsp;`inline-block` 行内块元素 &nbsp;&nbsp;&nbsp;`block` 块元素 &nbsp;&nbsp;&nbsp;`table` 块级表格元素 &nbsp;&nbsp;&nbsp;`table-cell` 表格单元格元素 &nbsp;&nbsp;&nbsp;`table-row` 表格行元素 &nbsp;&nbsp;&nbsp;`flex` 弹性布局块元素 &nbsp;&nbsp;&nbsp;`inline-flex` 弹性布局内联元素
② `sm` ≥576px &nbsp;&nbsp;&nbsp;`md` ≥768px &nbsp;&nbsp;&nbsp;`lg` ≥992px &nbsp;&nbsp;&nbsp;`xl` ≥1200px

<table>
  <thead>
    <tr style="background: #555555; color: #fff;">
      <th>Screen Size</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Hidden on all</td>
      <td><code>.d-none</code></td>
    </tr>
    <tr>
      <td>Hidden only on xs</td>
      <td><code>.d-none</code> <code>.d-sm-block</code></td>
    </tr>
    <tr>
      <td>Hidden only on sm</td>
      <td><code>.d-sm-none</code> <code>.d-md-block</code></td>
    </tr>
    <tr>
      <td>Hidden only on md</td>
      <td><code>.d-md-none</code> <code>.d-lg-block</code></td>
    </tr>
    <tr>
      <td>Hidden only on lg</td>
      <td><code>.d-lg-none</code> <code>.d-xl-block</code></td>
    </tr>
    <tr>
      <td>Hidden only on xl</td>
      <td><code>.d-xl-none</code></td>
    </tr>
    <tr>
      <td>Visible on all</td>
      <td><code>.d-block</code></td>
    </tr>
    <tr>
      <td>Visible only on xs</td>
      <td><code>.d-block</code> <code>.d-sm-none</code></td>
    </tr>
    <tr>
      <td>Visible only on sm</td>
      <td><code>.d-none</code> <code>.d-sm-block</code> <code>.d-md-none</code></td>
    </tr>
    <tr>
      <td>Visible only on md</td>
      <td><code>.d-none</code> <code>.d-md-block</code> <code>.d-lg-none</code></td>
    </tr>
    <tr>
      <td>Visible only on lg</td>
      <td><code>.d-none</code> <code>.d-lg-block</code> <code>.d-xl-none</code></td>
    </tr>
    <tr>
      <td>Visible only on xl</td>
      <td><code>.d-none</code> <code>.d-xl-block</code></td>
    </tr>
  </tbody>
</table>

#### • 打印显示：`.d-print-①`
>① `none` 不显示 &nbsp;&nbsp;&nbsp;`inline` 内联元素 &nbsp;&nbsp;&nbsp;`inline-block` 行内块元素 &nbsp;&nbsp;&nbsp;`block` 块元素 &nbsp;&nbsp;&nbsp;`table` 块级表格元素 &nbsp;&nbsp;&nbsp;`table-cell` 表格单元格元素 &nbsp;&nbsp;&nbsp;`table-row` 表格行元素 &nbsp;&nbsp;&nbsp;`flex` 弹性布局块元素 &nbsp;&nbsp;&nbsp;`inline-flex` 弹性布局内联元素

<br>
### 4、浮动：`.float-①`/`.float-②-①`
>① `left` 向左浮动 &nbsp;&nbsp;&nbsp;`right` 向右浮动 &nbsp;&nbsp;&nbsp;`none` 不浮动
② `sm` ≥576px &nbsp;&nbsp;&nbsp;`md` ≥768px &nbsp;&nbsp;&nbsp;`lg` ≥992px &nbsp;&nbsp;&nbsp;`xl` ≥1200px

<br>
### 5、尺寸：`.①②-③`/`.min-①②-③`
>① `m` max &nbsp;&nbsp;&nbsp;`v` viewport
② `w` width &nbsp;&nbsp;&nbsp;`h` height &nbsp;&nbsp;&nbsp;
③ `25` 25% &nbsp;&nbsp;&nbsp;`50` 50% &nbsp;&nbsp;&nbsp;`75` 75% &nbsp;&nbsp;&nbsp;`100` 100% &nbsp;&nbsp;&nbsp;`auto` 适应内容

<br>
### 6、间距：`.①②-③-④`
>① `m` margin &nbsp;&nbsp;&nbsp;`p` padding
② `t` top &nbsp;&nbsp;&nbsp;`r` right &nbsp;&nbsp;&nbsp;`b` bottom &nbsp;&nbsp;&nbsp;`l` left &nbsp;&nbsp;&nbsp;`x` X轴方向 &nbsp;&nbsp;&nbsp;`y` Y轴方向
③ `sm` ≥576px &nbsp;&nbsp;&nbsp;`md` ≥768px &nbsp;&nbsp;&nbsp;`lg` ≥992px &nbsp;&nbsp;&nbsp;`xl` ≥1200px
④ `auto` 适应内容 &nbsp;&nbsp;&nbsp;`0` 清除间距 &nbsp;&nbsp;&nbsp;`1` 0.25rem &nbsp;&nbsp;&nbsp;`2` 0.5rem &nbsp;&nbsp;&nbsp;`3` 1rem &nbsp;&nbsp;&nbsp;`4` 1.5rem &nbsp;&nbsp;&nbsp;`5` 3rem

<br>
### 7、文本
#### • 文本水平对齐方式：`.text-justify|left|center|right`
```html
<p class="text-justify">左起两端对齐</p>
<p class="text-left">左对齐</p>
<p class="text-center">居中对齐</p>
<p class="text-right">右对齐</p>
```
![此处输入图片的描述][130]

#### • 文本换行/溢出/省略：`.text-wrap|nowrap|truncate`/`.text-break`
```html
<p class="bg-secondary w-25">默认的中文文本不会溢出，换行显示；英文文本会溢出，一行显示</p>
<p class="bg-primary w-25 text-wrap">.text-wrap的中文文本不会溢出，换行显示；英文文本会溢出，一行显示</p>
<p class="bg-success w-25 text-nowrap">.text-nowrap的文本会溢出，一行显示</p>
<p class="bg-warning w-25 text-truncate">.text-truncate的文本不会溢出，不换行，溢出部分省略为...</p>
<p class="bg-danger w-25 text-break">.text-break的文本不会溢出，换行显示</p>
```
![此处输入图片的描述][131]

#### • 字母大小写转换：`.text-uppercase|lowercase|capitalize`
```html
<p class="text-lowercase">全小写 text-lowercase</p>
<p class="text-uppercase">全大写 text-uppercase</p>      
<p class="text-capitalize">首字母大写 text-capitalize</p>
```
![此处输入图片的描述][132]

#### • 文本粗细与斜体：`.font-weight-bolder|bold|normal|light|lighter` `.font-italic`
```html
<p class="font-weight-normal">普通文本 .font-weight-normal</p>
<p class="font-weight-bold">粗体文本 .font-weight-bold</p>
<p class="font-weight-bolder">更粗文本 .font-weight-bolder</p>
<p class="font-weight-light">细体文本 .font-weight-light</p>
<p class="font-weight-lighter">更细文本 .font-weight-lighter</p>
<p class="font-italic">斜体文本 .font-italic</p>

<!-- .font-weight-*和.font-italic可搭配使用 -->
```
![此处输入图片的描述][133]

#### • 等宽英文字体：`.text-monospace`
```html
<p class="text-monospace">This is in monospace</p>
```
![此处输入图片的描述][134]

#### • 文本从父继承颜色：`.text-reset`
```html
<p class="text-muted">
    <a href="#">链接1：默认颜色</a>
    <a href="#" class="text-reset">链接2：.text-reset从父继承颜色</a>
</p>
```
![此处输入图片的描述][135]

#### • 清除链接下划线：`.text-decoration-none`
```html
<a href="#" class="text-decoration-none">没有下划线的链接文本</a>
```
![此处输入图片的描述][136]
<br>
### 8、可见：`.visible`/`.invisible`
>`visible` 可见占位 { visibility: visible !important; }
`invisible` 不可见占位 { visibility: hidden !important; }

<br>

---


  [1]: http://wx2.sinaimg.cn/large/7de6638dly1fwmdzl9xsfj20n605vaa5.jpg
  [2]: http://wx1.sinaimg.cn/large/7de6638dly1fwmdzrprjgj20n505x74h.jpg
  [3]: http://wx4.sinaimg.cn/large/7de6638dly1fwme70jl6fj20yx07wglh.jpg
  [4]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwq6rce7b0j20np03st8z.jpg
  [5]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwq7dzvpa5j20nr02mt8u.jpg
  [6]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwqc1dage6j20ng041q2v.jpg
  [7]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwq8volf0aj20nl06xgmb.jpg
  [8]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwq9c1tdwgj20nq03hjrl.jpg
  [9]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwq7mqj1zfj20nq02xa9t.jpg
  [10]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwqb2gwwrij21bm049406.jpg
  [11]: http://wx3.sinaimg.cn/large/7de6638dly1fwnz471zmvg20o703w3yp.gif
  [12]: http://wx2.sinaimg.cn/large/7de6638dly1fwomlix20hj20o0029glk.jpg
  [13]: http://wx4.sinaimg.cn/large/7de6638dly1g231q57104j20o20cz40g.jpg
  [14]: http://wx3.sinaimg.cn/large/7de6638dly1fwom63xr8wj20o501rmxa.jpg
  [15]: http://wx1.sinaimg.cn/large/7de6638dly1g232ihkljqj20r701dmx7.jpg
  [16]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g25g5edsfij20o60ap0tn.jpg
  [17]: http://wx1.sinaimg.cn/large/7de6638dly1fwonw64f3yg20o306jjsl.gif
  [18]: http://wx1.sinaimg.cn/large/7de6638dly1fwnzp4lp9oj20nw05wjrk.jpg
  [19]: http://wx3.sinaimg.cn/large/7de6638dly1fwolo69dagj20o106xwes.jpg
  [20]: http://wx4.sinaimg.cn/large/7de6638dly1fwntbgdba9j20o00bdwft.jpg
  [21]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g25fs9ni3oj20o801rq2r.jpg
  [22]: http://wx4.sinaimg.cn/large/7de6638dly1fwon06nebcj20o008a3yq.jpg
  [23]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g25fad3xr6j20o203egll.jpg
  [24]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g25ntet333j20o701n0sl.jpg
  [25]: http://wx4.sinaimg.cn/large/7de6638dly1fwolw4qky3j20o3097wek.jpg
  [26]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwohkwibhaj20o4063glz.jpg
  [27]: http://wx4.sinaimg.cn/large/7de6638dly1fwom1fprbtj20o002r3yh.jpg
  [28]: http://wx3.sinaimg.cn/large/7de6638dly1fwomz2az6aj20nz08aaaa.jpg
  [29]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g25fiwtks0j20oa01n0si.jpg
  [30]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwoonho7qqj20o20b275m.jpg
  [31]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwntro22cej20pt0liac1.jpg
  [32]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwo0i01z6cj20o504zjrj.jpg
  [33]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwopnpnwwuj20o003jt8t.jpg
  [34]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwo0whqd56j20nw07at9m.jpg
  [35]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwob64aqhlj20nw030glt.jpg
  [36]: http://wx1.sinaimg.cn/large/7de6638dly1g2322j4tjmj20nx0czdhs.jpg
  [37]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwogq8uzgmj20jc08egm7.jpg
  [38]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwobmc1kqqj20o3014mx0.jpg
  [39]: http://wx4.sinaimg.cn/large/7de6638dly1fwoc22wp77g20nz0euq9h.gif
  [40]: http://wx4.sinaimg.cn/large/7de6638dly1g272nals5wg20t10n21l2.gif
  [41]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27gbftse2j20o70fq7ac.jpg
  [42]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27iaj37jdj20o605oaa3.jpg
  [43]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g27jz16lj9j20np0l0js4.jpg
  [44]: https://wx4.sinaimg.cn/mw1024/7de6638dly1g27iste5xkj20o6097mxd.jpg
  [45]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27ivysqe3j20o6076jrg.jpg
  [46]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g27iyblvv6j20o506yaa4.jpg
  [47]: http://wx1.sinaimg.cn/large/7de6638dly1g27j1v4uysg20o306u74r.gif
  [48]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27janc35gj20o6056t8r.jpg
  [49]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g27in5l9aij20o50dsq3e.jpg
  [50]: http://wx2.sinaimg.cn/large/7de6638dly1g27k6b5uqvg20p106zgok.gif
  [51]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g27r3qqiicj20o20dagof.jpg
  [52]: https://wx3.sinaimg.cn/mw690/7de6638dly1fx0ef79gedj20nu02gmx0.jpg
  [53]: https://wx4.sinaimg.cn/mw690/7de6638dly1g22qqfgzpej20ci07jaae.jpg
  [54]: https://wx1.sinaimg.cn/mw690/7de6638dly1g22u4nenhjj20cj0k7gt7.jpg
  [55]: https://wx2.sinaimg.cn/mw690/7de6638dly1g22udr27c9j20cj08xadr.jpg
  [56]: https://wx4.sinaimg.cn/mw690/7de6638dly1g22rflcnm6j207706u3yg.jpg
  [57]: https://wx3.sinaimg.cn/mw690/7de6638dly1g22rw7e7vjj20cw07pwek.jpg
  [58]: http://wx4.sinaimg.cn/large/7de6638dly1g22tj4zivig20ko05nwfc.gif
  [59]: http://wx1.sinaimg.cn/large/7de6638dly1g22ty7z741g20kj067t9i.gif
  [60]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwry55xg4vj21ap0nawgt.jpg
  [61]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwry7z4ymtj21ar0ndtar.jpg
  [62]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwrzck6dioj21at0i7mze.jpg
  [63]: http://wx3.sinaimg.cn/large/7de6638dly1g27ux2ylpog20o607fq3m.gif
  [64]: https://wx4.sinaimg.cn/mw1024/7de6638dly1g27uq3agitj20q003pt8s.jpg
  [65]: http://wx4.sinaimg.cn/large/7de6638dly1g27v4av1bxg20o60860uw.gif
  [66]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g27wldqcyuj20o7086t8s.jpg
  [67]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g27uuzsonhj20o8078t8s.jpg
  [68]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwmia665e5j20o307bmxa.jpg
  [69]: https://wx4.sinaimg.cn/mw1024/7de6638dly1g27w3a52q5j20o50as0t3.jpg
  [70]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g2b0qouxa4j20qt0j9js1.jpg
  [71]: https://wx3.sinaimg.cn/mw690/7de6638dly1fy467yuyw3j20uy06gq2y.jpg
  [72]: https://wx2.sinaimg.cn/mw690/7de6638dly1fy441ms8jqj20nz03p0sx.jpg
  [73]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g29dvt4mvvj20o7069gln.jpg
  [74]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g29dyo2sjij20o6079mx8.jpg
  [75]: http://wx3.sinaimg.cn/large/7de6638dly1g29gzdsu0kg20o3073mxy.gif
  [76]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g2b2cwa7ksj20o904g3yk.jpg
  [77]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g2azvjp06wj20o5054t8q.jpg
  [78]: https://wx4.sinaimg.cn/mw690/7de6638dly1fy46iibviuj20nt055q30.jpg
  [79]: https://wx3.sinaimg.cn/mw690/7de6638dly1fyg75k5q40j20o401oq2u.jpg
  [80]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g299pnxk6ij20o902fdfl.jpg
  [81]: http://wx2.sinaimg.cn/large/7de6638dly1g29dkea95pg20o5088dh4.gif
  [82]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g29cryo3icj20o7027jrb.jpg
  [83]: https://wx1.sinaimg.cn/mw690/7de6638dly1fyg2yprbk3j20o106egln.jpg
  [84]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g29bjutqevj20o706ia9y.jpg
  [85]: https://wx3.sinaimg.cn/mw690/7de6638dly1fyg5alo8doj20o706y3yp.jpg
  [86]: https://wx2.sinaimg.cn/mw690/7de6638dly1fygasb3751j20ol025t8n.jpg
  [87]: http://wx4.sinaimg.cn/large/7de6638dly1fyge09k72vg20o90bz0ul.gif
  [88]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g2b3frbu6uj20o309nq2z.jpg
  [89]: https://wx4.sinaimg.cn/mw690/7de6638dly1fygmf4e9o7j20o50900te.jpg
  [90]: https://wx2.sinaimg.cn/mw690/7de6638dly1fygl5uh8gqj20o802mwea.jpg
  [91]: https://wx2.sinaimg.cn/mw690/7de6638dly1fygkmm7npcj20o707raag.jpg
  [92]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwnrl5hnnlj20o307g3yv.jpg
  [93]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwnrslau0lj20o109b74q.jpg
  [94]: http://wx1.sinaimg.cn/large/7de6638dly1g2b5qpv8xng20n50b83z6.gif
  [95]: http://wx4.sinaimg.cn/large/7de6638dly1g2b5vj1isvg20ln0mgtib.gif
  [96]: http://wx3.sinaimg.cn/large/7de6638dly1g2b68ykt4sg20o40hk74w.gif
  [97]: http://wx2.sinaimg.cn/large/7de6638dly1g2b7po3smtg21ef03wq63.gif
  [98]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g2b8d1iyc6j20n505rjrd.jpg
  [99]: http://wx2.sinaimg.cn/large/7de6638dly1g2b8xty6dyg20n508njsp.gif
  [100]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwmjcvcm4bj20o302f3ye.jpg
  [101]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwmjcvcm4bj20o302f3ye.jpg
  [102]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwmj1wxaboj20o002ut8m.jpg
  [103]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwkk4gj0tzj20o302f746.jpg
  [104]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g2ba4ojko7j20vs02mglj.jpg
  [105]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g2bacdqw27j20w002lglj.jpg
  [106]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwmkltlee0j20o409k3ym.jpg
  [107]: http://wx1.sinaimg.cn/large/7de6638dly1fwml6uw2vpg20o604wjsi.gif
  [108]: http://wx1.sinaimg.cn/large/7de6638dly1fwmlds4q7ug20o004z75f.gif
  [109]: http://wx1.sinaimg.cn/large/7de6638dly1g2bd2cliq5g21ej0b10un.gif
  [110]: https://wx2.sinaimg.cn/mw1024/7de6638dly1g2bds6aovcj20oc0d6q2x.jpg
  [111]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwmolfcl1xj20om07c3yo.jpg
  [112]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwmrf5cwh7j20ix0313yc.jpg
  [113]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwmqtrr4g7j20o107nt8p.jpg
  [114]: http://wx1.sinaimg.cn/large/7de6638dly1fwmnebn13zg20l008cmz5.gif
  [115]: http://wx1.sinaimg.cn/large/7de6638dly1fwmskfuxaog20nn07zgpy.gif
  [116]: http://wx4.sinaimg.cn/large/7de6638dly1fwmsprbcm7g20nn07zn15.gif
  [117]: http://wx4.sinaimg.cn/large/7de6638dly1fx0ig4sxiug20o4041myi.gif
  [118]: http://wx1.sinaimg.cn/large/7de6638dly1fx0ihanzu6g20o4041wfg.gif
  [119]: http://wx1.sinaimg.cn/large/7de6638dly1fx0johdsecg20o80413yx.gif
  [120]: https://wx3.sinaimg.cn/mw690/7de6638dly1fx0fse5bzlj20o103zwek.jpg
  [121]: https://wx3.sinaimg.cn/mw690/7de6638dly1fx0heb8skoj20zd065gm0.jpg
  [122]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g27nopn87wj20la04k0sh.jpg
  [123]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g27nq7tmuoj20lc04f0sf.jpg
  [124]: https://wx4.sinaimg.cn/mw1024/7de6638dly1g27o4j3pmkj20p202q0os.jpg
  [125]: https://wx4.sinaimg.cn/mw1024/7de6638dly1g27o4j3olxj20oy02p0pc.jpg
  [126]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27ofay2ijj20qq02n0sk.jpg
  [127]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g27oiue6h2j20p4044a9t.jpg
  [128]: http://wx3.sinaimg.cn/large/7de6638dly1g2312pgh0zj20qu0m8wft.jpg
  [129]: http://wx4.sinaimg.cn/large/7de6638dly1g231ah3ukkj20pw0gngmi.jpg
  [130]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwof5hjxvjj20nz0admxw.jpg
  [131]: http://wx4.sinaimg.cn/large/7de6638dly1g22zzaj64fj21du0gfmzh.jpg
  [132]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwrq6t79hhj20o304lq33.jpg
  [133]: http://wx2.sinaimg.cn/large/7de6638dly1g230cjtlytj20qz0a20tf.jpg
  [134]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwofsmzi9ij20nx02rmx7.jpg
  [135]: http://wx3.sinaimg.cn/large/7de6638dly1g230m0e0flj20p501q0su.jpg
  [136]: http://wx1.sinaimg.cn/large/7de6638dly1g230s0hjj8j20pd01hq2v.jpg