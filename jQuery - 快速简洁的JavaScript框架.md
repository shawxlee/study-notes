# jQuery - 快速简洁的JavaScript框架

---

## jQuery CDNs
- [*jQuery CDN*][1] - jQuery Core 3.4.0
```html
<!-- uncompressed -->
<script src="https://code.jquery.com/jquery-3.4.0.js" ntegrity="sha256-DYZMCC8HTC+QDr5QNaIcfR7VSPtcISykd+6eSmBW5qo=" crossorigin="anonymous"></script>

<!-- minified -->
<script src="https://code.jquery.com/jquery-3.4.0.min.js" integrity="sha256-BJeo0qm959uMBGb65z40ejJYGSgR7REI4+CW1fNKwOg=" crossorigin="anonymous"></script>

<!-- slim -->
<script src="https://code.jquery.com/jquery-3.4.0.slim.js" integrity="sha256-milezx5lakrZu0OP9b2QWFy1ft/UEUK6NH1Jqz8hUhQ=" crossorigin="anonymous"></script>

<!-- slim minified -->
<script src="https://code.jquery.com/jquery-3.4.0.slim.min.js" integrity="sha256-ZaXnYkHGqIhqTbJ6MB4l9Frs/r7U4jlx7ir8PJYBqbI=" crossorigin="anonymous"></script>
```

- [*Microsoft Ajax CDN*][2] - jQuery version 3.3.1
```html
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.js
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.min.js
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.min.map
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.slim.js
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.slim.min.js
https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.3.1.slim.min.map
```

- [*cdnjs CDN*][3] - jQuery version 3.4.0
```html
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/core.js
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.js
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.min.js
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.min.map
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.slim.js
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.slim.min.js
https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.slim.min.map
```

- Staticfile CDN
```html
https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js
```

- 百度 CDN
```html
https://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js
https://libs.baidu.com/jquery/2.1.4/jquery.min.js
```

- 又拍云 CDN
```html
https://upcdn.b0.upaiyun.com/libs/jquery/jquery-2.0.2.min.js
```

- 新浪 CDN
```html
https://lib.sinaapp.com/js/jquery/2.0.2/jquery-2.0.2.min.js
```

---

## jQuery选择器

### • `$("CSS选择器")`
### • `$("元素:关键词")`

    *:first  选取第一个*元素
    *:last  选取最后一个*元素
    *:even  选取每个顺序为偶数的*元素（从0开始）
    *:odd  选取每个顺序为奇数的*元素（从0开始）
    *:hidden  所有隐藏的*元素
    *:visible  选取每个当前是可见的*元素

### • `$("元素:关键词(n)")`

    *:eq(n)  选取第n+1个*元素（从0开始）
    *:gt(n)  选取第n+1个*元素之后的所有*元素（从0开始）
    *:lt(n)  选取第n+1个*元素之前的所有*元素（从0开始）

### • `$(":关键词")`

    :contains(……)  选取所有包含指定字符串的元素
    :animated  选取当前的所有动画元素
    :header  选取所有<h1>~<h6>元素
    :selected  选取所有被选择的<option>元素
    :input  选取所有<input>元素
    :text  选取所有type="text"的<input>元素
    :password  选取所有type="password"的<input>元素
    :radio  选取所有type="radio"的<input>元素
    :checkbox  选取所有type="checkbox"的<input>元素
    :submit  选取所有type="submit"的<input>元素
    :reset  选取所有type="reset"的<input>元素
    :button  选取所有type="button"的<input>元素
    :image  选取所有type="image"的<input>元素
    :file  选取所有type="file"的<input>元素

### • `$(对象)`：获取当前JS对象转化成jQuery对象
### • `$(this)`：获取当前HTML元素转换为jQuery对象

---

## jQuery方法
### 1、jQuery事件方法
#### • `blur()`：当元素失去焦点时发生 blur 事件
```javascript
$(selector).blur();    //触发blur事件
$(selector).blur(function);    //将函数绑定到blur事件
```
    *function  规定当发生 blur 事件时运行的函数

#### • `click()`：点击元素时发生click事件
```javascript
$(selector).click();    //触发click事件
$(selector).click(function);    //将函数绑定到click事件
```
    *function  规定当发生click事件时运行的函数

#### • `event.stopPropagation()`：阻止事件冒泡到父元素，阻止任何父事件处理程序被执行
```javascript
event.stopPropagation();

//*event：参数来自事件绑定函数
```

