# HTML 标签|属性参考手册
Hyper Text Markup Language - 超级文本标记语言

---

## HTML 标签
### • `!--   --`：在源代码中插入注释
```html
<!-- 这是一段注释，不会在浏览器中显示 -->
```
<br/>
### • `a`：定义超链接
```html
<a href="https://www.runoob.com/">绝对路径URL</a>
<a href="tag_a.php">相对路径URL</a>
<a href="#top">锚点URL</a>

<!-- href：规定链接的目标URL -->
```
<a href="https://www.runoob.com/">https://www.runoob.com</a>

    download=""  下载链接的文档名称（*filename）
    hreflang=""  链接文档的语言代码（*language_code）
    media=""  媒体设备类型（*media_query）
    rel=""  当前文档与链接文档之间的关系（alternate|author|bookmark|help|license|next|nofollow|noreferrer|prefetch|prev|search|tag）
    target=""  在何处打开链接文档（_self|_blank|_parent|_top|*framename）
    type=""  链接文档的MIME类型（*MIME_type）
<br/>
### • `abbr`：对缩写词语进行标记
在文本底部添加一条虚线，表示一个缩写词或者首字母缩略词
```html
<p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>
```
![此处输入图片的描述][1]

    title=""  展示缩写词/首字母缩略词的完整版本
<br/>
### • `address`：定义文档作者/所有者的联系信息
address元素的文本通常显示为斜体，大多数浏览器会在该元素前后添加换行符
```html
<address>
Written by <strong>Shaw</strong><br>
Email: <a href="mailto:shaw@example.com">shaw@example.com</a>
</address>
```
![此处输入图片的描述][2]
<br/>
### • `b`：规定粗体文本
```html
<b>这是一段粗体字</b>

<!-- <i>、<b>、<u>元素相邻时，需用<br/>换行 -->
```
<b>这是一段粗体字</b>
<br/>
### • `blockquote`：摘自另一个源的块引用
```html
<h1>About WWF</h1>
<p>Here is a quote from WWF's website:</p>
<blockquote cite="https://www.worldwildlife.org/about">
For nearly 60 years, WWF has been protecting the future of nature.
The world’s leading conservation organization, WWF works in 100 countries and is supported by more than one million members in the United States and close to five million globally. WWF's unique way of working combines global reach with a foundation in science, involves action at every level from local to global, and ensures the delivery of innovative solutions that meet the needs of both people and nature.
</blockquote>

<!-- 浏览器通常会对blockquote元素的内容进行缩进 -->
```
![此处输入图片的描述][3]

    cite=""  使搜索引擎获取引用来源（*URL）
<br/>
### • `br/`：插入一个简单的换行符
```html
<p>这是第一行<br/>这是第二行</p>   <!-- 换行 -->
<p>这是第三行</p>
<br/>                            <!-- 空一行 -->
<p>这是第四行</p>
```
<p>这是第一行<br/>这是第二行</p>
<p>这是第三行</p>
<br/>
<p>这是第四行</p>
<br/>
### • `button`：定义一个按钮
```html
<button type="button">可点击按钮（IE默认值）</button>
<button type="submit">提交按钮（其他浏览器默认值）</button>
<button type="reset">重置按钮（清除表单数据）</button>
```
<button type="button">可点击按钮（IE默认值）</button>
<button type="submit">提交按钮（其他浏览器默认值）</button>
<button type="reset">重置按钮（清除表单数据）</button>

    autofocus  自动获得焦点
    disabled  禁用该按钮
    form=""  规定按钮所属表单（*form_id）
    name=""  规定按钮名称（*button_name）
    value=""  规定按钮的初始值，可修改（*text）
    
    *以下属性需与type="submit"配合使用：
    formnovalidate  提交表单时不进行验证
    formaction=""  覆盖form元素的action属性（*URL）
    formenctype=""  覆盖form元素的enctype属性（application/x-www-form-urlencoded | multipart/form-data | text/plain）
    formmethod=""  覆盖form元素的method属性（get|post）
    formtarget=""  覆盖form元素的target属性（_self|_blank|_parent|_top|*framename）
