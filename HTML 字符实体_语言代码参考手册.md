# HTML 字符实体|语言代码参考手册
Hyper Text Markup Language - 超级文本标记语言

---

## 字符实体
- **字符实体（character entities）**
1、在 HTML 中，某些字符是预留的；
2、在 HTML 中不能使用小于号 `<` 和大于号 `>` ，这是因为浏览器会误认为它们是标签；
3、如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体。

- **不间断空格（non-breaking space）**
1、HTML 中的常用字符实体是不间断空格 `&nbsp;` ；
2、浏览器会截短 HTML 页面中的连续空格，总是只显示一个，如需在页面中增加空格的数量，您需要使用 `&nbsp;` 字符实体。

### HTML ISO-8859-1 参考手册
HTML 4.01 支持 ISO 8859-1 (Latin-1) 字符集，这些符号中的大多数都可以在不进行实体引用的情况下使用，但是实体名称或实体编号为那些不容易通过键盘键入的符号提供了表达的方法：

>**※** 实体名称对大小写敏感
<table>
    <tr style="background: #555555; color: #fff;">
      <th style="text-align:center;">显示</th>
      <th style="text-align:center;">描述</th>
      <th style="text-align:center;">实体名称</th>
      <th style="text-align:center;">实体编号</th>
    </tr>
    <tr>
      <td>&quot;</td>
      <td>quotation mark（双引号）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;quot;</td>
      <td style="color:#00008B;">&amp;#34;</td>
    </tr>
    <tr>
      <td>&amp;</td>
      <td>ampersand（与）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;amp;</td>
      <td style="color:#00008B;">&amp;#38;</td>
    </tr>
    <tr>
      <td>'</td>
      <td>apostrophe（撇号）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;apos;</td>
      <td style="color:#00008B;font-weight:bold;">&amp;#39;</td>
    </tr>
    <tr>
      <td>&lt;</td>
      <td>less-than（小于）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;lt;</td>
      <td style="color:#00008B;">&amp;#60;</td>
    </tr>
    <tr>
      <td>&#62;</td>
      <td>greater-than（大于）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;gt;</td>
      <td style="color:#00008B;">&amp;#62;</td>
    </tr>
    <tr>
      <td>&nbsp;</td>
      <td>non-breaking space（空格）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;nbsp;</td>
      <td style="color:#00008B;">&amp;#160;</td>
    </tr>
    <tr>
      <td>&iexcl;</td>
      <td>inverted exclamation mark（倒置感叹号）</td>
      <td style="color:#00008B;">&amp;iexcl;</td>
      <td style="color:#00008B;">&amp;#161;</td>
    </tr>
    <tr>
      <td>¢</td>
      <td>cent（美分）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;cent;</td>
      <td style="color:#00008B;">&amp;#162;</td>
    </tr>
    <tr>
      <td>£</td>
      <td>pound（英镑）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;pound;</td>
      <td style="color:#00008B;">&amp;#163;</td>
    </tr>
    <tr>
      <td>¤</td>
      <td>currency（货币）</td>
      <td style="color:#00008B;">&amp;curren;</td>
      <td style="color:#00008B;">&amp;#164;</td>
    </tr>
    <tr>
      <td>¥</td>
      <td>yen（日元）/yuan（人民币）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;yen;</td>
      <td style="color:#00008B;">&amp;#165;</td>
    </tr>
    <tr>
      <td>&brvbar;</td>
      <td>broken vertical bar（间断的竖杠）</td>
      <td style="color:#00008B;">&amp;brvbar;</td>
      <td style="color:#00008B;">&amp;#166;</td>
    </tr>
    <tr>
      <td>§</td>
      <td>section（分节符）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;sect;</td>
      <td style="color:#00008B;">&amp;#167;</td>
    </tr>
    <tr>
      <td>¨</td>
      <td>diaeresis（分音符号）</td>
      <td style="color:#00008B;">&amp;uml;</td>
      <td style="color:#00008B;">&amp;#168;</td>
    </tr>
    <tr>
      <td>&copy;</td>
      <td>copyright（版权所有）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;copy;</td>
      <td style="color:#00008B;">&amp;#169;</td>
    </tr>
    <tr>
      <td>ª</td>
      <td>feminine ordinal indicator（阴性序数记号）</td>
      <td style="color:#00008B;">&amp;ordf;</td>
      <td style="color:#00008B;">&amp;#170;</td>
    </tr>
    <tr>
      <td>&laquo;</td>
      <td>left angle quotation mark（左双角引号）</td>
      <td style="color:#00008B;">&amp;laquo;</td>
      <td style="color:#00008B;">&amp;#171;</td>
    </tr>
    <tr>
      <td>¬</td>
      <td>not sign（否定）</td>
      <td style="color:#00008B;">&amp;not;</td>
      <td style="color:#00008B;">&amp;#172;</td>
    </tr>
    <tr>
      <td>­</td>
      <td>soft hyphen（软连字符）</td>
      <td style="color:#00008B;">&amp;shy;</td>
      <td style="color:#00008B;">&amp;#173;</td>
    </tr>
    <tr>
      <td>&#174;</td>
      <td>registered trademark（注册商标）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;reg;</td>
      <td style="color:#00008B;">&amp;#174;</td>
    </tr>
    <tr>
      <td>¯</td>
      <td>macron（长音符号）</td>
      <td style="color:#00008B;">&amp;macr;</td>
      <td style="color:#00008B;">&amp;#175;</td>
    </tr>
    <tr>
      <td>°</td>
      <td>degree（度）</td>
      <td style="color:#00008B;">&amp;deg;</td>
      <td style="color:#00008B;">&amp;#176;</td>
    </tr>
    <tr>
      <td>±</td>
      <td>plus-or-minus（正负号）</td>
      <td style="color:#00008B;">&amp;plusmn;</td>
      <td style="color:#00008B;">&amp;#177;</td>
    </tr>
    <tr>
      <td>²</td>
      <td>superscript 2（上标2）</td>
      <td style="color:#00008B;">&amp;sup2;</td>
      <td style="color:#00008B;">&amp;#178;</td>
    </tr>
    <tr>
      <td>³</td>
      <td>superscript 3（上标3）</td>
      <td style="color:#00008B;">&amp;sup3;</td>
      <td style="color:#00008B;">&amp;#179;</td>
    </tr>
    <tr>
      <td>´</td>
      <td>acute accent（尖音符号）</td>
      <td style="color:#00008B;">&amp;acute;</td>
      <td style="color:#00008B;">&amp;#180;</td>
    </tr>
    <tr>
      <td>µ</td>
      <td>micro（微米）</td>
      <td style="color:#00008B;">&amp;micro;</td>
      <td style="color:#00008B;">&amp;#181;</td>
    </tr>
    <tr>
      <td>¶</td>
      <td>paragraph（分段符号）</td>
      <td style="color:#00008B;">&amp;para;</td>
      <td style="color:#00008B;">&amp;#182;</td>
    </tr>
    <tr>
      <td>·</td>
      <td>middle dot（中间点）</td>
      <td style="color:#00008B;">&amp;middot;</td>
      <td style="color:#00008B;">&amp;#183;</td>
    </tr>
    <tr>
      <td>¸</td>
      <td>cedilla（变音符号）</td>
      <td style="color:#00008B;">&amp;cedil;</td>
      <td style="color:#00008B;">&amp;#184;</td>
    </tr>
    <tr>
      <td>¹</td>
      <td>superscript 1（上标1）</td>
      <td style="color:#00008B;">&amp;sup1;</td>
      <td style="color:#00008B;">&amp;#185;</td>
    </tr>
    <tr>
      <td>º</td>
      <td>masculine ordinal indicator（阳性序数记号）</td>
      <td style="color:#00008B;">&amp;ordm;</td>
      <td style="color:#00008B;">&amp;#186;</td>
    </tr>
    <tr>
      <td>&raquo;</td>
      <td>right angle quotation mark (右双角引号)</td>
      <td style="color:#00008B;">&amp;raquo;</td>
      <td style="color:#00008B;">&amp;#187;</td>
    </tr>
    <tr>
      <td>¼</td>
      <td>fraction 1/4（四分之一）</td>
      <td style="color:#00008B;">&amp;frac14;</td>
      <td style="color:#00008B;">&amp;#188;</td>
    </tr>
    <tr>
      <td>½</td>
      <td>fraction 1/2（二分之一）</td>
      <td style="color:#00008B;">&amp;frac12;</td>
      <td style="color:#00008B;">&amp;#189;</td>
    </tr>
    <tr>
      <td>¾</td>
      <td>fraction 3/4（四分之三）</td>
      <td style="color:#00008B;">&amp;frac34;</td>
      <td style="color:#00008B;">&amp;#190;</td>
    </tr>
    <tr>
      <td>¿</td>
      <td>inverted question mark（倒置问号）</td>
      <td style="color:#00008B;">&amp;iquest;</td>
      <td style="color:#00008B;">&amp;#191;</td>
    </tr>
    <tr>
      <td>&Agrave;</td>
      <td>capital A, grave accent</td>
      <td style="color:#00008B;">&amp;Agrave;</td>
      <td style="color:#00008B;">&amp;#192;</td>
    </tr>
    <tr>
      <td>&Aacute;</td>
      <td>capital A, acute accent</td>
      <td style="color:#00008B;">&amp;Aacute;</td>
      <td style="color:#00008B;">&amp;#193;</td>
    </tr>
    <tr>
      <td>&Acirc;</td>
      <td>capital A, circumflex accent</td>
      <td style="color:#00008B;">&amp;Acirc;</td>
      <td style="color:#00008B;">&amp;#194;</td>
    </tr>
    <tr>
      <td>&Atilde;</td>
      <td>capital A, tilde</td>
      <td style="color:#00008B;">&amp;Atilde;</td>
      <td style="color:#00008B;">&amp;#195;</td>
    </tr>
    <tr>
      <td>&Auml;</td>
      <td>capital A, umlaut mark</td>
      <td style="color:#00008B;">&amp;Auml;</td>
      <td style="color:#00008B;">&amp;#196;</td>
    </tr>
    <tr>
      <td>&Aring;</td>
      <td>capital A, ring</td>
      <td style="color:#00008B;">&amp;Aring;</td>
      <td style="color:#00008B;">&amp;#197;</td>
    </tr>
    <tr>
      <td>&AElig;</td>
      <td>capital AE</td>
      <td style="color:#00008B;">&amp;AElig;</td>
      <td style="color:#00008B;">&amp;#198;</td>
    </tr>
    <tr>
      <td>&Ccedil;</td>
      <td>capital C, cedilla</td>
      <td style="color:#00008B;">&amp;Ccedil;</td>
      <td style="color:#00008B;">&amp;#199;</td>
    </tr>
    <tr>
      <td>&Egrave;</td>
      <td>capital E, grave accent</td>
      <td style="color:#00008B;">&amp;Egrave;</td>
      <td style="color:#00008B;">&amp;#200;</td>
    </tr>
    <tr>
      <td>&Eacute;</td>
      <td>capital E, acute accent</td>
      <td style="color:#00008B;">&amp;Eacute;</td>
      <td style="color:#00008B;">&amp;#201;</td>
    </tr>
    <tr>
      <td>&Ecirc;</td>
      <td>capital E, circumflex accent</td>
      <td style="color:#00008B;">&amp;Ecirc;</td>
      <td style="color:#00008B;">&amp;#202;</td>
    </tr>
    <tr>
      <td>&Euml;</td>
      <td>capital E, umlaut mark</td>
      <td style="color:#00008B;">&amp;Euml;</td>
      <td style="color:#00008B;">&amp;#203;</td>
    </tr>
    <tr>
      <td>&Igrave;</td>
      <td>capital I, grave accent</td>
      <td style="color:#00008B;">&amp;Igrave;</td>
      <td style="color:#00008B;">&amp;#204;</td>
    </tr>
    <tr>
      <td>&Iacute;</td>
      <td>capital I, acute accent</td>
      <td style="color:#00008B;">&amp;Iacute;</td>
      <td style="color:#00008B;">&amp;#205;</td>
    </tr>
    <tr>
      <td>&Icirc;</td>
      <td>capital I, circumflex accent</td>
      <td style="color:#00008B;">&amp;Icirc;</td>
      <td style="color:#00008B;">&amp;#206;</td>
    </tr>
    <tr>
      <td>&Iuml;</td>
      <td>capital I, umlaut mark</td>
      <td style="color:#00008B;">&amp;Iuml;</td>
      <td style="color:#00008B;">&amp;#207;</td>
    </tr>
    <tr>
      <td>&ETH;</td>
      <td>capital ETH, Icelandic</td>
      <td style="color:#00008B;">&amp;ETH;</td>
      <td style="color:#00008B;">&amp;#208;</td>
    </tr>
    <tr>
      <td>&Ntilde;</td>
      <td>capital N, tilde</td>
      <td style="color:#00008B;">&amp;Ntilde;</td>
      <td style="color:#00008B;">&amp;#209;</td>
    </tr>
    <tr>
      <td>&Ograve;</td>
      <td>capital O, grave accent</td>
      <td style="color:#00008B;">&amp;Ograve;</td>
      <td style="color:#00008B;">&amp;#210;</td>
    </tr>
    <tr>
      <td>&Oacute;</td>
      <td>capital O, acute accent</td>
      <td style="color:#00008B;">&amp;Oacute;</td>
      <td style="color:#00008B;">&amp;#211;</td>
    </tr>
    <tr>
      <td>&Ocirc;</td>
      <td>capital O, circumflex accent</td>
      <td style="color:#00008B;">&amp;Ocirc;</td>
      <td style="color:#00008B;">&amp;#212;</td>
    </tr>
    <tr>
      <td>&Otilde;</td>
      <td>capital O, tilde</td>
      <td style="color:#00008B;">&amp;Otilde;</td>
      <td style="color:#00008B;">&amp;#213;</td>
    </tr>
    <tr>
      <td>&Ouml;</td>
      <td>capital O, umlaut mark</td>
      <td style="color:#00008B;">&amp;Ouml;</td>
      <td style="color:#00008B;">&amp;#214;</td>
    </tr>
    <tr>
      <td>×</td>
      <td>multiplication（乘号）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;times;</td>
      <td style="color:#00008B;">&amp;#215;</td>
    </tr>
    <tr>
      <td>&Oslash;</td>
      <td>capital O, slash</td>
      <td style="color:#00008B;">&amp;Oslash;</td>
      <td style="color:#00008B;">&amp;#216;</td>
    </tr>
    <tr>
      <td>Ù</td>
      <td>capital U, grave accent</td>
      <td style="color:#00008B;">&amp;Ugrave;</td>
      <td style="color:#00008B;">&amp;#217;</td>
    </tr>
    <tr>
      <td>Ú</td>
      <td>capital U, acute accent</td>
      <td style="color:#00008B;">&amp;Uacute;</td>
      <td style="color:#00008B;">&amp;#218;</td>
    </tr>
    <tr>
      <td>Û</td>
      <td>capital U, circumflex accent</td>
      <td style="color:#00008B;">&amp;Ucirc;</td>
      <td style="color:#00008B;">&amp;#219;</td>
    </tr>
    <tr>
      <td>Ü</td>
      <td>capital U, umlaut mark</td>
      <td style="color:#00008B;">&amp;Uuml;</td>
      <td style="color:#00008B;">&amp;#220;</td>
    </tr>
    <tr>
      <td>Ý</td>
      <td>capital Y, acute accent</td>
      <td style="color:#00008B;">&amp;Yacute;</td>
      <td style="color:#00008B;">&amp;#221;</td>
    </tr>
    <tr>
      <td>Þ</td>
      <td>capital THORN, Icelandic</td>
      <td style="color:#00008B;">&amp;THORN;</td>
      <td style="color:#00008B;">&amp;#222;</td>
    </tr>
    <tr>
      <td>ß</td>
      <td>small sharp s, German</td>
      <td style="color:#00008B;">&amp;szlig;</td>
      <td style="color:#00008B;">&amp;#223;</td>
    </tr>
    <tr>
      <td>à</td>
      <td>small a, grave accent</td>
      <td style="color:#00008B;">&amp;agrave;</td>
      <td style="color:#00008B;">&amp;#224;</td>
    </tr>
    <tr>
      <td>á</td>
      <td>small a, acute accent</td>
      <td style="color:#00008B;">&amp;aacute;</td>
      <td style="color:#00008B;">&amp;#225;</td>
    </tr>
    <tr>
      <td>â</td>
      <td>small a, circumflex accent</td>
      <td style="color:#00008B;">&amp;acirc;</td>
      <td style="color:#00008B;">&amp;#226;</td>
    </tr>
    <tr>
      <td>ã</td>
      <td>small a, tilde</td>
      <td style="color:#00008B;">&amp;atilde;</td>
      <td style="color:#00008B;">&amp;#227;</td>
    </tr>
    <tr>
      <td>ä</td>
      <td>small a, umlaut mark</td>
      <td style="color:#00008B;">&amp;auml;</td>
      <td style="color:#00008B;">&amp;#228;</td>
    </tr>
    <tr>
      <td>å</td>
      <td>small a, ring</td>
      <td style="color:#00008B;">&amp;aring;</td>
      <td style="color:#00008B;">&amp;#229;</td>
    </tr>
    <tr>
      <td>æ</td>
      <td>small ae</td>
      <td style="color:#00008B;">&amp;aelig;</td>
      <td style="color:#00008B;">&amp;#230;</td>
    </tr>
    <tr>
      <td>ç</td>
      <td>small c, cedilla</td>
      <td style="color:#00008B;">&amp;ccedil;</td>
      <td style="color:#00008B;">&amp;#231;</td>
    </tr>
    <tr>
      <td>è</td>
      <td>small e, grave accent</td>
      <td style="color:#00008B;">&amp;egrave;</td>
      <td style="color:#00008B;">&amp;#232;</td>
    </tr>
    <tr>
      <td>é</td>
      <td>small e, acute accent</td>
      <td style="color:#00008B;">&amp;eacute;</td>
      <td style="color:#00008B;">&amp;#233;</td>
    </tr>
    <tr>
      <td>ê</td>
      <td>small e, circumflex accent</td>
      <td style="color:#00008B;">&amp;ecirc;</td>
      <td style="color:#00008B;">&amp;#234;</td>
    </tr>
    <tr>
      <td>ë</td>
      <td>small e, umlaut mark</td>
      <td style="color:#00008B;">&amp;euml;</td>
      <td style="color:#00008B;">&amp;#235;</td>
    </tr>
    <tr>
      <td>ì</td>
      <td>small i, grave accent</td>
      <td style="color:#00008B;">&amp;igrave;</td>
      <td style="color:#00008B;">&amp;#236;</td>
    </tr>
    <tr>
      <td>í</td>
      <td>small i, acute accent</td>
      <td style="color:#00008B;">&amp;iacute;</td>
      <td style="color:#00008B;">&amp;#237;</td>
    </tr>
    <tr>
      <td>î</td>
      <td>small i, circumflex accent</td>
      <td style="color:#00008B;">&amp;icirc;</td>
      <td style="color:#00008B;">&amp;#238;</td>
    </tr>
    <tr>
      <td>ï</td>
      <td>small i, umlaut mark</td>
      <td style="color:#00008B;">&amp;iuml;</td>
      <td style="color:#00008B;">&amp;#239;</td>
    </tr>
    <tr>
      <td>ð</td>
      <td>small eth, Icelandic</td>
      <td style="color:#00008B;">&amp;eth;</td>
      <td style="color:#00008B;">&amp;#240;</td>
    </tr>
    <tr>
      <td>ñ</td>
      <td>small n, tilde</td>
      <td style="color:#00008B;">&amp;ntilde;</td>
      <td style="color:#00008B;">&amp;#241;</td>
    </tr>
    <tr>
      <td>ò</td>
      <td>small o, grave accent</td>
      <td style="color:#00008B;">&amp;ograve;</td>
      <td style="color:#00008B;">&amp;#242;</td>
    </tr>
    <tr>
      <td>ó</td>
      <td>small o, acute accent</td>
      <td style="color:#00008B;">&amp;oacute;</td>
      <td style="color:#00008B;">&amp;#243;</td>
    </tr>
    <tr>
      <td>ô</td>
      <td>small o, circumflex accent</td>
      <td style="color:#00008B;">&amp;ocirc;</td>
      <td style="color:#00008B;">&amp;#244;</td>
    </tr>
    <tr>
      <td>õ</td>
      <td>small o, tilde</td>
      <td style="color:#00008B;">&amp;otilde;</td>
      <td style="color:#00008B;">&amp;#245;</td>
    </tr>
    <tr>
      <td>ö</td>
      <td>small o, umlaut mark</td>
      <td style="color:#00008B;">&amp;ouml;</td>
      <td style="color:#00008B;">&amp;#246;</td>
    </tr>
    <tr>
      <td>÷</td>
      <td>division（除号）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;divide;</td>
      <td style="color:#00008B;">&amp;#247;</td>
    </tr>
    <tr>
      <td>ø</td>
      <td>small o, slash</td>
      <td style="color:#00008B;">&amp;oslash;</td>
      <td style="color:#00008B;">&amp;#248;</td>
    </tr>
    <tr>
      <td>ù</td>
      <td>small u, grave accent</td>
      <td style="color:#00008B;">&amp;ugrave;</td>
      <td style="color:#00008B;">&amp;#249;</td>
    </tr>
    <tr>
      <td>ú</td>
      <td>small u, acute accent</td>
      <td style="color:#00008B;">&amp;uacute;</td>
      <td style="color:#00008B;">&amp;#250;</td>
    </tr>
    <tr>
      <td>û</td>
      <td>small u, circumflex accent</td>
      <td style="color:#00008B;">&amp;ucirc;</td>
      <td style="color:#00008B;">&amp;#251;</td>
    </tr>
    <tr>
      <td>ü</td>
      <td>small u, umlaut mark</td>
      <td style="color:#00008B;">&amp;uuml;</td>
      <td style="color:#00008B;">&amp;#252;</td>
    </tr>
    <tr>
      <td>ý</td>
      <td>small y, acute accent</td>
      <td style="color:#00008B;">&amp;yacute;</td>
      <td style="color:#00008B;">&amp;#253;</td>
    </tr>
    <tr>
      <td>þ</td>
      <td>small thorn, Icelandic</td>
      <td style="color:#00008B;">&amp;thorn;</td>
      <td style="color:#00008B;">&amp;#254;</td>
    </tr>
    <tr>
      <td>ÿ</td>
      <td>small y, umlaut mark</td>
      <td style="color:#00008B;">&amp;yuml;</td>
      <td style="color:#00008B;">&amp;#255;</td>
    </tr>
    <tr>
      <td>€</td>
      <td>euro（欧元）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;euro;</td>
      <td style="color:#00008B;">&amp;#8364;</td>
    </tr>
    <tr>
      <td>™</td>
      <td>trademark（商标）</td>
      <td style="color:#00008B;font-weight:bold;">&amp;trade;</td>
      <td style="color:#00008B;">&amp;#8482;</td>
    </tr>