#### • `focus()`：当元素获得焦点时发生 focus 事件
```javascript
$(selector).focus();    //触发focus事件
$(selector).focus(function);    //将函数绑定到focus事件
```
    *function  规定当发生 focus 事件时运行的函数

#### • `on()`：在被选元素及子元素上添加一个或多个事件处理程序
```javascript
$(selector).on(event,childSelector,data,function);

//*event：规定要从被选元素移除的一个或多个有效事件或命名空间，由空格分隔多个事件值，也可以是数组
```
    *childSelector  规定只能添加到指定的子元素上的事件处理程序（且不是选择器本身）
    *data  规定传递到函数的额外数据
    *function  规定当事件发生时运行的函数

#### • `ready()`：当DOM已经加载，且页面完全呈现时，发生ready事件
```javascript
$(document).ready(function);
$().ready(function);
$(function);

//*function：文档加载后要运行的函数
```
<br/>
### 2、jQuery HTML/CSS 方法
#### • `addClass()`：向被选元素添加一个或多个类
```javascript
$(selector).addClass(class);   
$(selector).addClass(function(index,oldclass));    //使用函数来添加类

//*class：要添加的class的名称，多个类用空格隔开
//*function(index,oldclass)：规定返回一个或多个待添加类名的函数
```
    *index  接收选择器的index位置
    *oldclass  接收选择器的旧的类值

#### • `append()`：在被选元素的尾部插入指定内容
```javascript
$(selector).append(content);   
$(selector).append(function(index,html));    //使用函数来附加内容

//*content：要插入的内容（可包含HTML标签）
//*function(index,html)：规定返回待插入内容的函数
```
    *index  接收选择器的index位置
    *html  接收选择器的当前HTML

#### • `attr()`：设置或返回被选元素的属性值
```javascript
$(selector).attr(attribute);    //返回属性值
$(selector).attr(attribute,value);    //设置属性/值
$(selector).attr(attribute,function(index,oldvalue));    //使用函数来设置属性/值
$(selector).attr({attribute:value, attribute:value ...});    //设置多个属性/值对

//*attribute：规定属性的名称
//*value：规定属性的值
//*function(index,oldvalue)：规定返回属性值的函数

//对于布尔值的属性，prop()返回true|false，attr()返回属性名称
//对于元素中我们自定义的属性，建议使用attr()
```

#### • `css()`：返回或设置匹配的元素的一个或多个样式属性
```javascript
$(selector).css(name);    //返回 CSS 属性值
$(selector).css(name,value);    //设置 CSS 属性
$(selector).css(name,function(index,value));    //使用函数来设置 CSS 属性
$(selector).css({property:value, property:value, ...});    //设置多个 CSS 属性/值对

//*name：规定CSS属性的名称
//*function(index,value)：规定返回CSS属性新值的函数
//*property:value：规定要设置为样式属性的“名称/值对”对象
```
    *value  规定 CSS 属性的值；如果设置了空字符串值，则从元素中删除指定属性
    *index  接受选择器的 index 位置
    *oldvalue  接受 CSS 属性的当前值

#### • `hasClass()`：检查被选元素是否包含指定的class
```javascript
$(selector).hasClass(class);

//*class：需要在指定元素中查找的类
```

#### • `html()`：返回或设置被选元素的内容 (innerHTML)
```javascript
$(selector).html();    //返回元素内容
$(selector).html(content);    //设置元素内容
$(selector).html(function(index,oldcontent));    //使用函数来设置元素内容

//*function(index,oldcontent)：规定一个返回被选元素的新内容的函数
```
    *content  规定被选元素的新内容，可包含<HTML>标签
    *index  接收选择器的index位置
    *oldcontent  接收选择器的当前内容

#### • `prop()`：设置或返回被选元素的属性和值
```javascript
$(selector).prop(property);    //返回属性的值
$(selector).prop(property,value);    //设置属性和值
$(selector).prop(property,function(index,currentvalue));    //使用函数设置属性和值
$(selector).prop({property:value, property:value,...});    //置多个属性和值

//*property：规定属性的名称

//对于布尔值的属性，prop()返回true|false，attr()返回属性名称
//对于元素原本具有的属性，建议使用prop()
```
    *value  规定属性的值
    function(*index,*currentvalue)  规定返回要设置的属性值的函数（*index：检索集合中元素的 index 位置  *currentvalue：检索被选元素的当前属性值）

#### • `remove()`：移除被选元素，包括所有的文本和子节点
```javascript
$(selector).remove();
```