<br/>
### • `cite`：定义作品（比如书籍、歌曲、电影、电视节目、绘画、雕塑等等）的标题
```html
<p>这幅画的名字叫<cite>The Scream</cite>，作者是Edward Munch。</p>
```
![此处输入图片的描述][4]
<br/>
### • `code`：定义计算机代码文本
```html
<p>HTML元素 <code>span</code>，<code>section</code>，<code>div</code> 用于定义部分文档内容。</p>

<!-- 不同的CSS设置下，code标签将显示不同的效果 -->
```
<p>HTML元素 <code>span</code>，<code>section</code>，<code>div</code> 用于定义部分文档内容。</p>
<br/>
### • `del`：定义文档中已删除的文本
```html
<p>del元素内的文本会被划上<del> 一条删除线 </del>。</p>
```
<p>del元素内的文本会被划上<del> 一条删除线 </del>。</p>
    cite=""  规定一个文档的 URL，该文档解释了文本被删除的原因（*URL）
    datetime=""  规定文本被删除的日期和时间（*YYYY-MM-DDThh:mm:ssTZD）
<br/>
### • `div`：定义文档中的分区或节
```html
<div>
    <h3>这是节的标题</h3>
    <p>这是节的内容</p>
</div>

<!-- 严格的组织工具，不受任何格式关联 -->
```
<br/>
### • `dl`：定义一个描述列表
```html
<dl>
  <dt>项目一名称</dt>
  <dd>这是对项目一的描述</dd>
  <dt>项目二名称</dt>
  <dd>这是对项目二的描述</dd>
  ……
</dl>

<!-- 不同的CSS设置下，dl标签将显示不同的效果 -->
```
<dl>
	<dt>项目一名称</dt>
	<dd>这是对项目一的描述</dd>
	<dt>项目二名称</dt>
	<dd>这是对项目二的描述</dd>
	……
</dl>
#### - `dt`：定义一个描述列表的项目/名字
#### - `dd`：对一个描述列表中的项目/名字进行描述
<br/>
### • `em`：呈现为被强调的文本
```html
<p>em元素内的文本将会 <em>斜体</em> 显示</p>
```
<p>em元素内的文本将会 <em>斜体</em> 显示</p>
<br/>
### • `form`：为用户输入创建HTML表单
```html
<form>
    <input type="text" name="input" placeholder="请输入信息"/>
    <input type="submit" value="提交"/>
</form>

<!-- type：决定输入字段的形式   name：input元素的名称 -->
```
![效果示例][5]

    novalidate  提交表单时不进行验证
    accept-charset=""  服务器可处理的表单数据字符集（*character_set）
    action=""  向何处发送表单数据（*URL）
    autocomplete=""  是否启用自动完成功能（on|off）
    method=""  发送表单数据的HTTP方法（get|post）
    name=""  规定表单名称（*form_name）
    target=""  在何处打开action URL（_blank|_self|_parent|_top）
    
    *以下属性需与method="post"配合使用：
    enctype=""  向服务器发送表单数据之前如何对其进行编码（application/x-www-form-urlencoded | multipart/form-data | text/plain）
#### - `fieldset`：将表单内的相关元素分组，并在周围绘制边框
```html
<form>
    <fieldset>
        <legend>这是分组小标题</legend>
        姓名：<input type="text"><br>
        电话：<input type="text"><br>
		住址：<input type="text">
    </fieldset>
</form>
```
![此处输入图片的描述][6]

    disabled  规定该组中的相关表单元素应该被禁用
    form=""  规定 fieldset 所属的一个或多个表单（*form_id）
    name=""  规定 fieldset 的名称（*text）