</table>

---

## 语言代码
- **ISO 语言代码**
1、HTML 的 lang 属性可用于网页或部分网页的语言，这对搜索引擎和浏览器是有帮助的；
2、根据 W3C 推荐标准，需要通过 html 标签中的 lang 属性对每张页面中的主要语言进行声明：
```html
<!-- HTML 中 -->
<html lang="en">
    ……
</html>

<!-- XHTML 中 -->
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
    ……
</html>
```

### ISO 639-1 语言代码
ISO 639-1 为各种语言定义了缩略词，可以在 HTML 和 XHTML 中的 lang 和 xml:lang 属性中使用它们：
<table>
	<tr style="background: #555555; color: #fff;">
		<th>语言</th>
		<th>ISO 代码</th>
	</tr>
	<tr>
		<td>Abkhazian</td>
		<td>ab</td>
	</tr>
	<tr>
		<td>Afar</td>
		<td>aa</td>
	</tr>
	<tr>
		<td>Afrikaans</td>
		<td>af</td>
	</tr>
	<tr>
		<td>Albanian</td>
		<td>sq</td>
	</tr>
	<tr>
		<td>Amharic</td>
		<td>am</td>
	</tr>
	<tr>
		<td>Arabic</td>
		<td>ar</td>
	</tr>
	<tr>
		<td>Aragonese</td>
		<td>an</td>
	</tr>
	<tr>
		<td>Armenian</td>
		<td>hy</td>
	</tr>
	<tr>
		<td>Assamese</td>
		<td>as</td>
	</tr>
	<tr>
		<td>Aymara</td>
		<td>ay</td>
	</tr>
	<tr>
		<td>Azerbaijani</td>
		<td>az</td>
	</tr>
	<tr>
		<td>Bashkir</td>
		<td>ba</td>
	</tr>
	<tr>
		<td>Basque</td>
		<td>eu</td>
	</tr>
	<tr>
		<td>Bengali (Bangla)</td>
		<td>bn</td>
	</tr>
	<tr>
		<td>Bhutani</td>
		<td>dz</td>
	</tr>
	<tr>
		<td>Bihari</td>
		<td>bh</td>
	</tr>
	<tr>
		<td>Bislama</td>
		<td>bi</td>
	</tr>
	<tr>
		<td>Breton</td>
		<td>br</td>
	</tr>
	<tr>
		<td>Bulgarian</td>
		<td>bg</td>
	</tr>
	<tr>
		<td>Burmese</td>
		<td>my</td>
	</tr>
	<tr>
		<td>Byelorussian (Belarusian)</td>
		<td>be</td>
	</tr>
	<tr>
		<td>Cambodian</td>
		<td>km</td>
	</tr>
	<tr>
		<td>Catalan</td>
		<td>ca</td>
	</tr>
	<tr>
		<td>Cherokee</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Chewa</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Chinese (简体)</td>
		<td>zh</td>
	</tr>
	<tr>
		<td>Chinese (繁体)</td>
		<td>zh</td>
	</tr>
	<tr>
		<td>Corsican</td>
		<td>co</td>
	</tr>
	<tr>
		<td>Croatian</td>
		<td>hr</td>
	</tr>
	<tr>
		<td>Czech</td>
		<td>cs</td>
	</tr>
	<tr>
		<td>Danish</td>
		<td>da</td>
	</tr>
	<tr>
		<td>Divehi</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Dutch</td>
		<td>nl</td>
	</tr>
	<tr>
		<td>Edo</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>English</td>
		<td>en</td>
	</tr>
	<tr>
		<td>Esperanto</td>
		<td>eo</td>
	</tr>
	<tr>
		<td>Estonian</td>
		<td>et</td>
	</tr>
	<tr>
		<td>Faeroese</td>
		<td>fo</td>
	</tr>
	<tr>
		<td>Farsi</td>
		<td>fa</td>
	</tr>
	<tr>
		<td>Fiji</td>
		<td>fj</td>
	</tr>
	<tr>
		<td>Finnish</td>
		<td>fi</td>
	</tr>
	<tr>
		<td>Flemish</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>French</td>
		<td>fr</td>
	</tr>
	<tr>
		<td>Frisian</td>
		<td>fy</td>
	</tr>
	<tr>
		<td>Fulfulde</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Galician</td>
		<td>gl</td>
	</tr>
	<tr>
		<td>Gaelic (Scottish)</td>
		<td>gd</td>
	</tr>
	<tr>
		<td>Gaelic (Manx)</td>
		<td>gv</td>
	</tr>
	<tr>
		<td>Georgian</td>
		<td>ka</td>
	</tr>
	<tr>
		<td>German</td>
		<td>de</td>
	</tr>
	<tr>
		<td>Greek</td>
		<td>el</td>
	</tr>
	<tr>
		<td>Greenlandic</td>
		<td>kl</td>
	</tr>
	<tr>
		<td>Guarani</td>
		<td>gn</td>
	</tr>
	<tr>
		<td>Gujarati</td>
		<td>gu</td>
	</tr>
	<tr>
		<td>Haitian Creole</td>
		<td>ht</td>
	</tr>
	<tr>
		<td>Hausa</td>
		<td>ha</td>
	</tr>
	<tr>
		<td>Hawaiian</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Hebrew</td>
		<td>he, iw</td>
	</tr>
	<tr>
		<td>Hindi</td>
		<td>hi</td>
	</tr>
	<tr>
		<td>Hungarian</td>
		<td>hu</td>
	</tr>
	<tr>
		<td>Ibibio</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Icelandic</td>
		<td>is</td>
	</tr>
	<tr>
		<td>Ido</td>
		<td>io</td>
	</tr>
	<tr>
		<td>Igbo</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Indonesian</td>
		<td>id, in</td>
	</tr>
	<tr>
		<td>Interlingua</td>
		<td>ia</td>
	</tr>
	<tr>
		<td>Interlingue</td>
		<td>ie</td>
	</tr>
	<tr>
		<td>Inuktitut</td>
		<td>iu</td>
	</tr>
	<tr>
		<td>Inupiak</td>
		<td>ik</td>
	</tr>
	<tr>
		<td>Irish</td>
		<td>ga</td>
	</tr>
	<tr>
		<td>Italian</td>
		<td>it</td>
	</tr>
	<tr>
		<td>Japanese</td>
		<td>ja</td>
	</tr>
	<tr>
		<td>Javanese</td>
		<td>jv</td>
	</tr>
	<tr>
		<td>Kannada</td>
		<td>kn</td>
	</tr>
	<tr>
		<td>Kanuri</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Kashmiri</td>
		<td>ks</td>
	</tr>
	<tr>
		<td>Kazakh</td>
		<td>kk</td>
	</tr>
	<tr>
		<td>Kinyarwanda (Ruanda)</td>
		<td>rw</td>
	</tr>
	<tr>
		<td>Kirghiz</td>
		<td>ky</td>
	</tr>
	<tr>
		<td>Kirundi (Rundi)</td>
		<td>rn</td>
	</tr>
	<tr>
		<td>Konkani</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Korean</td>
		<td>ko</td>
	</tr>
	<tr>
		<td>Kurdish</td>
		<td>ku</td>
	</tr>
	<tr>
		<td>Laothian</td>
		<td>lo</td>
	</tr>
	<tr>
		<td>Latin</td>
		<td>la</td>
	</tr>
	<tr>
		<td>Latvian (Lettish)</td>
		<td>lv</td>
	</tr>
	<tr>
		<td>Limburgish ( Limburger)</td>
		<td>li</td>
	</tr>
	<tr>
		<td>Lingala</td>
		<td>ln</td>
	</tr>
	<tr>
		<td>Lithuanian</td>
		<td>lt</td>
	</tr>
	<tr>
		<td>Macedonian</td>
		<td>mk</td>
	</tr>
	<tr>
		<td>Malagasy</td>
		<td>mg</td>
	</tr>
	<tr>
		<td>Malay</td>
		<td>ms</td>
	</tr>
	<tr>
		<td>Malayalam</td>
		<td>ml</td>
	</tr>
	<tr>
		<td>&nbsp;</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Maltese</td>
		<td>mt</td>
	</tr>
	<tr>
		<td>Maori</td>
		<td>mi</td>
	</tr>
	<tr>
		<td>Marathi</td>
		<td>mr</td>
	</tr>
	<tr>
		<td>Moldavian</td>
		<td>mo</td>
	</tr>
	<tr>
		<td>Mongolian</td>
		<td>mn</td>
	</tr>
	<tr>
		<td>Nauru</td>
		<td>na</td>
	</tr>
	<tr>
		<td>Nepali</td>
		<td>ne</td>
	</tr>
	<tr>
		<td>Norwegian</td>
		<td>no</td>
	</tr>
	<tr>
		<td>Occitan</td>
		<td>oc</td>
	</tr>
	<tr>
		<td>Oriya</td>
		<td>or</td>
	</tr>
	<tr>
		<td>Oromo (Afaan Oromo)</td>
		<td>om</td>
	</tr>
	<tr>
		<td>Papiamentu</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Pashto (Pushto)</td>
		<td>ps</td>
	</tr>
	<tr>
		<td>Polish</td>
		<td>pl</td>
	</tr>
	<tr>
		<td>Portuguese</td>
		<td>pt</td>
	</tr>
	<tr>
		<td>Punjabi</td>
		<td>pa</td>
	</tr>
	<tr>
		<td>Quechua</td>
		<td>qu</td>
	</tr>
	<tr>
		<td>Rhaeto-Romance</td>
		<td>rm</td>
	</tr>
	<tr>
		<td>Romanian</td>
		<td>ro</td>
	</tr>
	<tr>
		<td>Russian</td>
		<td>ru</td>
	</tr>
	<tr>
		<td>Sami (Lappish)</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Samoan</td>
		<td>sm</td>
	</tr>
	<tr>
		<td>Sangro</td>
		<td>sg</td>
	</tr>
	<tr>
		<td>Sanskrit</td>
		<td>sa</td>
	</tr>
	<tr>
		<td>Serbian</td>
		<td>sr</td>
	</tr>
	<tr>
		<td>Serbo-Croatian</td>
		<td>sh</td>
	</tr>
	<tr>
		<td>Sesotho</td>
		<td>st</td>
	</tr>
	<tr>
		<td>Setswana</td>
		<td>tn</td>
	</tr>
	<tr>
		<td>Shona</td>
		<td>sn</td>
	</tr>
	<tr>
		<td>Sichuan Yi</td>
		<td>ii</td>
	</tr>
	<tr>
		<td>Sindhi</td>
		<td>sd</td>
	</tr>
	<tr>
		<td>Sinhalese</td>
		<td>si</td>
	</tr>
	<tr>
		<td>Siswati</td>
		<td>ss</td>
	</tr>
	<tr>
		<td>Slovak</td>
		<td>sk</td>
	</tr>
	<tr>
		<td>Slovenian</td>
		<td>sl</td>
	</tr>
	<tr>
		<td>Somali</td>
		<td>so</td>
	</tr>
	<tr>
		<td>Spanish</td>
		<td>es</td>
	</tr>
	<tr>
		<td>Sundanese</td>
		<td>su</td>
	</tr>
	<tr>
		<td>Swahili (Kiswahili)</td>
		<td>sw</td>
	</tr>
	<tr>
		<td>Swedish</td>
		<td>sv</td>
	</tr>
	<tr>
		<td>Syriac</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Tagalog</td>
		<td>tl</td>
	</tr>
	<tr>
		<td>Tajik</td>
		<td>tg</td>
	</tr>
	<tr>
		<td>Tamazight</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Tamil</td>
		<td>ta</td>
	</tr>
	<tr>
		<td>Tatar</td>
		<td>tt</td>
	</tr>
	<tr>
		<td>Telugu</td>
		<td>te</td>
	</tr>
	<tr>
		<td>Thai</td>
		<td>th</td>
	</tr>
	<tr>
		<td>Tibetan</td>
		<td>bo</td>
	</tr>
	<tr>
		<td>Tigrinya</td>
		<td>ti</td>
	</tr>
	<tr>
		<td>Tonga</td>
		<td>to</td>
	</tr>
	<tr>
		<td>Tsonga</td>
		<td>ts</td>
	</tr>
	<tr>
		<td>Turkish</td>
		<td>tr</td>
	</tr>
	<tr>
		<td>Turkmen</td>
		<td>tk</td>
	</tr>
	<tr>
		<td>Twi</td>
		<td>tw</td>
	</tr>
	<tr>
		<td>Uighur</td>
		<td>ug</td>
	</tr>
	<tr>
		<td>Ukrainian</td>
		<td>uk</td>
	</tr>
	<tr>
		<td>Urdu</td>
		<td>ur</td>
	</tr>
	<tr>
		<td>Uzbek</td>
		<td>uz</td>
	</tr>
	<tr>
		<td>Venda</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Vietnamese</td>
		<td>vi</td>
	</tr>
	<tr>
		<td>Volapük</td>
		<td>vo</td>
	</tr>
	<tr>
		<td>Wallon</td>
		<td>wa</td>
	</tr>
	<tr>
		<td>Welsh</td>
		<td>cy</td>
	</tr>
	<tr>
		<td>Wolof</td>
		<td>wo</td>
	</tr>
	<tr>
		<td>Xhosa</td>
		<td>xh</td>
	</tr>
	<tr>
		<td>Yi</td>
		<td>&nbsp;</td>
	</tr>
	<tr>
		<td>Yiddish</td>
		<td>yi, ji</td>
	</tr>
	<tr>
		<td>Yoruba</td>
		<td>yo</td>
	</tr>
	<tr>
		<td>Zulu</td>
		<td>zu</td>
	</tr>
</table>

---