#### • `removeClass()`：从被选元素移除一个或多个类
```javascript
$(selector).removeClass(class);
$(selector).removeClass(function(index,oldclass));    //使用函数来移除类

//*function(index,oldclass)：通过运行函数来移除指定的类
```
    *class  要移除的class的名称，多个类用空格隔开
    *index  接收选择器的index位置
    *oldclass  接收选择器的旧的类值

#### • `scrollLeft()`：返回或设置匹配元素的滚动条的水平位置（像素值）
```javascript
$(selector).scrollLeft();    //返回水平滚动条位置
$(selector).scrollLeft(position);    //设置水平滚动条位置
```
    *position  规定以像素计的新位置

#### • `text()`：设置或返回被选元素的文本内容
```javascript
$(selector).text();    //返回文本内容，会删除 HTML 标记
$(selector).text(content);    //设置文本内容
$(selector).text(function(index,oldcontent));    //使用函数来设置元素内容

//*function(index,oldcontent)：规定返回被选元素的新文本内容的函数
```
    *content  规定被选元素的新文本内容（特殊字符会被编码）
    *index  接收选择器的index位置
    *oldcontent  接收选择器的当前内容

#### • `toggleClass()`：对添加和移除被选元素的一个或多个类进行切换
```javascript
$(selector).toggleClass(classname,function(index,currentclass),switch);

//*classname：规定添加或移除的一个或多个类名。如需规定若干个类，请使用空格分隔类名
```
    *function(index,currentclass)  规定返回需要添加/删除的一个或多个类名的函数（*index：返回集合中元素的 index 位置  *currentclass：返回被选元素的当前类名）
    *switch  布尔值，规定是否仅仅添加（true）或移除（false）类

#### • `val()`：返回或设置被选元素的值
```javascript
$(selector).val();    //返回 Value 属性
$(selector).val(value);    //设置 Value 属性的值
$(selector).val(function(index,oldvalue));    //使用函数设置 Value 属性的值

//*value：设置Value属性的值
//*function(index,oldvalue)：规定返回要设置的值的函数
```
    *index  接收选择器的index位置
    *oldvalue  接收选择器的当前value属性

---

## jQuery函数
### 1、jQuery效果函数
#### • `animate()`：执行 CSS 属性集的自定义动画
```javascript
$(selector).animate({styles},speed,easing,callback);

//*styles：规定产生动画效果的一个或多个 CSS 属性/值
```
    *speed  规定动画的速度（毫秒|"slow"|"fast"）
    *easing  规定在动画的不同点中元素的速度（"swing"|"linear"）
    *callback  animate 函数执行完之后，要执行的函数。

#### • `fadeIn()`：使用淡入效果来显示一个隐藏的元素
```javascript
$(selector).fadeIn(speed,callback);
```
    *speed  元素从隐藏到完全可见的速度
    *callback  fadeIn函数执行完之后，要执行的函数

#### • `fadeOut()`：使用淡出效果来隐藏一个可见的元素
```javascript
$(selector).fadeOut(speed,callback);
```
    *speed  元素从可见到隐藏的速度
    *callback  fadeOut函数执行完之后，要执行的函数

#### • `hide()`：如果被选元素已被显示，则隐藏该元素
```javascript
$(selector).hide(speed,callback);
```
    *speed  元素从可见到隐藏的速度
    *callback  hide函数执行完之后，要执行的函数

#### • `show()`：如果被选元素已被隐藏，则显示该元素
```javascript
$(selector).show(speed,callback);
```
    *speed  元素从隐藏到完全可见的速度
    *callback  show函数执行完之后，要执行的函数

#### • `toggle()`：切换元素的可见状态
```javascript
$(selector).toggle(speed,callback,switch);
```
    *speed  元素切换状态的速度
    *callback  toggle函数执行完之后，要执行的函数
    *switch  布尔值，规定 toggle 是否隐藏或显示所有被选元素

<br/>
### 2、jQuery Ajax操作函数
#### • `ajax()`：通过HTTP请求加载远程数据
```javascript
jQuery.ajax([settings]);
```
    *settings  用于配置 Ajax 请求的键值对集合
