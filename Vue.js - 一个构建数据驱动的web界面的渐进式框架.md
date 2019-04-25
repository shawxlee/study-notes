# Vue.js - 一个构建数据驱动的web界面的渐进式框架

---

## 安装
### 1、官网下载独立版本
下载地址：[https://vuejs.org/v2/guide/installation.html][1]

### 2、引入CDN
官网CDN（推荐）：[https://cdn.jsdelivr.net/npm/vue@2.5.17/dist/vue.js][2]
BootCDN（国内）：[https://cdn.bootcss.com/vue/2.4.2/vue.min.js][3]
unpkg：[https://unpkg.com/vue@2.5.17/dist/vue.js][4]
cdnjs：[https://cdnjs.cloudflare.com/ajax/libs/vue/2.1.8/vue.min.js][5]
```html
<head>
	<meta charset="utf-8">
    <title>……</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.5.17/dist/vue.js"></script>
</head>
```

---

## 起步
### 1、Vue实例：`var varName = new Vue({el: '#idName', ……});`
每个Vue应用都需要通过创建一个Vue实例来启动，即声明一个变量，这个变量称为“根实例”
```html
<body>
    <div id="idName1">……</div>   <!-- 定义元素的id名 -->
    <div id="idName2">……</div>
    
    <script type="text/javascript">
        var varName = new Vue({       //1、创建根实例
            el: '#idName1',           //2、el选项绑定元素id
            data: {                   //3、其他选项设置数据值
                ……
            }
        });
        new Vue({             //创建实例时也可省略变量名
            el: '#idName2',
            ……
        });
    </script>
</body>
```
<br/>
### 2、数据与方法：`data: {keyName: value, ……},`
Vue实例向响应式系统中加入了data对象中能找到的所有属性，当属性的值发生改变时，html视图将会产生相应的变化
```html
<body>
    <div id="apple">
		<h1>site: {{ site }}</h1>
		<h1>url: {{ url }}</h1>
		<h1>alexa: {{ alexa }}</h1>
	</div>

	<script type="text/javascript">
	    //先声明一个变量存放原始数据：
		var dat = {
			site: "Runoob",
			url: "www.runoob.com",
			alexa: "10000",
		};
		//再创建根实例启动vue应用：
		var app = new Vue({
			el: '#apple',      //绑定el选项与元素id
			data: dat,         //绑定data选项与原始数据
		});
		//检验数据是否绑定成功：
		document.write(app.site === dat.site);   //判定为“true”
		document.write("<br/>");
		//修改属性值，原始数据会跟着变化：
		app.site = "菜鸟教程";
		document.write(dat.site + "<br/>");
		//修改原始数据，属性也会跟着变化：
		dat.alexa = "1234";
		document.write(app.alexa);
	</script>
</body>
```
![效果示例][6]
#### • 前缀$：`$optName`

向Vue实例自带的属性或方法添加前缀$，以便与用户定义的属性区分开来
```html
<body>
	<div id="apple">
		<h1>site: {{ site }}</h1>
		<h1>url: {{ url }}</h1>
		<h1>alexa: {{ alexa }}</h1>
	</div>

	<script type="text/javascript">
		var data = {
			site: "Runoob",
			url: "www.runoob.com",
			alexa: "10000",
		};
		var app = new Vue({
			el: '#apple',
			data: data,      //变量与选项重名，难以区分
		});
		//给自带选项添加前缀$加以区分：
	document.write(app.$data === data);   //判定为“true”
		document.write("<br/>");
		document.write(app.data === data);   //判定为“false”
	</script>
</body>
```
![效果示例][7]

---

## 插值
### 1、文本插值：`{{ text }}`
文本插值只输出绑定数据的值的文本，不进行运算解析
```html
<body>
	<div id="apple">
		<h1>{{ message }}</h1>     ——只输出文本"1+1"
		<h1>{{ html }}</h1>        ——只输出文本"<p>sometext<p/>"
	</div>

	<script type="text/javascript">
		var dat = {
			message: "1+1",   //只显示文本，不进行运算
			html: "<p>sometext</p>",   //只显示源代码，不解析html
		};
		var app = new Vue({
			el: '#apple',
			data: dat,
		});
	</script>
</body>
```
![效果示例][8]
<br/>
### 2、表达式插值：`{{ expression }}`
表达式是JavaScript中的一个短语，解释器会计算结果，常量是最简单的表达式
```html
<body>
	<div id="apple">
	    {{ message }}<br/>               ——只输出值的文本"1+1"
	    {{ 1+1 }}<br/>                   ——输出计算结果"2"
	    {{ bool?'True':'False' }}<br/>   ——条件运算表达式
	    {{ title.toUpperCase() }}        ——JS对象方法表达式
	</div>

	<script type="text/javascript">
		var dat = {
			message: "1+1",
			bool: true,   //条件为true时，输出'True'
			title: "This is a title.",
		};
		var app = new Vue({
			el: '#apple',
			data: dat,
		});
	</script>
</body>

<!-- JS语句或控制流不是表达式，所以绑定不会生效 -->
```
![效果示例][9]
<br/>
### 3、数组插值：`{{ arrName[indexNumber] }}`
在HTML框架中可以直接用数组下标的形式引入数据
```html
<body>
	<div id="apple">
	    <h1>{{ name }}</h1>
        <div>
            <p>赵钱：{{ mark[0] }}</p>
            <p>孙李：{{ mark[2] }}</p>
            <p>周吴：{{ mark[1] }}</p>
            <p>郑王：{{ mark[1] }}</p>
        </div>
	</div>

	<script type="text/javascript">
		var dat = {
			title: "成绩单",
            mark: ["优秀","合格","不合格"],
		};
		var app = new Vue({
			el: '#apple',
			data: dat,
		});
	</script>
</body>
```
![效果示例][10]

---

## 属性
### 1、计算属性：`computed: {exprName: function() {……},},`
用于计算复杂的逻辑表达式，可以像绑定普通属性一样在模板中绑定计算属性
```html
<body>
	<div id="example">
		<p>初始数据：{{ original }}</p>
		<p>进行颠倒字符顺序的逻辑运算，输出结果：{{ result }}</p>
	</div>
	<div id="example2">调用其他实例的数据也可：{{ result2 }}</div>

	<script type="text/javascript">
	    var orig = {
	        original: "Hello!",
	    };
		var exam = new Vue({
			el: '#example',
			data: orig,
			// 在计算属性中进行一切复杂的逻辑运算
			computed: {
				// 在function中处理JS表达式
				result: function() {
				    // this指向根实例exam1
					return this.original.split('').reverse('').join('');
				},
			},
		});
		var exam2 = new Vue({
			el: '#example2',
			computed: {
				result2: function() {
				    // computed可以调用其他实例的数据
					return exam.original.split('').reverse('').join('');
				},
			},
		});
	</script>
</body>

<!-- 计算结果的值始终取决于初始数据的值，随着初始数据的修改而变化 -->
```
![此处输入图片的描述][11]
#### • 计算属性的缓存特性
与方法属性不同的是，计算属性依赖于初始数据进行缓存，只要初始数据不变，那么多次重新访问都会立即返回之前缓存的结果，而当相关依赖发生改变时才会重新求值，适用于性能消耗较大的运算
```html
<body>
	<div id="example">
		<p>方法属性返回毫秒数：{{ dateNow1() }}</p>
		<p>计算属性返回毫秒数：{{ dateNow2 }}</p>
	</div>

	<script type="text/javascript">
		new Vue({
			el: '#example',
			methods: {
			    dateNow1: function () {
					// 每当重新调用方法时，方法属性总会再次执行函数
					return Date.now();
				},
			},
			computed: {
				dateNow2: function () {
					// 此则表达式不依赖初始数据，因此计算将不再更新
					return Date.now();
				},
			},
		});
	</script>
</body>
```
#### • 自定义计算属性的setter
计算属性默认只有getter，但若需要也可以自定义一个setter
```html
<body>
	<div id="example">
		<p>输出姓名：{{ fullName }}</p>
	</div>

	<script type="text/javascript">
		new Vue({
			el: '#example',
			data: {
			    firstName: 'Li',
			    lastName: 'Lei',
			},
			computed: {
			    fullName: {
			        // getter
			        get: function() {
			            return this.firstName + ' ' + this.lastName;
			        },
			        // setter
			        set: function(newVal) {
			            var name = newVal.split(' ');
			            this.firstName = name[0];
			            this.lastName = name[name.length - 1];
			        },
			    },
			},
		});
	</script>
</body>
```

---

## 指令
指令是带有前缀v-的特殊属性，当表达式的值改变时，将影响作用到HTML文件
### 1、`v-bind:propName` / `:propName`：动态地绑定元素的属性
>★ 组件中的 prop 可以通过 v-bind 动态赋值
#### • 绑定href/src/title属性：`:href|src|title`
Step1 `:href|src|title="keyName"`
Step2 `keyName: 'value'`
```html
<body>
	<div id="example">
		<a v-bind:href="aUrl">输出可链接的文字（无标题）</a>
		<img :src="imgUrl">
		<a :href="aUrl" :title="aTitle">输出可链接文字（有标题）</a>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
	        data: {
	            aUrl: 'https://cn.vuejs.org/',
	            imgUrl: 'http://www.runoob.com/try/demo_source/logo.png',
	            aTitle: '我是标题！',
	        },
		});
	</script>
</body>
```
![效果示例][12]

#### • 绑定class属性：`:class`
##### - 对象语法：传给 v-bind:class 一个或多个对象，以动态地切换 class
Step1 `:class="{className: keyName}"` / `:class="ObjName"`
Step2 `keyName: true|false` / `ObjName: {'className': true|false}`
```html
<body>
	<div id="example">
		<div :class="{active: isActive, 'text-info': isTextInfo}">对象语法1（可选共存）</div>
		<div :class="classObject">对象语法2（可选共存）</div>
		<!-- :class指令可与普通的class属性共存 -->
		<div class="bg-primary" :class="{small: isSmall}"></div>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
	        data: {
	            isActive: true,
	            isTextInfo: false,
	            classObject: {
	                'lead': true,
	                'mark': false,
	            },
	            isSmall: true,
	        },
		});
	</script>
</body>

<!-- :class同样适用于自定义组件，元素上已经存在的类不会被覆盖 -->
```
##### - 数组语法：把一个数组传给 v-bind:class，以应用一个 class 列表
Step1 `:class="[keyName1, keyName2]"` / `:class="[condName ? keyName1 : '', keyName2]"` / `:class="[{className: keyName1}, keyName2]"`
Step2 `keyName1: 'className1', keyName2: 'className2'` / `keyName1: 'className1', keyName2: 'className2', condName: true|false` / `keyName1: true|false, keyName2: 'className2'`
```html
<body>
	<div id="example">
		<div :class="[activeClass, textInfoClass]">数组语法1（必须共存）</div>
		<!-- 如果想根据条件切换列表中的class，可以用三元表达式 -->
		<div :class="[isLead ? leadClass : '', markClass]">数组语法2（可选共存）</div>
		<!-- 当有多个条件class时，可以在数组语法中使用对象语法 -->
		<div :class="[{ small: isSmall }, bgPrimary]">数组语法3（可选共存）</div>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
	        data: {
	            activeClass: 'active',
	            textInfoClass: 'text-info',
	            isLead: true,
	            leadClass: 'lead',
	            markClass: 'mark',
	            isSmall: false,
	            bgPrimary: 'bg-primary',
	        },
		});
	</script>
</body>

<!-- :class同样适用于自定义组件，元素上已经存在的类不会被覆盖 -->
```

#### • 绑定style属性：`:style`
##### - 对象语法：传给 v-bind:style 一个或多个对象
Step1 `:style="{styleName: keyName}"` / `:style="ObjName"`
Step2 `keyName: value` / `ObjName: {styleName: value}`
```html
<body>
	<div id="example">
	    <!-- :style指令中的CSS属性名必须转换为camelCase命名法 -->
		<div :style="{color: activeColor, fontSize: activeFontSize}">对象语法1（必须共存）</div>
		<div :style="styleObject">对象语法2（必须共存）</div>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
	        data: {
	            activeColor: 'blue',
	            activeFontSize: '20px',
	            styleObject: {
	                //对象中的属性名也必须转换为camelCase命名法
	                lineHeight: 1,
	                textShadow: '1px 1px 3px grey',
	            },
	        },
		});
	</script>
</body>

<!-- :style会自动侦测兼容性，并向CSS属性添加浏览器引擎前缀 -->
```
##### - 数组语法：将多个样式对象应用到同一个元素上
Step1 `:style="[ObjName1, ObjName2]"` / `:style="[ObjName2, condName ? ObjName2 :'']"`
Step2 `ObjName1: {styleName: value}, ObjName2: {styleName: value}` / `ObjName1: {styleName: value}, ObjName2: {styleName: value}, condName: true|false`
```html
<body>
	<div id="example">
		<div :style="[baseStyles, addStyles]">数组语法1（必须共存）</div>
		<!-- 如果想根据条件切换列表中的style，可以用三元表达式 -->
		<div :style="[baseStyles, isAdd ? addStyles :'']">数组语法2（可选共存）</div>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
	        data: {
	            baseStyles: {
	                color: 'blue',
	                fontSize: '20px',
	            },
	            addStyles: {
	                lineHeight: 1,
	                textShadow: '1px 1px 3px grey',
	            },
	            isAdd: false,
	        },
		});
	</script>
</body>

<!-- :style会自动侦测兼容性，并向CSS属性添加浏览器引擎前缀 -->
```
##### - 多重值：提供多个带浏览器前缀的值
`:style="{styleName: ['-preName1-value1', '-preName2-value2', ……, 'value3']}"`
```html
<body>
	<div id="example">
		<div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">……</div>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
		});
	</script>
</body>

<!-- 如果浏览器兼容性允许，那么就只会渲染最后一个不带前缀的值 -->
```
<br/>
### 2、`v-for`：列表循环
#### • 数组：绑定数据到数组来渲染一个列表
Step1 `v-for="itemName in|for arrName"` / `v-for="(itemName, index) in|for arrName"`
Step2 `{{ itemName.keyName }}` `{{ index }}`
Step3 `arrName: [{ keyName: value1 }, { keyName: value2 }, ……],`
```html
<body>
	<ul id="example">
		<li v-for="item in list">
		    <!-- v-for下的其他语句将在列表各项重复输出 -->
		    {{ message }} {{ item.name }}
		</li>
	</ul>
	<ol id="twoParms">
	    <!-- 支持可选的第二参数index来输出数组中各项的索引 -->
		<li v-for="(item, index) in list">
			{{ item.name }} —— 此项索引为{{ index }}
		</li>
	</ol>

	<script type="text/javascript">
	    var listInfo = {
	        message: "君の名は？",
			list: [
			    //数组中各列表项的键名必须相同，默认只输出键值
			    { name: 'Li Lei' },
				{ name: 'Han Meimei' },
				{ name: 'Wang Xiaoming' }
			],
	    };
		new Vue({
			el: '#example',
			data: listInfo,
		});
		new Vue({
			el: '#twoParms',
			data: listInfo,
		});
	</script>
</body>

<!-- v-for同样适用于自定义组件，同时:key是必须的 -->
```
![此处输入图片的描述][13]
##### - `:key`：跟踪每个节点的身份，从而重用和重新排序现有元素
Step1 给数组中每项数据标记一个唯一的id：`{id: idNumber, keyName: value}`
Step2 在v-for后用v-bind绑定一个key属性，id作为值：`:key="itemName.id"`
```html
<body>
	<ul id="example">
		<li v-for="item in list" :key="item.id">
		    {{ item.name }}
		</li>
	</ul>

	<script type="text/javascript">
		var vm = new Vue({
			el: '#example',
			data: {
				list: [
				{
					id: 1,
					name: 'Li Lei'
				},
				{
					id: 2,
					name: 'Han Meimei'
				},
				{
					id: 3,
					name: 'Wang Xiaoming'
				}
				],
			},
		});
	</script>
</body>

<!-- 作为Vue识别节点的一个通用机制，key并不与v-for特别关联 -->
```
##### - 过滤/排序：显示一个数组的过滤或排序副本，而不改变原始数据
Step1 `v-for="n in exprName"` / `v-for="n in methName(parmName)"`
Step2 `{{ n }}`
Step3 `computed: {exprName: function() {……}}` / `methods: {methName: function(parmName) {……}}`
```html
<body>
	<ul id="nInComp">
		<li v-for="n in compNumbers">{{ n }}</li>
	</ul>
	<ul id="nInMeth">
		<li v-for="n in meth(numbers)">{{ n }}</li>
	</ul>

	<script type="text/javascript">
	    var numList = {
	        numbers: [ 1, 2, 3, 4, 5 ]
	    };
		new Vue({
			el: '#nInComp',
			data: numList,
			//创建返回过滤或排序数组的计算属性
			computed: {
			    compNumbers: function () {
			        return this.numbers.filter(function(number){
			            return number % 2 === 0
			        })
			    }
            }
		});
		new Vue({
			el: '#nInMeth',
			data: numList,
			//在计算属性不适用的情况下，可以使用一个 method 方法
			methods: {
                meth: function (numbers) {
                    return numbers.filter(function (number) {
                        return number % 2 === 0
                    })
                }
            }
		});
	</script>
</body>
```
![此处输入图片的描述][14]
#### • 对象：通过一个对象的属性来迭代
Step1 `v-for="itemName in objName"` / `v-for="(itemName, key) in objName"` / `v-for="(itemName, key, index) in objName"`
Step2 `{{ itemName }}` `{{ key }}` `{{ index }}`
Step3 `objName: { keyName1: value, keyName2: value, …… },`
```html
<body>
    <ul id="example">
		<li v-for="item in list">
		    <!-- 插值只填写itemName，默认只输出对象中各项的键值 -->
		    {{ item }}
		</li>
	</ul>
	<ul id="twoParms">
	    <!-- 支持可选的第二参数key来输出对象中各项的键名 -->
		<li v-for="(item, key) in list">
		    {{ key }} : {{ item }}
		</li>
	</ul>
	<ol id="threeParms">
	    <!-- 还可添加第三个参数index来输出索引 -->
		<li v-for="(item, key, index) in list">
		    {{ key }} : {{ item }} [{{ index }}]
		</li>
	</ol>

	<script type="text/javascript">
	    var listInfo = {
	        list: {
				//对象中各项键名必须不同，默认只输出键值
				name: 'Li Lei',
				gender: 'Female',
				age: '25'
			},
	    };
	    new Vue({
			el: '#example',
			data: listInfo,
		});
		new Vue({
			el: '#twoParms',
			data: listInfo,
		});
		new Vue({
			el: '#threeParms',
			data: listInfo,
		});
	</script>
</body>
```
![此处输入图片的描述][15]
#### • 取整：在指定的范围内取整数，将重复多次模板
Step1 `v-for="n in rangeNumber"`
Step2 `{{ n }}`
```html
<body>
	<div id="example">
		<span v-for="n in 10">{{ n }} </span>
	</div>
	
	<script type="text/javascript">
		new Vue({
	        el: '#example',
		});
	</script>
</body>
```
![此处输入图片的描述][16]
#### • `template`：要循环多个元素，可包裹在一个不可见的template元素内
`<template v-for="itemName in|for arrName">……</template>`
/ `<template v-for="itemName in objName">……</template>`
```html
<body>
	<ul id="example">
	    <!-- 最终的渲染结果将不包含template元素 -->
	    <template v-for="item in list">
	        <li>{{ item.name }}</li>
	        <li class="divider"></li>
	    </template>
	</ul>
	
	<script type="text/javascript">
		new Vue({
			el: '#example',
			data: {
			    list: [
				    { name: 'Li Lei' },
				    { name: 'Han Meimei' },
				    { name: 'Wang Xiaoming' }
			    ],
			},
		});
	</script>
</body>
```
![此处输入图片的描述][17]
#### • 搭配v-if：同一节点优先级v-for＞v-if，v-if重复在每个v-for循环中
Step1 `v-for="itemName in|for arrName" v-if="condName"`
Step2 `{{ itemName.keyName }}`
Step3 `arrName: [{keyName: value1, condName: true|false}, {keyName: value2, condName: true|false}, ……],`
```html
<body>
    <div id="apple">
		<div v-for="letter in letters" v-if="!letter.isRead">
			<h1>第{{ letter.id }}封信未读！</h1>
		</div>
	</div>
	<!-- 若想有条件地跳过循环，可将v-if置于父元素（或template） -->
	<div id="orange">
        <ul v-if="todos.length">
            <li v-for="todo in todos">
                {{ todo.item }}
            </li>
        </ul>
        <h1 v-else>No todos left!</h1>
    </div>

	<script type="text/javascript">
		new Vue({
			el: '#apple',
			data: {
				letters: [
				{
					id: 1,
					isRead: true,
				},
				{
					id: 2,
					isRead: false,
				},
				{
					id: 3,
					isRead: true,
				},
				],
			},
		});
		new Vue({
			el: '#orange',
			data: {
				todos: [],
			},
		});
	</script>
</body>
```
![此处输入图片的描述][18]
#### • 更新检测数据的Console方法
##### - 变异方法：观察数组，操作方法将会触发视图更新，会改变原始数组
`varName.arrName.pop()` 删除数组的最后一个元素，并返回删除的元素
`varName.arrName.push()` 向数组的末尾添加元素，并返回新的长度
`varName.arrName.shift()` 删除数组的第一个元素，并返回删除的元素
`varName.arrName.unshift()` 向数组的开头添加元素，并返回新的长度
`varName.arrName.splice()` 插入、删除或替换数组的元素
`varName.arrName.sort()` 对数组的元素进行排序
`varName.arrName.reverse()` 颠倒数组中元素的顺序
```javascript
> vm.list.pop({ name: 'Wang Xiaoming' })
< {__ob__: Observer}

> vm.list.push({ name: 'Li Xiuli' })
< 3

> vm.list.shift({ name: 'Li Lei' })
< {__ob__: Observer}

> vm.list.unshift({ name: 'Li Xiaolang' })
< 3

> vm.list.splice(1,0,{ name: 'Wang San' })
< []

> vm.list.sort()
< (4) [{…}, {…}, {…}, {…}, __ob__: Observer]

> vm.list.reverse()
< (4) [{…}, {…}, {…}, {…}, __ob__: Observer]
```
##### - 替换数组：不会改变原始数组，但总是返回一个新数组，可以替换旧数组
`varName.arrName = varName.arrName.filter()` 创建一个新的数组
`varName.arrName = varName.arrName.concat()` 连接两个或多个数组
`varName.arrName = varName.arrName.slice()` 从已有的数组中返回选定的元素
```javascript
> vm.list = vm.list.filter(function (item) {
      return item.name.match(/Han Meimei/)
  })
< [{…}, __ob__: Observer]

> vm.list = vm.list.concat({ name: 'Li Li' })
< (2) [{…}, {…}, __ob__: Observer]

> vm.list = vm.list.slice(1)
< [{…}, __ob__: Observer]
```
##### - 注意事项：Vue不能检测某些变动的数组，可以改用其他方法
① 利用索引直接设置一个项：
`Vue.set(varName.arrName, indexNumber, newItem)`
/ `varName.$set(varName.arrName, indexNumber, newItem)`
/ `varName.arrName.splice(indexNumber, 1, newItem)`
② 修改数组的长度：
`varName.arrName.splice(newLength)`
③ 向对象添加一个新属性：
`Vue.set(varName.objName, 'keyName', value)`
/ `varName.$set(varName.objName, 'keyName', value)`
④ 向对象添加多个新属性：
`varName.objName = Object.assign({}, varName.objName, { keyName1: value, keyName2: value, …… })`
```javascript
> Vue.set(vm.list, 1, { name: 'Li Xiaolang' })
< {__ob__: Observer}

> vm.$set(vm.list, 0, { name: 'Li Li' })
< {__ob__: Observer}

> vm.list.splice(2, 1, { name: 'Wang San' })
< [{…}]

> vm.list.splice(2)
< [{…}]

> Vue.set(vm.list, 'city', 'Beijing')
< "Beijing"

> vm.$set(vm.list, 'job', 'Programmer')
< "Programmer"

> vm.list = Object.assign({}, vm.list, { email: 'lilei@qq.com',   phone: 1234567890 })
< {…}
```
<br/>
### 2、`v-html`：输出解析后的html，替换标签的内容
Step1 `v-html="keyName"`
Step2 `keyName: '……'`
```html
<body>
	<div id="apple">
		<h1>{{ htmlA }}</h1>
		<h1 v-html="htmlB">此内容不显示</h1>   ——输出"sometext"
	</div>
	
	<script type="text/javascript">
		var dat = {
			htmlA: "<p>sometext</p>",
			htmlB: '<p>sometext</p>',
		};
		new Vue({
			el: '#apple',
			data: dat,
		});
	</script>
</body>
```
![效果示例][19]
<br/>
### 3、`v-if`：表达式的值为true时渲染元素，false时不显示元素
Step1 `v-if="keyName"`
Step2 `keyName: true|false`
```html
<body>
	<div id="example">
		<h1 v-if="ifA">若ifA为true，则渲染此元素，否则不显示</h1>
		<p v-if="ifB">若ifB为true，则渲染此元素，否则不显示</p>
	</div>
	
	<script type="text/javascript">
		new Vue({
			el: '#example',
			data: {
			    ifA: true,   //渲染元素
			    ifB: false,   //不显示
			},
		});
	</script>
</body>
```
![效果示例][20]
#### • `template`：要切换多个元素，可包裹在一个不可见的template元素内
`<template v-if="keyName">……</template>`
```html
<body>
	<div id="example">
	    <!-- 最终的渲染结果将不包含template元素 -->
		<template v-if="ifTemp">
		    <h1>薛定谔的标题</h1>
            <p>薛定谔的文本</p>
        </template>
	</div>
	
	<script type="text/javascript">
		new Vue({
			el: '#example',
			data: {
			    ifTemp: true,   //渲染template内的元素组
			},
		});
	</script>
</body>
```
![此处输入图片的描述][21]
#### • `v-else`：若v-if指令的值为false，则渲染v-else的元素
Step1 `v-if="keyName"` `v-else`
Step2 `keyName: true|false`
```html
<body>
	<div id="example">
		<h1 v-if="ifTrue">若ifTrue为true，则此元素被渲染</h1>
		<!-- v-else元素必须紧跟在带v-if/v-else-if的元素后 -->
		<p v-else>若ifTrue为false，则此元素被渲染</p>
	</div>
	
	<script type="text/javascript">
		var bool = {
		    ifTrue: false,
		};
		new Vue({
			el: '#example',
			data: bool,
		});
	</script>
</body>
```
![此处输入图片的描述][22]
#### • `v-else-if`：若v-if指令的值为false，则渲染v-else的元素，可多个
Step1 `v-if="keyName1"` `v-else-if="keyName2"` `v-else`
Step2 `keyName1: true|false,` `keyName2: true|false`
```html
<body>
	<div id="example">
		<h1 v-if="ifA">若ifA为true，则只渲染此元素</h1>
		<!-- v-else-if元素必须紧跟在带v-if/v-else-if的元素后 -->
		<h3 v-else-if="ifB">若ifA为false且ifB为true，则只渲染此元素</h3>
		<p v-else>若ifA和ifB都为false，则只渲染此元素</p>
	</div>
	
	<script type="text/javascript">
		var bool = {
		    ifA: false,
		    ifB: true,
		};
		new Vue({
			el: '#example',
			data: bool,
		});
	</script>
</body>
```
![此处输入图片的描述][23]
#### • `key`：在多个相同类型的元素间切换时，使他们相互独立，避免复用
Step1 `v-if="keyName"` `key="keyword1"` `v-else` `key="keyword2"`
Step2 `keyName: true|false,`
```html
<!-- 切换v-if将不会清除已输入的内容，因为两个模板使用了相同的元素 -->
<template v-if="loginType === 'username'">
	<label>Username</label>
	<input placeholder="Enter your username">
</template>
<template v-else>
    <label>Email</label>
	<input placeholder="Enter your email address">
</template>
```
![此处输入图片的描述][24]
```html
<!-- 向被复用的元素添加一个具有唯一值的key属性，即可重新渲染 -->
<template v-if="loginType === 'username'">
	<label>Username</label>
	<input placeholder="Enter your username" key="username-input">
</template>
<template v-else>
    <label>Email</label>
	<input placeholder="Enter your email address" key="email-input">
</template>
```
![此处输入图片的描述][25]
<br/>
### 4、`v-model`：在表单元素上创建双向数据绑定，实时更新数据
Step1 `v-model="keyName"`
Step2 `{{ keyName }}`
Step3 `keyName: '……'`
```html
<body>
	<div id="apple">
		<input type="text" v-model="modText">
		<p>正在输入：{{ modText }}</p>
	</div>
	
	<script type="text/javascript">
		var dat = {
		    modText: "请输入内容……",
		};
		new Vue({
		    el: '#apple',
		    data: dat,
		});
	</script>
</body>

<!-- v-model指令会忽略表单元素的value、checked、selected属性 -->
```
![效果示例][26]
<br/>
### 5、`v-on:eventName` / `@eventName`：绑定事件监听器，触发JS代码
>**※** eventName：DOM事件属性名去掉on前缀
#### • 事件表达式：在表达式中运行简单的JavaScript代码
`@eventName="expression"`
```html
<body>
	<div id="apple">
		<button @click="counter+=1">点我+1</button>
		{{ counter }}
		<br/>		
		<button @click="string+=1">点我+'1'</button>
		{{ string }}
	</div>
	
	<script type="text/javascript">
		var dat = {
	        counter: 1,   //参与递增计数
	        string: '1',   //只输出字符串
        };
        new Vue({
	        el: '#apple',
	        data: dat,
        });
	</script>
</body>
```
![效果示例][27]

#### • 事件处理方法：绑定一个需要调用的方法名称
Step1 `@eventName="methName"` / `v-on="{eventName: methName}"`
Step2 `methName: function() {……}`
```html
<body>
	<div class="apple">
		<p v-if="ifShow">这是一段被显示的文本</p>
		<button @click="onClick">点我隐藏文本</button>
		<br/>
		<br/>
		<button id="pear" v-on="{mouseenter:onEnter, mouseleave:onLeave}" @click="onClickA">点我弹窗</button>
	</div>
	
	<script type="text/javascript">
		var dat = {
	        ifShow: true,   //条件为true时文本被显示
        };
        var meth = {
	        onClick: function(){
		        this.ifShow=false;   //点击后ifShow属性值变为false
	        },
	        onEnter: function(){
		        document.getElementById('pear').style.fontWeight="bold";   //鼠标进入时元素的字体变粗
	        },
	        onLeave: function(){
		        document.getElementById('pear').style.fontWeight="normal";   //鼠标离开时元素的字体恢复正常
	        },
	        onClickA: function(){
		        alert("点击成功！");   //点击后弹窗提醒
	        },
        };
        new Vue({
	        el: '.apple',
	        data: dat,
	        methods: meth,
        });
	</script>
</body>
```
![效果示例][28]

#### • 内联处理器中的方法：在内联JavaScript语句中调用方法
Step1 `@eventName="methName(……)"`
Step2 `methName: function(p){……}`
```html
<body>
	<div id="apple">
		<button @click="onClick('一个弹窗')">点我</button>
		<button @click="onClick('另一个弹窗')">再点我</button>
	</div>

	<script type="text/javascript">
	    var meth = {
	        onClick: function(p){
		        alert(p);          //参数p可在多个表达式内赋值
	        },
        };
        new Vue({
	        el: '#apple',
	        methods: meth,
        });
	</script>
</body>
```
![效果示例][29]

#### • 事件修饰符
`.stop` &nbsp;阻止事件继续传播（发生到此元素为止）
`.prevent` &nbsp;取消事件的默认动作（例如使a元素点击链接时不跳转）
`.capture` &nbsp;在捕获阶段处理事件（从最外层元素开始向此元素发生）
`.self` &nbsp;仅当由此元素触发事件时才处理（而不由子元素冒泡）
`.once` &nbsp;事件只能被触发一次（处理一次后自动移除事件）
`.passive` &nbsp;立即触发事件的默认动作（不必耗时等待处理器）
```html
<a @click.stop="doThis">单个修饰符表达式</a>

<a @click.stop.prevent="doThat">修饰符可以串联</a>
<!-- 修饰符串联的前后顺序很重要，事件会从左到右依次处理 -->

<form @submit.prevent>也可以只有修饰符</form>

<div @scroll.passive="onScroll">提升移动端性能</div>
<!-- .passive和.prevent不能一起使用，因为.prevent将会被忽略 -->
```

#### • 按键修饰符
##### - 常用按键别名：`.enter` `.tab` `.delete` `.esc` `.space` `.up` `.down` `.left` `.right`
```html
<input @keypress.13="submit">
<!-- 函数仅在键值是 13 时调用 -->

<input @keydown.enter="submit">
<!-- 函数仅在按键 enter 时调用 -->

<!-- 打印键，建议使用keypress事件；功能键，可使用keydown或keyup -->
```
##### - 自定义按键修饰符别名：`Vue.config.keyCodes.keyName`
```html
<body>
	<div id="apple">
		<input type="text" @keyup.f1="message">
	</div>

	<script type="text/javascript">
	    //自定义键值为112的按键别名为f1
	    Vue.config.keyCodes.f1 = 112;
        new Vue({
	        el: '#apple',
	        data: {
	            message: '……',
	        },
        });
	</script>
</body>
```
```html
<body>
	<div id="apple">
		<input type="text" @keyup.media-play-pause="method">
		<!-- HTML不区分大小写，需用全小写/短横线命名才能匹配数据 -->
	</div>

	<script type="text/javascript">
	    Vue.config.keyCodes = {
            f1: 112,
            //自定义键值为179的按键别名为media-play-pause
            mediaPlayPause: 179,   //键名需转换为驼峰式命名
            "media-play-pause": 179,   //但字符串中支持短横线命名
            up: [38, 87]
        };
        new Vue({
	        el: '#apple',
	        methods: {
	            method: function(){……},
	        },
        });
	</script>
</body>

<!-- 全局字符串下区分大小写，不受命名法转换的限制 -->
```
##### - 自动匹配按键修饰符：将 [*KeyboardEvent.key*][30] 中任意有效按键名转换为kebab-case来作为修饰符
```html
<input @keyup.page-down="onPageDown">
<!-- 函数仅在 $event.key === 'PageDown' 时被调用 -->
```
#### • 系统修饰符
##### - 仅在按住相应键时才触发事件监听器：`.ctrl` `.alt` `.shift` `.meta` `.exact`
```html
<input @keyup.alt.67="clear">
<!-- 按住 Alt 后再按 C -->

<div @click.ctrl="doSomething">Do something</div>
<!-- 按住 Ctrl 后再单击 -->

<button @click.ctrl.exact="onCtrlClick">A</button>
<!-- 有且只有 Ctrl 被按住的时候才触发 -->

<button @click.exact="onClick">A</button>
<!-- 仅当没有任何系统修饰符被按住的时候才触发 -->
```
##### - 鼠标按钮修饰符：`.left` `.right` `.middle`
```html
<button @click.left="onLeftClick">A</button>
<!-- 点击鼠标左键时触发事件 -->
 
<div @click.right="onClick" oncontextmenu="return false">A</div>
<!-- 点击鼠标右键时触发事件，并阻止默认右键菜单 -->

<div @click.middle="onMiddle">A</div>
<!-- 点击鼠标滚轮时触发事件 -->
```
<br/>
### 6、`v-show`：切换元素的display属性，true可见，false不可见
Step1 `v-show="keyName"`
Step2 `keyName: true|false`
```html
<body>
	<div id="example">
	    <!-- v-show元素始终会被渲染，不支持template和v-else -->
		<h1 v-show="showA">若showA为true，此元素可见</h1>
		<p v-show="showB">若showB为false，则此元素不显示</p>
	</div>
	
	<script type="text/javascript">
		var bool = {
			showA: true,   //显示元素
			showB: false,   //不显示
		};
		new Vue({
			el: '#example',
			data: bool,
		});
	</script>
</body>

<!-- 若需要频繁切换，建议使用v-show；若条件很少改变，建议使用v-if -->
```

---

## 组件
组件是可复用的Vue实例，且带有一个名字；用独立可复用的小组件来构建大型应用，几乎任意类型的应用都可以抽象为一个组件树：
![组件][31]

### 1、组件注册
#### • 全局组件：可以用在任何新创建的根实例的模板中，在各自内部也都可以相互使用
Step1 构造并注册全局组件：`Vue.component('tag-name', {……});`
Step2 创建根实例：`new Vue({el: '#……'});`
Step3 调用组件：`<tag-name></tag-name>`
```html
<!-- 在HTML中调用组件，可复用多次，互不影响 -->
<div id="example">
    <tag-name></tag-name>
    <tag-name></tag-name>
</div>
<!-- 可应用于多个实例 -->
<div id="example2">
    <tag-name></tag-name>
</div>
```
```javascript
//在JS中构造组件，注册为全局组件
Vue.component('tag-name', {
    //组件的data选项必须是一个函数，否则会影响到其它所有实例
    data() {
        return {
            keyName1: value1,
            keyName2: value2,
            ……
        }
    },
    //组件的内容模板，书写HTML表达式
    template: '……'
});
//创建根实例，在挂载的元素范围内使用组件
new Vue({
    el: '#example'
});
new Vue({
    el: '#example2'
})
```
<br/>
#### • 局部组件：只能用在注册的根实例的模板中，且在其子组件中不可用
Step1 构造组件：`var varName = {……};`
Step2 注册局部组件：`new Vue({el: '#……', components: {'tag-name': varName})`
Step3 调用组件：`<tag-name></tag-name>`
```html
<!-- 仅可在挂载的根实例中调用组件 -->
<div id="example">
    <tag-name></tag-name>
</div>
<div id="example2">
    <!-- ×不能应用于其它根实例，浏览器报错 -->
    <tag-name></tag-name>
</div>
```
```javascript
//在JS中构造组件
var myTag = {
    data() {
        return {
            keyName1: value1,
            keyName2: value2,
            ……
        }
    },
    template: '……'
};
new Vue({
    el: '#example',
    //在根实例的components选项中注册为局部组件
    components: {
        'tag-name': myTag
    }
});
new Vue({
    el: '#example2'
})
```

<br/>
### 2、Prop
#### • `props`：自定义组件的属性，通过props传递数据
Step1 定义特性：`props: ['propName1', 'propName2', ……]`
Step2 传递数据：`<tag-name prop-name="……"></tag-name>`
```html
<div id="example">
    <!-- HTML大小写不敏感，所以 camelCase 命名的 prop 需使用其等价的 kebab-case 命名 -->
	<tag-name prop-a="valueA" prop-b="valueB"></tag-name>
	<!-- 可以通过 v-bind 动态赋予一个变量的值 -->
	<tag-name :prop-c="keyName"></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //用一个 props 选项将组件的属性包含在 prop 列表中
    props: ['propA', 'propB', 'propC'],
    //多行模板须包裹在一个父元素中，并在模板字符串`……`内书写
    template: `
        <div>
            <p>属性1：{{ propA }}</p>
            <p>属性2：{{ propB }}</p>
            <p>属性3：{{ propC }}</p>
        </div>
    `
});
new Vue({
    el: '#example',
    data: {
        keyName: 'valueC'
    }
})

//如果包裹在字符串'……'中，那么就不受命名法转换的限制
```
<br/>
#### • 组件v-for：使用 v-bind 来动态传递 prop
```html
<div id="example">
    <!-- 使用一个 v-bind 绑定 prop 参数，传入所有列表数据 -->
	<tag-name v-for="item in items" :key="item.id" :item="item"></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //只需定义一个prop
    props: ['item'],
    template: `……`
});
new Vue({
    el: '#example',
    data: {
        items: [
        { 
            id: 1,
            keyName1: '……',
            keyName2: '……',
            ……
        },
        { 
            id: 2,
            keyName1: '……',
            keyName2: '……',
            ……
        },
        ……
        ]
    }
})
```
<br/>
#### • Prop类型：以对象形式列出每项 prop 指定的名称和类型
```html
<div id="example">
    <!-- 需使用 v-bind 来表明这是 JavaScript 表达式而不是字符串 -->
	<tag-name :prop-b="42"></tag-name>
	<tag-name :prop-c="false"></tag-name>
	<tag-name :prop-d="[234, 266, 273]"></tag-name>
	<tag-name :prop-e="{name: 'Shaw', age: '26'}"></tag-name>
	<!-- 使用不带参数的 v-bind 将一个对象的所有属性都传入 -->
	<tag-name v-bind="objectE"></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    props: {
        propA: String,
        propB: Number,
        propC: Boolean,
        propD: Array,
        propE: Object,
        propF: Function,
        propG: Promise
    },
    template: `……`
});
new Vue({
    el: '#example',
    data: {
        objectE: {
            id: 1,
            name: 'Shaw',
            age: '26'
        }
    }
})

//不仅为组件提供了文档，还会在遇到错误的类型时从浏览器的控制台提示用户
```

<br/>
### 3、自定义事件
#### • 监听子组件事件：父级组件可以通过 v-on 监听子组件的任意事件
```html
<div id="example">
	<tag-name @eventName="count += 1"></tag-name>
	<!-- 通过 $event 访问 $emit 第二个参数提供的值 -->
	<tag-name @eventName="count += $event"></tag-name>
	<!-- 这个事件处理函数也可以是一个方法 -->
	<tag-name @eventName="methName"></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    props: ……,
    //子组件可以通过调用内建的 $emit 方法传入事件名称来触发一个事件
    template: `
        <div>
            <button @click="$emit('eventName')">点击这个按钮会触发eventName事件</button>
            <button @click="$emit('eventName', 1)">使用 $emit 的第二个参数来提供一个特定的值</button>
        </div>
    `
});
new Vue({
    el: '#example',
    data: {
        count: 0
    },
    methods: {
        //$emit 提供的这个值将会作为方法的第一个参数传入
        methName: function (p) {
            this.count += p
        }
    }
})
```
<br/>
#### • 组件v-model：创建支持 v-model 的自定义输入组件
```html
<div id="example">
	<tag-name v-model="……"></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //将其 value 特性绑定到一个名叫 value 的 prop 上
    props: ['value'],
    //在其 input 事件被触发时，将新的值通过自定义的 input 事件抛出
    template: `
        <input :value="value" @input="$emit('input', $event.target.value)">
    `
});
new Vue({
    el: '#example'
})
```

<br/>
### 4、插槽
#### • 插槽内容：将 slot 元素作为承载分发内容的出口
Step1 向模板添加slot：`<slot></slot>`
Step2 向组件添加内容：`<tag-name>……</tag-name>`
```html
<div id="example">
    <!-- 未添加内容的组件将显示原本的模板内容 -->
	<tag-name></tag-name>
	<!-- 添加的内容将替换模板中的slot位置显示 -->
	<tag-name>
	    <a href="#">这是组件添加的内容，会替换模板中的slot</a>
	</tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //在模板中待替换的位置添加slot元素
    template: `
        <div>
            <span>这是模板中原本的内容</span>
            <slot></slot>
        </div>
    `
});
new Vue({
    el: '#example'
})

//父级模板里的所有内容都是在父级作用域中编译的，子模板里的所有内容都是在子作用域中编译的
```
![此处输入图片的描述][35]
<br>
#### • 后备内容：为插槽设置默认内容，它只在组件没有提供内容时被渲染
```html
<div id="example">
    <!-- 未添加内容的组件将渲染后备内容 -->
	<tag-name></tag-name>
	<!-- 添加的内容将替换掉模板中的slot -->
	<tag-name><a href="#">这是组件添加的内容1</a></tag-name>
	<tag-name><a href="#">这是组件添加的内容2</a></tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //在slot中设置后备内容
    template: `
        <div>
            <span>这是模板中原本的内容</span>
            <slot><a href="#">这是slot中的后备内容</a></slot>
        </div>
    `
});
new Vue({
    el: '#example'
})
```
![此处输入图片的描述][36]
<br>
#### • 具名插槽：定义额外的插槽
Step1 定义具名插槽：`<slot name="slotName"></slot>`
Step2 向具名插槽提供内容：`<template v-slot:slotName>……</template>`
```html
<div id="example">
    <tag-name>
	    <!-- 在template元素上使用v-slot指令，向具名插槽提供内容 -->
	    <template v-slot:header>
	        <h1>这是替换header插槽的内容</h1>
        </template>
	    <!-- 所有没被包裹在v-slot中的内容都会提供给默认插槽 -->
	    <p>这是替换默认插槽的内容</p>
	    <template v-slot:footer>
	        <h5>这是替换footer插槽的内容</h5>
	    </template>
    </tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //向额外的插槽添加name属性
    template: `
        <div>
            <header>
                <slot name="header"></slot>
            </header>
            <main>
                <slot></slot>
            </main>
            <footer>
                <slot name="footer"></slot>
            </footer>
        </div>
    `
});
new Vue({
    el: '#example'
})
```
![此处输入图片的描述][37]
<br>
#### • 作用域插槽：让插槽内容能够访问子组件中才有的数据
```html
<div id="example">
    <!-- 若只有一个默认插槽，可直接在组件上使用 v-slot 来定义插槽 prop 的名字 -->
    <tag-name v-slot="slotProps">{{ slotProps.user.firstName }}</tag-name>
    <!-- 若有多个插槽，需使用完整的基于 template 的语法 -->
    <tag-name>
        <template v-slot:default="slotProps">{{ slotProps.user.firstName }}</template>
        <template v-slot:footer="footerProps">{{ footerProps.user.middleName }}</template>
    </tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //将 user 作为一个 slot 元素的特性绑定上去，称为插槽 prop
    template: `
        <div>
            <main>
                <slot :user="user">{{ user.lastName }}</slot>
            </main>
            <footer>
                <slot name="footer" :user="user">{{ user.lastName }}</slot>
            </footer>
        </div>
    `
});
new Vue({
    el: '#example',
    data: {
        user: { 
            firstName: '……',
            middleName: '……',
            lastName: '……',
            ……
        }
    }
})
```

<br>
### 5、动态组件
#### • `:is="……"`：在不同组件之间进行动态切换
Step1 绑定插槽prop：`<slot v-bind:dataName="dataName">{{ …… }}</slot>`
Step2 给插槽prop赋值：`<template v-slot:default="slotProps">{{ slotProps.…… }}</template>`
```html
<div id="example">
    <!-- 在一个template元素上使用v-slot指令，向具名插槽提供内容 -->
    <tag-name v-slot="slotProps">{{ slotProps.user.firstName }}</tag-name>
</div>
```
```javascript
Vue.component('tag-name', {
    //向额外的插槽添加name属性
    template: `
        <span>
            <slot v-bind:user="user">{{ user.lastName }}</slot>
        </span>
    `
});
new Vue({
    el: '#example'
})
```

---

## 工具
### 1、单文件组件：文件扩展名为 *.vue 的单文件组件

---

  [1]: https://vuejs.org/v2/guide/installation.html
  [2]: https://cdn.jsdelivr.net/npm/vue@2.5.17/dist/vue.js
  [3]: https://cdn.bootcss.com/vue/2.4.2/vue.min.js
  [4]: https://unpkg.com/vue@2.5.17/dist/vue.js
  [5]: https://cdnjs.cloudflare.com/ajax/libs/vue/2.1.8/vue.min.js
  [6]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw3mucu01gj20o50bj74q.jpg
  [7]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw4o3pdu08j20o40aat90.jpg
  [8]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw63us0jhlj20o704saa0.jpg
  [9]: https://wx2.sinaimg.cn/mw690/7de6638dly1fw5r7thgkaj20o4040t8j.jpg
  [10]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwisqplrk8j20sx08hjrp.jpg
  [11]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwsho36r4sj20p104rq3c.jpg
  [12]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw4yfvjkz5j20uj053wf5.jpg
  [13]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwvwxg7ui7j20mr06imxr.jpg
  [14]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwvx6tmv9dj20ms04et8i.jpg
  [15]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwvxnc1mm4j20mo09c3yt.jpg
  [16]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwun7x5v9kj20p600ojr7.jpg
  [17]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwvwr0r7slj20mq05adfs.jpg
  [18]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwwhvq4690j20nn04ajrh.jpg
  [19]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw63wqjsb9j20o704mjrf.jpg
  [20]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwvwa59kvhj20nr03u74g.jpg
  [21]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwvw6pbbysj20nt03naa3.jpg
  [22]: https://wx1.sinaimg.cn/mw690/7de6638dly1fwsk1fx20bj20om0150so.jpg
  [23]: https://wx3.sinaimg.cn/mw690/7de6638dly1fwskdfwf2bj20pa01m3yn.jpg
  [24]: http://wx4.sinaimg.cn/large/7de6638dly1fwskxgf0yrg20ou04amy2.gif
  [25]: http://wx2.sinaimg.cn/large/7de6638dly1fwskzkquofg20ou04aq3n.gif
  [26]: https://wx4.sinaimg.cn/mw690/7de6638dly1fw4r2rscnkg20f00400sv.gif
  [27]: https://wx3.sinaimg.cn/mw690/7de6638dly1fw64fq6uyug20eb03ydgu.gif
  [28]: http://wx4.sinaimg.cn/large/7de6638dly1fw63gobgmmg210a05pdhe.gif
  [29]: http://wx2.sinaimg.cn/large/7de6638dly1fw8qls0qv4g2107041dhb.gif
  [30]: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key/Key_Values
  [31]: https://cn.vuejs.org/images/components.png
  [32]: https://wx2.sinaimg.cn/mw690/7de6638dly1fwe6qal2z5j20ip04jwej.jpg
  [33]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwe4wm8ckcg20bh03xt9e.gif
  [34]: https://wx4.sinaimg.cn/mw690/7de6638dly1fwebunw3t0j20p605vq39.jpg
  [35]: https://wx1.sinaimg.cn/mw1024/7de6638dly1g2eqrfpobcj20o602k3yu.jpg
  [36]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g2er9qsh8lj20o403faaq.jpg
  [37]: https://wx3.sinaimg.cn/mw1024/7de6638dly1g2es35fkjgj20o205ogma.jpg