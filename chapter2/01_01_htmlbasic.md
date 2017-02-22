# Htmlbaisic  
- [一、前言](#一前言)  
- [二、html基础格式内容](#二html基础格式内容)  
  - [1、<!DOCTYPE>](#1<!DOCTYPE>)  
  - [2、html标签](#2html标签)  
  - [3、head头](#3head头)  
  - [4、body体](#4body体)  
- [三、html头部](#三html头部)  
  - [1、title](#1title)  
  - [2、meta](#2meta)  
  - [3、link](#3link)  
  - [4、style](#4style)  
  - [5、script](#5script)  
  - [6、base](#6base)  
- [四、块与内联标签](#四块与内联标签)  
  - [1、块与内联的区别](#1块与内联的区别)  
  - [2、可变元素](#2可变元素)  
  - [3、div和span](#3div和span)  
  - [4、通过样式设置块或内联](#4通过样式设置块或内联)  
- [五、属性](#五属性)  
  - [1、全局属性](#1全局属性)  
  - [2、其它重要属性](#2、全局属性之外的重要属性)  
- [六、列表](#六列表)  
  - [1、无序列表](#1无序列表)  
  - [2、有序列表](#2有序列表)  
  - [3、自定义列表](#3自定义列表)  
- [七、表格](#七表格)  
  - [1、表格其他标签](#1表格其他标签)  
  - [2、表格重要的属性](#2表格重要的属性)  
- [八、表单](#八表单)  
  - [1、输入元素input](#1输入元素input)  
  - [2、文本域textarea](#2文本域textarea)  
  - [3、下拉标签select](#3下拉标签select)  
  - [4、label](#4label)  
  - [5、按钮button](#5按钮button)  
  - [6、fieldset](#6fieldset)  
- [九、框架](#九框架)  
- [十、格式化标签](#十格式化标签)  
  - [1、文本格式化标签](#1文本格式化标签)  
  - [2、"计算机输出" 标签](#2"计算机输出" 标签)  
  - [3、引文, 引用, 及标签定义](#3引文, 引用, 及标签定义)  
- [十一、其它重要标签](#十一其它重要标签)  
- [十二、事件](#十二事件)  

## 一、前言  
学习web前端开发基础技术需要掌握的最基础的三门技术：HTML、CSS、JavaScript语言。  

1. HTML是网页内容的载体。内容就是网页制作者放在页面上想要让用户浏览的信息，可以包含文字、图片、视频等。  

2. CSS样式是表现。就像网页的外衣。比如，标题字体、颜色变化，或为标题加入背景图片、边框等。所有这些用来改变内容外观的东西称之为表现。  

3. JavaScript是用来实现网页上的特效效果。如：鼠标滑过弹出下拉菜单。或鼠标滑过表格的背景颜色改变。还有焦点新闻（新闻图片）的轮换。可以这么理解，有动画的，有交互的一般都是用JavaScript来实现的。   

总结起来就是：HTML负责结构和内容，CSS负责表现，而JavaScript则负责交互和特效。  

所以web前端学习要从HTML、CSS、JavaScript语言学起，只有学好他们才能更好的学习更高级的技术。  

[回到顶部](#htmlbasic)  

## 二、html基础格式内容  
````  
<!DOCTYPE HTML>
<html>
    <head>
        <meta charset="utf-8">
        <title>制作我的第一个网页</title>
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
</html>  
````  
这是一个基础的HTML格式：  

### 1、<!DOCTYPE>  

`<!DOCTYPE>`是文档声明，声明使用的是哪个版本的HTML，在HTML5时代，就是`<!DOCTYPE HTML>`，如果要使用其他版本的HTML，可以[点击这里查看其他HTML版本声明方法](http://www.w3school.com.cn/html/html_doctype.asp)。  

### 2、html标签  

HTML标记标签通常被称为 HTML 标签 (HTML tag)，标签又称元素。  
- 一个HTML页面由很多个标签组成，网页的所有内容都必须放在标签之间，不同的标签定义不同的格式或内容。  
- HTML 标签是由**尖括号包围**的关键词，比如 <html>；  
- HTML 标签通常是**成对出现的**，比如 <b> 和 </b>；  
- 标签对中的第一个标签是**开始标签**，第二个标签是**结束标签**；    
- 少数标签没有基础标签，非成对出现，如`<br/>`、`<hr/>`、`<img/>`等。  
- 标签与标签之间是可以**嵌套**的，但先后顺序必须保持一致，如：`<div>`里嵌套`<p>`，那么`</p>`必须放在`</div>`的前面。

网页的内容都包含在`<html>`和`</html>`之间。  

### 3、head头  

`<head>`标签定义文档的头部内容，头部内容是描述文档的属性和信息的，通常不会在网页中显示出来。
### 4、body体  

`<body>`标签内放入文档的主体内容，是会显示在网页上的。  

[回到顶部](#htmlbasic)  

## 三、html头部  

`<head>`标签是所有头部标签的容器。`<head></head>`内的标签可包含脚本、样式表、元信息等等。  

以下标签都可以添加到 head 部分：`<title>`、`<base>`、`<link>`、`<meta>`、`<script>`以及 `<style>`。  

### 1、title    

`<title>`用来定义网页的标题。  

title 元素在所有 HTML/XHTML 文档中都是必需的。  

title 元素能够：
- 定义浏览器工具栏中的标题；  
- 提供页面被添加到收藏夹时显示的标题；  
- 显示在搜索引擎结果中的页面标题。   

[回到顶部](#htmlbasic)  

### 2、meta    

元数据（metadata）是关于数据的信息。  

`<meta>` 标签提供关于 HTML 文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。  

meta 元素常被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。
<meta> 标签始终位于 head 元素中。  

元数据可用于浏览器（如何显示内容或重新加载页面）、搜索引擎（关键词）、或其他 web 服务。

最常用的是定义文档的字符集，通常我们使用`utf-8`字符集：  
````
<meta charset="utf-8">
````  
上面这是简略写法，它的完整写法是：  
````
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">  
````

一些搜索引擎会利用 meta 元素的 name 和 content 属性来索引页面。  

下面的 meta 元素定义页面的描述：  
```
<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />  
```
下面的 meta 元素定义页面的关键词：  
````
<meta name="keywords" content="HTML, CSS, XML" />  
````

meta元素还有很多功能，并不常用，要说清楚可能需要单独一个篇章。  

[回到顶部](#htmlbasic)  

### 3、link    

`<link>`标签定义文档与外部资源之间的关系。
`<link>`标签最常用于连接样式表：
````
<link rel="stylesheet" type="text/css" href="mystyle.css" />
````  

### 4、style    

`<style>`标签用于为HTML文档定义样式信息。
````
<style type="text/css">
body {background-color:yellow}
p {color:blue}
</style>
````  

### 5、script    

`<script>`标签用于定义客户端脚本，比如 JavaScript。  

### 6、base    

`<base>`标签为页面上的所有链接规定默认地址或默认目标（target）：
````
<base href="http://www.w3school.com.cn/images/" />
<base target="_blank" />
````  

[回到顶部](#htmlbasic)  

## 四、块与内联标签  

大多数 HTML 元素被定义为块级元素或内联元素。  

块级元素在浏览器显示时，通常会以新行来开始（和结束）。  

实例: `<h1>`、 `<p>`、 `<ul>`、 `<table>`。

内联元素在显示时通常不会以新行开始。  

实例: `<b>`、 `<td>`、 `<a>`、 `<img>`。  

### 1、块与内联的区别  

1. 块级元素会独占一行，其宽度自动填满其父元素宽度。行内元素不会独占一行，相邻的行内元素会排列在同一行里，知道一行排不下，才会换行，其宽度随元素的内容而变化。  

- 块级元素可以设置width,height属性，行内元素设置width,height无效**【注意：块级元素即使设置了宽度，仍然是独占一行的】** 。  

- 块级元素可以设置margin和padding。行内元素的水平方向的padding-left、padding-right、margin-left、margin-right都产生边距效果，但是竖直方向的padding-top、padding-bottom、margin-top、margin-bottom都不会产生边距效果。**（水平方向有效，竖直方向无效）**  

[回到顶部](#htmlbasic)  

### 2、可变元素  

可变元素为根据上下文语境决定该元素为块元素或者内联元素。  

- `applet` - java applet  
- `button` - 按钮  
- `del` - 删除文本  
- `iframe` - inline frame  
- `ins` - 插入的文本  
- `map` - 图片区块(map)  
- `object` - object对象  
- `script` - 客户端脚本  

### 3、div和span  

`<div>`元素是块级元素，没有特定的含义，它可用于组合其他 HTML 元素的容器。  

`<span>`元素是内联元素，也没有特定的含义，可用作文本的容器。  

`<div>`和`<span>`被频繁大量使用，它们的存在增强了HTML的可塑性。  

### 4、通过样式设置块或内联  

通过CSS样式中的`display`可以将某个元素定义为块级元素、内联元素或行内块元素。  

`display:block;`可将标签设置为块级元素；`display:inline;`可将标签设置为内联元素；`display:inline-block;`可将元素设置为行内块元素。  

行内块元素是不会独占一行，但又可以设置宽和高属性的元素。  

[回到顶部](#htmlbasic)  

## 五、属性  

属性是 HTML 元素提供的附加信息。  

- HTML元素可以设置属性；  
- 属性可以在元素中添加附加信息；  
- 属性一般描述于开始标签；  
- 属性总是以名称/值对的形式出现，比如：`name="value"`；  
- 属性值应该始终被包括在引号内，双引号是最常用的，但使用单引号也可以，极少的属性值因为自身就有双引号，则必须使用单引号，如：`name='"ShotGun"Nelson'`；  
- 和标签一样，属性怼大小写不敏感，丹建议使用小写。  

### 1、全局属性  

全局属性是适用于所有标签的属性，全局属性有这些：  

|属性|说明|  
|:----|:----|  
|[id](http://www.w3school.com.cn/tags/att_standard_id.asp)|规定元素的唯一id。|  
|[class](http://www.w3school.com.cn/tags/att_standard_class.asp)|规定元素的一个或多个类名（引用样式表中的类）。|  
|[style](http://www.w3school.com.cn/tags/att_standard_style.asp)|规定元素的行内 CSS 样式。|  
|[title](http://www.w3school.com.cn/tags/att_standard_title.asp)|规定有关元素的额外信息。|  
|[lang](http://www.w3school.com.cn/tags/att_standard_lang.asp)|规定元素内容的语言。|  
|[hidden](http://www.w3school.com.cn/tags/att_global_hidden.asp)|规定元素仍未或不再相关。HTML新属性。|  
|[accesskey](http://www.w3school.com.cn/tags/att_standard_accesskey.asp)|规定激活元素的快捷键。|  
|[contenteditable](http://www.w3school.com.cn/tags/att_global_contenteditable.asp)|规定元素内容是否可编辑。HTML5新属性。|  
|[data-*](http://www.w3school.com.cn/tags/att_global_data.asp)|用于存储页面或应用程序的私有定制数据。HTML5新属性。|  
|[dir](http://www.w3school.com.cn/tags/att_standard_dir.asp)|规定元素中内容的文本方向。|  
|[draggable](http://www.w3school.com.cn/tags/att_global_draggable.asp)|规定元素是否可拖动。HTML5新属性|  
|[spellcheck](http://www.w3school.com.cn/tags/att_global_spellcheck.asp)|规定是否对元素进行拼写和语法检查。|  
|[tabindex](http://www.w3school.com.cn/tags/att_standard_tabindex.asp)|规定元素的 tab 键次序。|  
|contextmenu|规定元素的上下文菜单。上下文菜单在用户点击元素时显示。HTML5新属性，但不被大多数浏览器支持。|  
|dropzone|规定在拖动被拖动数据时是否进行复制、移动或链接。HTML5新属性，但不被大多数浏览器支持。|  
|translate|规定是否应该翻译元素内容。HTML5新属性，但不被大多数浏览器支持。|    

[回到顶部](#htmlbasic)  

### 2、全局属性之外的重要属性  

|属性|说明|  
|:----|:----|  
|[href](http://www.w3school.com.cn/tags/att_a_href.asp)|规定链接指向的页面的 URL。|  
|[src](http://www.w3school.com.cn/tags/att_img_src.asp)|规定显示图像的 URL。|  
|[width](http://www.w3school.com.cn/tags/att_img_height-width.asp)|设置块级元素宽度。img中是设置图像宽度。|  
|[height](http://www.w3school.com.cn/tags/att_img_height-width.asp)|设置块级元素高度。img中是设置图像高度。|  
|[alt](http://www.w3school.com.cn/tags/att_img_alt.asp)|规定图像的替代文本。|  
|[target](http://www.w3school.com.cn/tags/att_a_target.asp)|规定在何处打开链接文档。|  
|[type](http://www.w3school.com.cn/tags/att_a_type.asp)|type 属性规定目标文档的 MIME 类型。只能在 href 属性存在时使用。|  
|[value](http://www.w3school.com.cn/tags/att_button_value.asp)|规定与元素关联的初始值。|    

[回到顶部](#htmlbasic)  

## 六、列表  

HTML 支持有序、无序和自定义列表。  

### 1、无序列表  
无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记。  

无序列表使用`<ul>`标签：
````
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
````
浏览器显示如下：
- Coffee  
- Milk    

[回到顶部](#htmlbasic)  

### 2、有序列表   

有序列表也是一列项目，列表项目使用数字进行标记。 有序列表始于`<ol>`标签。每个列表项始于`<li>`标签。  

列表项项使用数字来标记：  
````
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
````  
浏览器中显示如下：
1. Coffee
- Milk  

### 3、自定义列表  
自定义列表不仅仅是一列项目，而是项目及其注释的组合。
自定义列表以 `<dl>` 标签开始。每个自定义列表项以 `<dt>` 开始。每个自定义列表项的定义以 `<dd>` 开始。  
````
<dl>
<dt>Coffee</dt>
<dd>-- black hot drink</dd>
<dt>Milk</dt>
<dd>-- white cold drink</dd>
</dl>  
````
浏览器显示如下：  
Coffee  
-- black hot drink  
Milk  
-- white cold drink   

**提示:** 列表可以嵌套，项内部可以使用段落、换行符、图片、链接以及其他列表等等。  

[回到顶部](#htmlbasic)  

## 七、表格   

表格由`<table>`标签来定义。每个表格均有若干行（由`<tr>`标签定义），每行被分割为若干单元格（由`<td>`标签定义）。字母td指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。  
一个典型的表格代码如下：  
````
<table>
    <tr>
        <td>row 1, cell 1</td>
        <td>row 1, cell 2</td>
    </tr>
    <tr>
        <td>row 2, cell 1</td>
        <td>row 2, cell 2</td>
    </tr>
</table>  
````  
网页显示：  
<table>
    <tr>
        <td>row 1, cell 1</td>
        <td>row 1, cell 2</td>
    </tr>
    <tr>
        <td>row 2, cell 1</td>
        <td>row 2, cell 2</td>
    </tr>
</table>    

[回到顶部](#htmlbasic)  

### 1、表格其他标签  

`<th>`标签定义表格的表头。默认加粗黑体显示。表头一般放在表格的页眉中。  

`<thead>`标签定义表格的页眉，不是必须的。  

`<tbody>`标签定义表格的主题，不是必须的。  

`<tfoot>`标签定义表格的页脚，不是必须的,如果出现了必须在`<tbody>`之前，在`<thead>`之后。  

`<caption>`标签定义表格的标题，标题通常显示的表格的上面，不是必须的。  

`<colgroup>`标签定义表格列的组，一般和`col`标签合用，可以以列为单位设置属性或样式。  

一个包含所有表格标签的代码如下：  
````
<table>
  <caption>
  这是表格的标题
  </caption>
  <colgroup>
    <col span="2" style="background-color:red;"/>
    <col style="background-colorgreen;">
  </colgroup>
  <thead>
    <tr>
      <th>页眉第一列</th>
      <th>页眉第二列</th>
      <th>页眉第三列</th>
    </tr>
  </thead>  
  <tfoot>
    <tr>
      <td>页脚第一列</td>
      <td>页脚第二列</td>
      <td>页脚第三列</td>
    </tr>
  </tfoot>
  <tbody>
  <tr>
    <td>第一行第一列</td>
    <td>第一行第二列</td>
    <td>第一行第三列</td>
  </tr>
  <tr>
    <td>第二行第一列</td>
    <td>第二行第二列</td>
    <td>第二行第三列</td>
  </tr>
  </tbody>
</table>
````  
网页显示效果如下：  
<table>
  <caption>
  这是表格的标题
  </caption>
  <colgroup>
    <col span="2" style="background-color:red;"/>
    <col style="background-color:green;">
  </colgroup>
  <thead>
    <tr>
      <th>页眉第一列</th>
      <th>页眉第二列</th>
      <th>页眉第三列</th>
    </tr>
  </thead>  
  <tfoot>
    <tr>
      <td>页脚第一列</td>
      <td>页脚第二列</td>
      <td>页脚第三列</td>
    </tr>
  </tfoot>
  <tbody>
  <tr>
    <td>第一行第一列</td>
    <td>第一行第二列</td>
    <td>第一行第三列</td>
  </tr>
  <tr>
    <td>第二行第一列</td>
    <td>第二行第二列</td>
    <td>第二行第三列</td>
  </tr>
  </tbody>
</table>  

[回到顶部](#htmlbasic)  

### 2、表格重要的属性  

表格特有的重要的属性主要是`rowspan`和`colspan`。  

`rowspan`可以设置单元格跨行，`colspan`可以设置单元格跨列：   

````
<table border="1">
<caption>
 单元格跨两列:
</caption>
<tr>
  <th>Name</th>
  <th colspan="2">Telephone</th>
</tr>
<tr>
  <td>Bill Gates</td>
  <td>555 77 854</td>
  <td>555 77 855</td>
</tr>
</table>

<table border="1">
<caption>
 单元格跨两行:
</caption>
<tr>
  <th>First Name:</th>
  <td>Bill Gates</td>
</tr>
<tr>
  <th rowspan="2">Telephone:</th>
  <td>555 77 854</td>
</tr>
<tr>
  <td>555 77 855</td>
</tr>
</table>
````  
上述代码网页显示效果：  
<table border="1">
<caption>
 单元格跨两列:
</caption>
<tr>
  <th>Name</th>
  <th colspan="2">Telephone</th>
</tr>
<tr>
  <td>Bill Gates</td>
  <td>555 77 854</td>
  <td>555 77 855</td>
</tr>
</table>

<table border="1">
<caption>
 单元格跨两行:
</caption>
<tr>
  <th>First Name:</th>
  <td>Bill Gates</td>
</tr>
<tr>
  <th rowspan="2">Telephone:</th>
  <td>555 77 854</td>
</tr>
<tr>
  <td>555 77 855</td>
</tr>
</table>  

[回到顶部](#htmlbasic)  

## 八、表单  

表单的作用是连通浏览器端和服务器端，实现交互的。  

表单元素是允许用户在表单中输入内容,比如：文本域(textarea)、下拉列表、单选框(radio-buttons)、复选框(checkboxes)等等。  

### 1、输入元素input  

表单众多标签中最长被用到的是`<input/>`标签。根据`type`属性的不同，`<input/>`有很多不同的形态，实现不同的功能。`<input/>` 的`type`类型总共有23种，常用的有10种：  

|type|说明|  
|:----|:----|  
|button|定义可点击按钮（多数情况下，用于通过 JavaScript 启动脚本）。|  
|checkbox|定义复选框。|  
|file|定义输入字段和 "浏览"按钮，供文件上传。|  
|hidden|定义隐藏的输入字段。|  
|image|定义图像形式的提交按钮。|  
|password|定义密码字段。该字段中的字符被掩码。|  
|radio|定义单选按钮。|  
|reset|定义重置按钮。重置按钮会清除表单中的所有数据。|  
|submit|定义提交按钮。提交按钮会把表单数据发送到服务器。|  
|text|定义单行的输入字段，用户可在其中输入文本。默认宽度为 20 个字符。|  


### 2、文本域textarea  

`<textarea>`标签定义一个多行的文本输入控件。  

文本区域中可容纳无限数量的文本，其中的文本的默认字体是等宽字体（通常是 Courier）。  

可以通过 cols 和 rows 属性来规定 textarea 的尺寸大小，不过更好的办法是使用 CSS 的 height 和 width 属性。   

代码示例：  
````
<textarea rows="4" cols="30">
我是一个文本框。
</textarea>
````  
网页显示效果：  

<textarea rows="2" cols="30">
我是一个文本框。
</textarea>    

[回到顶部](#htmlbasic)  

### 3、下拉标签select  

`<select>`元素用来创建下拉列表。  

`<select>`元素中的`<option>`标签定义了列表中的可用选项。  

`<select>`元素中的`<optgroup>`标签用来组合选项。  

代码示例：  
````
<select>
  <optgroup label="第一组选项">
    <option value="first">选项一</option>
    <option value="second">选项二</option>
  </optgroup>
  <optgroup label="第二组选项">
    <option value="third">选项3</option>
    <option value="forth">选项4</option>
  </optgroup>
</select>  
````  
网页显示效果：  
<select>
  <optgroup label="第一组选项">
    <option value="first">选项一</option>
    <option value="second">选项二</option>
  </optgroup>
  <optgroup label="第二组选项">
    <option value="third">选项3</option>
    <option value="forth">选项4</option>
  </optgroup>
</select>    

[回到顶部](#htmlbasic)  

### 4、label  

`<label>`标签为 input 元素定义标注（标记）。  

`label`元素不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果您在`label`元素内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。  

`<label>`标签的for属性应当与相关元素的id属性相同。  

###  5、按钮button  

`<button></button>`标签是按钮，作用几乎与`<input type="button">`、`<input type="submit">`及`<input type="reset">`相同，区别是`<button></button>`标签之间可以嵌套其他标签，可以实现更丰富的内容。  

`<input type="submit">` === `<button type="submit"></button>`  
`<input type="reset">` === `<button type="reset"></button>`  
`<input type="button">` === `<button type="button"></button>`  

但是不同浏览器对`<button>`的默认取值不同，所以如果我们先要一个按钮来提交表单数据的话，最好还是用`<input type="submit">`。  

### 6、fieldset  

`<fieldset>`标签可以将表单内的相关元素分组。  

`<fieldset>`标签会在相关表单元素周围绘制边框。  

`<legend>`标签为`<fieldset>`标签定义标题。  

代码示例：  
````
<fieldset>
 <legend>Personalia:</legend>
 Name: <input type="text"><br>
 Email: <input type="text"><br>
 Date of birth: <input type="text">
</fieldset>
````  
页面显示效果：
<form>
  <fieldset>
   <legend>Personalia:</legend>
   Name: <input type="text"><br>
   Email: <input type="text"><br>
  </fieldset>
  Date of birth: <input type="text">
</form>    

[回到顶部](#htmlbasic)  

## 九、框架   

`<iframe>`标签规定一个内联框架。  

一个内联框架被用来在当前 HTML 文档中嵌入另一个文档。  

在`<iframe>`和`</iframe>`之间放文本，当某浏览器不支持iframe时，可以显示。  

使用CSS为`<iframe>`（包括滚动条）定义样式。   

[回到顶部](#htmlbasic)  

## 十、格式化标签  

HTML 使用标签 `<b>`("bold") 与 `<i>`("italic") 对输出的文本进行格式, 如：**粗体** or*斜体*。这些HTML标签被称为格式化标签。  

### 1、文本格式化标签  

|标签|描述|  
|:----|:----|  
|`<b>`|定义粗体文本|  
|`<em>`|定义着重文字|  
|`<i>`|定义斜体字|  
|`<small>`|定义小号字|  
|`<strong>`|定义加重语气|  
|`<sub>`|定义下标字|  
|`<sup>`|定义上标字|  
|`<ins>`|定义插入字|  
|`<del>`|定义删除字|  

### 2、"计算机输出" 标签
|标签|描述|  
|:----|:----|  
|`<code>`|定义计算机代码|  
|`<kbd>`|定义键盘码|  
|`<samp>`|定义计算机代码样本|  
|`<var>`|定义变量|  
|`<pre>`|定义预格式文本|   

### 3、引文, 引用, 及标签定义  

|标签|描述|  
|:----|:----|  
|`<abbr>`|定义缩写|  
|`<address>`|定义地址|  
|`<bdo>`|定义文字方向|  
|`<blockquote>`|定义长的引用|  
|`<q>`|定义短的引用语|  
|`<cite>`|定义引用、引证|  
|`<dfn>`|定义一个定义项目|   

[回到顶部](#htmlbasic)  

## 十一、其它重要标签    

`<br/>`标签起到换行的作用。  

`<hr/>`标签在页面中创建一条水平线。  

`<!---->`定义注释，注释内容放在中划线之间，如：`<!-- 这是注释 -->`。  

## 十二、事件  

HTML中事件可以理解为 **会出发浏览器中的行为的属性** ，通常是会出发JavaScript函数。  

事件属性不建议常用，我们完全可以用JavaScript脚本来代替它。  
