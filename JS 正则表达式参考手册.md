# JS 正则表达式参考手册
正则表达式 (Regular Expression)：使用单个字符串来描述、匹配一系列符合某个句法规则的字符串搜索模式

---

### 1、语法
```javascript
/RegularExpression/modifier    // modifier：修饰符（可选）
```
<br>
### 2、模式
#### • 普通字符：包括所有大写和小写字母、所有数字、所有标点符号和一些其他符号
```javascript
/\N/    // \N 对前面至少 N 个的匹配结果再引用一次
```
```javascript
/\NNN/    // \NNN 匹配为八进制转义值的3个数字 NNN
```
```javascript
/\cX/    // \cX 匹配由X指明的控制字符（X的值必须为 A-Z 或 a-z 之一）
```
```javascript
/\d/    // \d 匹配一个数字
```
```javascript
/\D/    // \D 匹配一个非数字字符
```
```javascript
/\f/    // \f 匹配一个换页符
```
```javascript
/\n/    // \n 匹配一个换行符
```
```javascript
/\r/    // \r 匹配一个回车符
```
```javascript
/\s/    // \s 匹配任何空白字符（空格、制表符、换页符等）
```
```javascript
/\S/    // \S 匹配任何非空白字符
```
```javascript
/\t/    // \t 匹配一个制表符
```
```javascript
/\v/    // \v 匹配一个垂直制表符
```
```javascript
/\w/    // \w 匹配字母、数字、下划线
```
```javascript
/\W/    // \W 匹配非字母、非数字、非下划线
```
```javascript
/\xNN/    // \xNN 匹配为十六进制转义值的2个数字 NN
```
```javascript
/\uNNNN/    // \uNNNN 匹配以十六进制数 NNNN 规定的 Unicode 字符
```
#### • 特殊字符：一些有特殊含义的字符，需使用\转义来匹配特殊字符本身
```javascript
/\x/    // \ 将特殊字符标记为原义字符/向后引用/八进制转义符
```
```javascript
/./    // . 匹配除换行符之外的任何单字符
```
```javascript
/x|y/    // (|) 匹配 x 或 y 
```
```javascript
/[xyz]/    // [] 匹配方括号内的任意字符
```
```javascript
/[^xyz]/    // [^] 匹配不在方括号内的任意字符
```
```javascript
/[x-y]/    // [-] 匹配指定范围内的任意单个字符
```
```javascript
/[^x-y]/    // [^-] 匹配指定范围外的任意单个字符
```
```javascript
/(pattern)/    // () 标记一个子表达式的开始和结束位置
```
```javascript
/(?:pattern)/    // (?:) 非获取匹配，匹配但不获取结果
```
#### • 限定符：指定正则表达式的一个给定组件必须要出现多少次才能满足匹配
```javascript
/pattern?/    // ? 包含0个/1个指定项（限定符后跟?将匹配限定范围内最少个）
```
```javascript
/pattern+/    // + 包含1个/多个指定项
```
```javascript
/pattern*/    // * 包含0个/1个/多个指定项
```
```javascript
/pattern{N}/    // {N} 包含 N 个指定项
```
```javascript
/pattern{N,}/    // {N,} 包含连续至少 M 个指定项
```
```javascript
/pattern{M,N}/    // {M,N} 包含连续至少 M 个、至多 N 个指定项
```
#### • 定位符：将正则表达式固定到行首或行尾
```javascript
/\b/    // \b 匹配单词边界（空格前后）
```
```javascript
/\B/    // \B 匹配非单词边界
```
```javascript
/^pattern/    // ^ 以指定项为行首
```
```javascript
/pattern$/    // $ 以指定项为行尾
```
```javascript
/(?=pattern)/    // (?=) 非获取匹配，从任何匹配指定项的字符串开始处查找
```
```javascript
/(?!pattern)/    // (?!) 非获取匹配，从任何不匹配指定项的字符串开始处查找
```
```javascript
/(?<=pattern)/    // (?!) 非获取匹配，从任何匹配指定项的字符串结尾处查找
```
```javascript
/(?<!pattern)/    // (?!) 非获取匹配，从任何不匹配指定项的字符串结尾处查找
```
#### • 运算符优先级：相同优先级的从左到右进行运算，不同优先级的运算先高后低

运算符 | 优先级
--- | ---
`\` | 1
`()`  `(?:)`  `(?=)`  `[]` | 2
`*`  `+`  `?`  `{N}`  `{N,}`  `{M,N}` | 3
`^`  `$`  `\……` | 4
`\|` | 5
#### • 字符簇：一个表示所有匹配字符的范围的组合
```javascript
[a-z]    // 匹配所有的小写字母中的单个字符
[A-Z]    // 匹配所有的大写字母中的单个字符
[a-zA-Z]    // 匹配所有的字母中的单个字符
[0-9]    // 匹配所有的数字中的单个字符
[ \f\r\t\n]    // 匹配所有的白字符中的单个字符
^[1-9][0-9]*$    // 匹配所有的正整数 
^\-?[0-9]+$    // 匹配所有的整数 
^[-]?[0-9]+(\.[0-9]+)?$    // 匹配所有的浮点数
```
<br>
### 3、修饰符
```javascript
/RegExp/i    // i：执行对大小写不敏感的匹配
```
```javascript
/RegExp/g    // g：执行全局匹配
```
```javascript
/RegExp/m    // m：执行多行匹配
```
<br>
### 4、相关方法
#### • `exec()`：检索字符串中的正则表达式的匹配（返回匹配值/null）
```javascript
RegExpObject.exec(string)

// *string：要检测的字符串
```

#### • `test()`：检测一个字符串是否匹配某个模式（返回true/false）
```javascript
RegExpObject.test(string)

// *string：要检测的字符串
```

#### • `toString()`：返回正则表达式的字符串值
```javascript
RegExpObject.toString()
```

#### • `match()`：在字符串内检索指定的值，或找到一个或多个正则表达式的匹配
```javascript
stringObject.match(regexp)

// *regexp：规定要匹配的模式的 RegExp 对象
```

#### • `replace()`：在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串
```javascript
stringObject.replace(searchvalue,newvalue)

// *searchvalue：规定子字符串或要替换的模式的 RegExp 对象
// *newvalue：一个字符串值，规定了替换文本或生成替换文本的函数
```

#### • `search()`：检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串
```javascript
stringObject.search(searchvalue)

// *searchvalue：查找的字符串或者正则表达式
```

#### • `split()`：把一个字符串分割成字符串数组
```javascript
stringObject.split(separator,limit)
```
    *separator  字符串或正则表达式，从该参数指定的地方分割 string Object
    *limit  该参数可指定返回的数组的最大长度。如果设置了该参数，返回的子串不会多于这个参数指定的数组。如果没有设置该参数，整个字符串都会被分割，不考虑它的长度
<br>
### 5、相关属性
#### • `constructor`：返回对象的构造函数
```javascript
RegExpObject.constructor
```
#### • `global`：判断正则表达式是否有修饰符 g
```javascript
RegExpObject.global
```
#### • `ignoreCase`：判断正则表达式是否有修饰符 i
```javascript
RegExpObject.ignoreCase
```
#### • `lastIndex`：规定下次匹配的起始位置（g环境下）
```javascript
RegExpObject.lastIndex
```
#### • `multiline`：判断正则表达式是否有修饰符 m
```javascript
RegExpObject.multiline
```
#### • `source`：返回模式匹配所用的文本
```javascript
RegExpObject.source
```

---