<table>
    <tr style="background: #555555; color: #fff;">
        <th style="text-align:center;">参数</th>
        <th style="text-align:center;">类型</th>
        <th style="text-align:center;">定义</th>
        <th style="text-align:center;">默认值</th>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>url</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">发送请求的URL</td>
        <td style="text-align:center;">当前页面地址</td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>type</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">请求的类型</td>
        <td style="text-align:center;">"GET"</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>timeout</code></td>
        <td style="text-align:center;">Number</td>
        <td style="text-align:center;">设置请求超时时间（毫秒）</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>async</code></td>
        <td style="text-align:center;">Boolean</td>
        <td style="text-align:center;">请求是否异步处理</td>
        <td style="text-align:center;">true</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>cache</code></td>
        <td style="text-align:center;">Boolean</td>
        <td style="text-align:center;">浏览器是否缓存被请求页面</td>
        <td style="text-align:center;">true</td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>data</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">要发送到服务器的数据</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>dataType</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">预期的服务器响应的数据类型</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>beforeSend(xhr)</code></td>
        <td style="text-align:center;">Function</td>
        <td style="text-align:center;">发送请求前运行的函数</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>complete(xhr,ts)</code></td>
        <td style="text-align:center;">Function</td>
        <td style="text-align:center;">请求完成时运行的函数</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>success</code></td>
        <td style="text-align:center;">Function</td>
        <td style="text-align:center;">当请求成功时运行的函数</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>error</code></td>
        <td style="text-align:center;">Function</td>
        <td style="text-align:center;">当请求失败时运行的函数</td>
        <td style="text-align:center;">xml或html</td>
    </tr>
    <tr>
        <td style="text-align:center;font-weight:bold;"><code>contentType</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">发送数据到服务器时所使用的内容类型</td>
        <td style="text-align:center;">"application/x-www-form-urlencoded"</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>dataFilter</code></td>
        <td style="text-align:center;">Function</td>
        <td style="text-align:center;">给返回的原始数据进行预处理</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>global</code></td>
        <td style="text-align:center;">Boolean</td>
        <td style="text-align:center;">是否触发全局AJAX事件</td>
        <td style="text-align:center;">true</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>ifModified</code></td>
        <td style="text-align:center;">Boolean</td>
        <td style="text-align:center;">是否仅在服务器数据改变时获取新数据</td>
        <td style="text-align:center;">false</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>jsonp</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">在一个jsonp中重写回调函数的字符串</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>username</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">响应HTTP访问认证请求的用户名</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>password</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">响应HTTP访问认证请求的密码</td>
        <td style="text-align:center;"></td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>processData</code></td>
        <td style="text-align:center;">Boolean</td>
        <td style="text-align:center;">发送的数据是否转换为查询字符串</td>
        <td style="text-align:center;">true</td>
    </tr>
    <tr>
        <td style="text-align:center;"><code>scriptCharset</code></td>
        <td style="text-align:center;">String</td>
        <td style="text-align:center;">请求的字符集</td>
        <td style="text-align:center;"></td>
    </tr>
</table>
<br/>
### 3、jQuery遍历函数
#### • `each()`：为每个匹配元素规定运行的函数
```javascript
$(selector).each(function(index,element));

//*function(index,element)：为每个匹配元素规定运行的函数
//*index：选择器的index位置
//*element：当前的元素（或this选择器）
```

#### • `find()`：获得当前元素集合中每个元素的后代，通过选择器、jQuery 对象或元素来筛选
```javascript
.find(selector);

//*selector：字符串值，包含供匹配当前元素集合的选择器表达式
```

#### • `not()`：从匹配元素集合中删除元素
```javascript
.not(selector);
.not(element);
.not(function(index));

//*selector：字符串值，包含用于匹配元素的选择器表达式
//*element：一个或多个需要从匹配集中删除的 DOM 元素
//*function(index)：用于检测集合中每个元素的函数，this 是当前 DOM 元素
```

---

  [1]: https://code.jquery.com/
  [2]: https://docs.microsoft.com/en-us/aspnet/ajax/cdn/overview#jQuery_Releases_on_the_CDN_0
  [3]: https://cdnjs.com/libraries/jquery/
  [4]: https://cdn.bootcss.com/jquery/1.10.2/jquery.min.js
  [5]: https://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js
  [6]: https://lib.sinaapp.com/js/jquery/2.0.2/jquery-2.0.2.min.js
  [7]: https://ajax.aspnetcdn.com/ajax/jquery/jquery-1.9.0.min.js
  [8]: https://code.jquery.com/jquery-3.3.1.min.js
  [9]: http://libs.useso.com/js/jquery/1.9.1/jquery.min.js
  [10]: http://cdn.static.runoob.com/libs/jquery/1.10.2/jquery.min.js