##### - `legend`：为fieldset元素定义标题
##### - `input/`：搜集用户输入的信息
    autofocus  自动获得焦点
    disabled  禁用此元素
    formnovalidate  提交表单时不进行验证
    multiple  允许一个以上的值
    readonly  输入字段为只读
    required  必填项
    placeholder=""  输入提示（*text）
    max=""  输入字段的最大值（*number|*date）
    min=""  输入字段的最小值（*number|*date）
    autocomplete=""  是否使用自动完成功能（on|off）
    form=""  输入字段所属的表单（*form_id）
    list=""  引用包含输入字段的预定义选项的datalist（*datalist_id）
    maxlength=""  输入字符的最大长度（*number）
    pattern=""  输入字段的值的模式或格式（*regexp）
    size=""  输入字段的宽度（*number）
    step=""  输入字的合法数字间隔（*number）
    value=""  input元素的值（*text）
    type=""  input元素的类型（button|checkbox|color|date|datetime|datetime-local|email|file|hidden|image|month|number|password|radio|range|reset|search|submit|tel|text|time|url|week）
    
    *以下属性需与type="file"配合使用：
    accept=""  规定通过上传的文件类型（audio/* | video/* | image/* | *MIME_type）
    
    *以下属性需与type="image"配合使用：
    src=""  以提交按钮形式显示的图像的URL（*URL）
    alt=""  图像输入的替代文本（*text）
    height=""  定义input字段的高度（*px|*%）
    width=""  定义input字段的宽度（*px|*%）
    
    *以下属性需与type="submit"或type="image"配合使用：
    formaction=""  覆盖表单的action属性（*URL）
    formenctype=""  覆盖表单的enctype属性（application/x-www-form-urlencoded | multipart/form-data | text/plain）
    formmethod=""  覆盖表单的method属性（get|post）
    formtarget=""  覆盖表单的target属性（_blank|_self|_parent|_top|*framename）
    
    *以下属性需与type="checkbox"或type="radio"配合使用：
    checked  在页面加载时应该被预先选定的input元素
    
##### - `label`：为input元素定义标注（标记）
当用户点击label元素时，浏览器就会自动将焦点转到相关的表单控件上
```html
<form>
    <label for="male">Male</label>
    <input type="radio" name="sex" id="male" checked/>
    <label for="female">Female</label>
    <input type="radio" name="sex" id="female"/>
</form>

<!-- label的for属性必须与input的id属性绑定使用 -->
<!-- 为实现单选效果，须向一组控件的每个input定义相同的name值 -->
```
![效果示例][7]

    for=""  label绑定到哪个表单元素（*element_id）
    form=""  label字段所属的一个或多个表单（*form_id）
<br/>
### • `h1`~`h6`：定义标题
```html
<h1>h1标题</h1>
<h2>h2标题</h2>
<h3>h3标题</h3>
<h4>h4标题</h4>
<h5>h5标题</h5>
<h6>h6标题</h6>
<p>p文字段落（1rem = 16px）</p>

<!-- 编号递增，则字号递减 -->
```
![此处输入图片的描述][8]
<br/>
### • `hr/`：在HTML页面中创建一条水平线
```html
<p>水平线上</p>
<hr/>
<p>水平线下</p>
```
<p>水平线上</p>
<hr/>
<p>水平线下</p>
<br/>
### • `i`：显示斜体文本效果
```html
<i>这是一段斜体字</i>

<!-- <i>、<b>、<u>元素相邻时，需用<br/>换行 -->
```
<i>这是一段斜体字</i>
<br/>
### • `img/`：向网页中嵌入一幅图像
```html
<img src="/i/eg_tulip.jpg" alt="郁金香"/>
<img src="http://www.w3school.com.cn/i/eg_tulip.jpg" alt="郁金香"/>

<!-- src：图像文件的路径   alt：图像无法显示时的替代文本 -->
```
<img src="http://www.w3school.com.cn/i/eg_tulip.jpg" alt="郁金香"/>

    width=""  规定图像的宽度（*px/*%）
    height=""  规定图像的高度（*px/*%）
    ismap  服务器端图像映射
    usemap="#……"  客户器端图像映射（*mapname）
    crossorigin=""  设置图像的跨域属性（anonymous|use-credentials）

**图像路径的书写方式：**
（假设要在网页文件h.html中引入图片文件i.jpg）
一、相对路径
1、同一根目录下
• i.jpg与h.html同级：`src="i.jpg"`
• i.jpg在h.html的下一级文件夹image中：`src="image/i.jpg"`
• i.jpg在h.html的上一级文件夹image中：`src="../i.jpg"`
• i.jpg在image文件夹中，h.html在html文件夹中，image与html同级：`src="../image/i.jpg"`
• 直接从当前根目录访问i.jpg：`src="/……/img/i.jpg"`
2、不同根目录下（假设i.jpg在C盘）：`src="file:///C:/……/i.jpg"` 
二、绝对路径
&nbsp;1、图片来源于网络：`src="http://www.w3school.com.cn/i.jpg"`
&nbsp;2、图片在本地硬盘上的位置：`src="C:\Users\Pictures\i.jpg"`
<br/>
### • `ins`：定义已经被插入文档中的文本

```html
<p>My favorite color is <del>blue</del> <ins>red</ins>!</p>

<!-- 通常将 ins 与 del 一起使用，描述文档中的更新和修正 -->
```
![此处输入图片的描述][9]
<br/>
### • `kbd`：定义键盘文本
```html
使用快捷键 <kbd>Ctrl</kbd> + <kbd>C</kbd> 进行复制

<!-- 不同的CSS设置下，kbd标签将显示不同的效果 -->
```
使用快捷键 <kbd>Ctrl</kbd> + <kbd>C</kbd> 进行复制
<br/>
### • `link/`：定义文档与外部资源的关系
```html
<head>
    <link rel="stylesheet" type="text/css" href="styles.css"/>
</head>

<!-- link只能存在于head部分，可出现多次 -->
```
    rel=""  必需，当前文档与被链接文档之间的关系（alternate|archives|author|bookmark|external|first|help|icon|last|license|next|nofollow|noreferrer|pingback|prefetch|prev|search|sidebar|stylesheet|tag|up）
    type=""  被链接文档的MIME类型（*MIME_type）
    href=""  被链接文档的位置（*URL）
    hreflang=""  被链接文档中文本的语言（*language_code）
    media=""  被链接文档显示设备（*media_query）
    
    *以下属性需与rel="icon"配合使用：
    sizes=""  被链接资源的尺寸（*HeightxWidth|any）
<br/>
### • `meta/`：提供有关页面的元信息
```html
<head>
    <meta charset="UTF-8"/>
    <meta name="keywords" content="HTML,CSS,JavaScript"/>
    <meta http-equiv="refresh" content="30"/>
</head>

以上内容发送到浏览器的元信息为：
content-type:text/html
charset:UTF-8
keywords:HTML,CSS,JavaScript
refresh:30

<!-- content属性始终要与name或http-equiv一起使用 -->
```

    charset=""  定义文档的字符编码（*character_set）
    content=""  定义与http-equiv或name属性相关的元信息（*text）
    http-equiv=""  把content属性关联到HTTP头部（content-type|default-style|refresh）
    name=""  把content属性关联到一个名称（application-name|author|description|generator|keywords）
<br/>
### • `ol`：定义有序列表
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
    reversed  降序
    start=""  起始值（*number）
    type=""  标记类型（1|A|a|I|i）
#### - `li`：定义列表项目
<br/>
### • `p`：定义段落
```html
<p>这是一段文本</p>
    
<!-- 自动换行，相邻段落间自动拉开垂直间距 -->
```
<p>这是一段文本</p>
<br/>
### • `picture`：为不同的显示/设备场景提供图像版本
浏览器会选择最匹配的 source 元素，如果没有匹配的，就显示 img 元素的内容
```html
<picture>
  <source src="/img1.jpg" media="screen and (max-width:576px)">
  <source src="/img2.jpg" media="screen and (max-width:1200px)">
  ……
  <img src="/img.jpg">
</picture>
```
#### - `source`：为媒体元素（如 video、audio）定义媒体资源
#### - `img`：定义 HTML 页面中的图像
<br/>
### • `pre`：定义预格式化的文本
pre元素中的文本通常会保留空格和换行符，而文本也会呈现为等宽字体；文本不可包含分段标签（如h*、p、address等）
```html
<pre>
<code>&lt;p&gt;Sample text here&lt;/p&gt;
&lt;p&gt;And another line of sample text here&lt;/p&gt;</code>
</pre>

<!-- 文本中需用字符实体表示特殊字符；通常与 code 标签结合使用 -->
```
<pre>
<code>&lt;p&gt;Sample text here&lt;/p&gt;
&lt;p&gt;And another line of sample text here&lt;/p&gt;</code>
</pre>
    width=""  定义每行的最大字符数（*number）
<br/>
### • `q`：定义短的引用
```html
<p>下面是一段引用的文本：<q>这是引用的内容</q></p>
```
![效果示例][10]

    cite=""  定义引用的出处或来源（*URL）
<br/>
### • `s`：对不正确、不准确或没有用的文本进行标识
```html
<p><s>My car is blue.</s></p>
<p>My new car is silver.</p>
```
<p><s>My car is blue.</s></p>
<p>My new car is silver.</p>
<br/>
### • `samp`：定义计算机程序的样本文本
```html
字符序列 <samp>ae</samp> 可能会被转换为 &aelig; 连字字符

<!-- 只有在提取某些短字符序列加以强调的情况下，才使用这个标签 -->
```
字符序列 <samp>ae</samp> 可能会被转换为 &aelig; 连字字符
<br/>
### • `script`：定义客户端脚本
```html
<!-- 直接插入脚本语句 -->
<script type="text/javascript">
    document.write("<h1>Hello World!</h1>")
</script>

<!-- 链接外部脚本文件 -->
<script type="text/javascript" src="script.js">
</script>   

<!-- type：脚本的MIME类型    src：规定外部脚本的URL -->
```

    async  异步执行脚本，仅适用于外部脚本
    defer  延迟执行脚本，仅适用于外部脚本
    charset=""  规定在脚本中使用的字符编码，仅适用于外部脚本（*charset）
<br/>
### • `select`：创建下拉列表
```html
<select>
    <option value="optA">optionA</option>
    <option value="optB">optionB</option>
    <option value="optC">optionC</option>
</select>

<!-- value：定义送往服务器的选项值 -->
```
<select>
    <option value="optA">optionA</option>
    <option value="optB">optionB</option>
    <option value="optC">optionC</option>
</select>

    autofocus  规定在页面加载时下拉列表自动获得焦点
    disabled  会禁用下拉列表
    multiple  可选择多个选项
    required  规定用户在提交表单前必须选择一个下拉列表中的选项
    form=""  定义 select 字段所属的一个或多个表单（*form_id）
    name=""  定义下拉列表的名称（*name）
    size=""  规定下拉列表中可见选项的数目（*number）
#### - `optgroup`：把相关的选项组合在一起
```html
<select>
    <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
    </optgroup>
    <optgroup label="German Cars">
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
    </optgroup>
</select>

<!-- label：为选项组规定描述 -->
```
![此处输入图片的描述][11]

    disabled  规定禁用该选项组
##### - `option`：定义下拉列表中的一个选项（一个条目）
    disabled  规定此选项应在首次加载时被禁用
    label=""  定义当使用optgroup时所使用的标注（*text）
    selected  规定选项（在首次显示在列表中时）表现为选中状态
<br/>
### • `small`：定义小型文本（和旁注）
```html
<h1>h1标题 <small>h1副标题</small></h1>
<h2>h2标题 <small>h2副标题</small></h2>
<h3>h3标题 <small>h3副标题</small></h3>
<h4>h4标题 <small>h4副标题</small></h4>
<h5>h5标题 <small>h5副标题</small></h5>
<h6>h6标题 <small>h6副标题</small></h6>
<p>p文本 <small>p副文本</small></p>
<small>单独使用时即按默认文本样式缩小</small>

<!-- 缩小文本的样式根据标签类型而定 -->
```
![此处输入图片的描述][12]
<br/>
### • `span`：对文档中的行内元素进行组合
```html
<p>我的母亲有<span style="color:blue;">蓝色</span>的眼睛，我的父亲有<span style="color:green;">绿色</span>的眼睛。</p>
```
<p>我的母亲有<span style="color:blue;">蓝色</span>的眼睛，我的父亲有<span style="color:green;">绿色</span>的眼睛。</p>
<br/>
### • `strong`：定义计算机程序的样本重要的文本
```html
<p>strong元素内的文本会被 <strong>加粗</strong> 显示</p>
```
<p>strong元素内的文本会被 <strong>加粗</strong> 显示</p>
<br/>
### • `style`：定义HTML文档的样式信息
```html
<style type="text/css">
    h1 {color: red;}
    p {color: blue;}
</style>

<!-- type="text/css"：规定样式表的MIME类型 -->
```

    media=""  为样式表规定不同的媒体类型（*media_query）
    scoped  样式仅应用到style元素的父元素及其子元素
<br/>
### • `table`：定义HTML表格
```html
<table>
    <caption>这是表格的标题</caption>
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
<table>
    <caption>这是表格的标题</caption>
    <tr>
        <th>表头：1行1列</th>
        <th>表头：1行2列</th>
    </tr>
    <tr>
        <td>内容：2行1列</td>
        <td>内容：2行2列</td>
    </tr>
</table>
    border="1"  在表格单元周围添加边框（表格不用于布局目的）
#### - `caption`：定义表格的标题（每个表格只能有一个标题）
#### - `tr`：定义 HTML 表格中的行
##### - `th`：定义 HTML 表格中的表头单元格
    
    colspan=""  表头单元格可横跨的列数（*number）
    rowspan=""  表头单元格可横跨的行数（*number）
    headers=""  与表头单元格相关联的一个或多个表头单元格（*header_id）
    scope=""  表头单元格是列/行/列组/行组的头部（col|row|colgroup|rowgroup）

##### - `td`：定义 HTML 表格中的标准单元格
    
    colspan=""  单元格可横跨的列数（*number）
    rowspan=""  单元格可横跨的行数（*number）
    headers=""  与单元格相关联的一个或多个表头单元格（*header_id）
<br/>
### • `textarea`：定义多行的文本输入控件
```html
<textarea rows="3" cols="20">这是一个多行文本框</textarea>

<!-- 通过cols和rows属性来规定textarea的尺寸 -->
```
![效果示例][13]

    autofocus  自动获得焦点
    disabled  禁用该文本区
    readonly  文本区为只读
    required  文本区域是必填的
    cols=""  文本区内的可见宽度（*number）
    rows=""  文本区内的可见行数（*number）
    form=""  文本区域所属的表单（*form_id）
    maxlength=""  文本区域的最大字符数（*number）
    name=""  文本区的名称（*text）
    placeholder=""  文本区域的简短提示（*text）
    wrap=""  文本如何换行（hard|soft）
<br/>
### • `u`：定义下划线文本
```html
<u>这是一段有下划线的文字</u>

<!-- <i>、<b>、<u>元素相邻时，需用<br/>换行 -->
```
![此处输入图片的描述][14]
<br/>
### • `ul`：定义无序列表
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
#### - `li`：定义列表项目
<br/>
### • `var`：定义变量，或者由用户提供的值
```html
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>

<!-- 文本通常显示为斜体；经常与 code 和 pre 标签一起使用 -->
```
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>

---

## HTML 5 新标签
### • `article`：规定独立的自包含内容（独立于站点的其余部分对其进行分发）
文章潜在来源：论坛帖子、报纸文章、博客条目、用户评论……
```html
<article>
    <h1>文章标题</h1>
    <p>文章内容</p>
</article>
```
<br/>
### • `aside`：定义主题之外的相关内容，通常显示成侧边栏或注释（例如目录、索引、广告、简介等）
```html
<p>The Disney movie <em>The Little Mermaid</em> was first released to theatres in 1989.</p>  
<aside>The movie earned $87 million during its initial release.</aside>  
<p>More info about the movie...</p>  
```
<br/>
### • `details`：规定了用户可见的或者隐藏的需求的补充细节
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
![此处输入图片的描述][15]
#### - `summary`：为details元素定义一个可见的标题，当用户点击标题时会显示出详细信息
<br/>
### • `figure`：规定独立的流内容（图像、图表、照片、代码等等）
```html
<p>这是一段主要内容这是一段主要内容这是一段主要内容</p>
<figure>
    <p>这是一段附加内容：</p>
    <img src="/img.jpg" alt="附加图片" width="50%">
    <figcaption>附加内容的小标题</figcaption>
</figure>

<!-- figcaption 应被置于 figure 下的第一个或最后一个位置 -->
```
![此处输入图片的描述][16]
#### - `figcaption`：定义 figure 元素的标题（caption）
<br/>
### • `footer`：定义文档或节的页脚（通常包含文档的作者、版权信息、使用条款链接、联系信息等）
```html
<footer>
    <p>页脚内容1</p>
    <p>页脚内容2</p>
</footer>
```
<br/>
### • `header`：定义文档的页眉（介绍信息）
```html
<header>
    <h1>页眉主题</h1>
    <p>页眉内容</p>
</header>
<p>文档内容</p>
```
<br/>
### • `mark`：定义高亮的文本
```html
<h1>h标题内<mark>高亮</mark></h1>    
<p>p文本内<mark>高亮</mark></p>
<mark>单独使用高亮</mark>
```
![此处输入图片的描述][17]
<br/>
### • `nav`：定义导航链接的部分
```html
<nav>
    <a href="跳转链接1">导航文本1</a>
    <a href="跳转链接2">导航文本2</a>
</nav>

<!-- 文档中的“向前”“向后”按钮应放到nav元素中 -->
```
<nav>
<a href="/html/">HTML</a> | <a href="/css/">CSS</a> | <a href="/js/">JavaScript</a> | <a href="/jquery/">jQuery</a>
</nav>
#### - `a`：定义超链接
<br/>
### • `section`：定义文档中的节（section、区段）
```html
<section>
    <h1>第一节标题</h1>
    <p>第一节内容</p>
</section>

<section>
    <h1>第二节标题</h1>
    <p>第二节内容</p>
</section>
```
<br/>
### • `source`：为媒体元素（如 video、audio）定义媒体资源
```html
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
  您的浏览器不支持 audio 元素
</audio>

<!-- src：媒体文件的URL    type：媒体资源的MIME类型 -->
```
    media=""  媒体资源的类型，供浏览器决定是否下载（*media_query）
<br/>
### • `video`：定义视频
```html
<video src="/i/movie.ogg">视频无法显示</video>

<!-- src：视频文件的URL -->
```
<video src="http://www.w3school.com.cn/i/movie.ogg">视频无法显示</video>

    controls  显示播放控件
    autoplay  自动播放
    loop  循环播放
    muted  静音
    preload=""  预备播放，autoplay下忽略（auto|metadata|none）
    poster=""  视频封面图（*URL）
    width=""  视频播放器的宽度（*px）
    height=""  视频播放器的高度（*px）

---

## HTML 全局属性
    hidden  规定对元素进行隐藏
    accesskey=""  规定激活元素的快捷键（*character）
    class=""  定义了元素的类名（*classname）
    contenteditable=""  指定元素内容是否可编辑（true|false）
    contextmenu=""  规定当用户右击元素时显示的上下文菜单（*menu_id）
    data-*=""  存储私有页面后应用的自定义数据（*somevalue）
    dir=""  规定元素内容的文本方向（ltr|rtl|auto）
    draggable=""  规定元素是否可拖动（true|false|auto）
    id=""  规定 HTML 元素的唯一的 id（idname）
    lang=""  规定元素内容的语言（*language_code）
    spellcheck=""  规定是否对元素内容进行拼写检查（true|false）
    style=""  规定元素的行内样式（*style_definitions）
    tabindex=""  规定当使用 Tab 键进行导航时元素的顺序（*number）
    title=""  规定关于元素的额外信息（*text）

---

## * HTML 语义化
根据内容的结构化，选择合适的标签，便于开发者阅读和写出更优雅的代码，让浏览器爬虫和机器更好地解析
>语义化程度：**div**（无语义） **<** **section**（整体） **<** **article**（独立）

**• 结构：**
标题 `<h1>`~`<h6>`
内容 `<section>` > `<article>`

表名 `<caption>`
表头 `<thead>` > 数据名称 `<th>`
内容 `<tbody>` > 数据值 `<td>`
尾部 `<tfoot>` > 数据值 `<td>`

**• 嵌套方式：**
```graphLR
    A(body) --- B(section A)
    A --- C(section B)
    B --- D(article 1)
    B --- E(article 2)
    B --- F(article 3)
```

**• 注意事项：**
1、尽可能少地使用无语义的标签~~`<div>`、`<sapn>`~~
2、在语义不明显时，尽量使用`<p>`，有兼容性
3、不要使用纯样式标签，改用CSS设置

---


  [1]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwnuvfapozj20o101tgll.jpg
  [2]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwomk40xlcj20ny029jre.jpg
  [3]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwon64k6zfj20ny0c8myv.jpg
  [4]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwoq7qezoyj20nw01cmx6.jpg
  [5]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwol0kj9z7j20ns01n743.jpg
  [6]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwoi5c27znj20np058weh.jpg
  [7]: https://wx3.sinaimg.cn/mw690/7de6638dly1fv2dlmghllj20pl03o3ym.jpg
  [8]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwny027prkj20nr0cwjrp.jpg
  [9]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwop2c6iloj20nw0190sl.jpg
  [10]: https://wx1.sinaimg.cn/mw690/7de6638dly1fvqlgxoupej20pi016aa0.jpg
  [11]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwok9hlajcj20o205tglm.jpg
  [12]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwnyt0d7chj20np0eeq3m.jpg
  [13]: https://wx1.sinaimg.cn/mw690/7de6638dly1fu2okz4rvsj206j02gweb.jpg
  [14]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwop3tsf1kj20o901bwed.jpg
  [15]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwnuvfapozj20o101tgll.jpg
  [16]: https://wx4.sinaimg.cn/mw690/7de6638dly1g22ves9tipj20pi0cg0ws.jpg
  [17]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwnyxwpugij20nw05zdfw.jpg