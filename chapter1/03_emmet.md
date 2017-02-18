# Emmet  
- [一、编写HTML代码](#一编写HTML代码)  
 - [1、初始化HTML](#1初始化HTML)  
 - [2、添加类、id、文本和属性](2#添加类、id、文本和属性)  
 - [3、嵌套](#3嵌套)  
 - [4、分组](#4分组)  
 - [5、隐式标签](#5隐式标签)  
 - [6、 定义多个元素](#6定义多个元素)  
 - [7、定义多个带属性的元素](#7定义多个带属性的元素)  
- [二、CSS缩写](#二CSS缩写)  
 - [1、值](#1值)  
 - [2、附加属性](#2附加属性)  
 - [3、模糊匹配](#3模糊匹配)  
 - [4、供应商前缀](#4供应商前缀)  
 - [5、 渐变](#5 渐变)  

## 一、编写HTML代码

### 1、初始化HTML

只需输入`!`或者`html:5`，然后按Tab键就可以自动生成HTML初始代码：

![Emmet实现HTML初始化演示](emmet_html1.gif)

### 2、添加类、id、文本和属性

连续输入元素名称和ID，Emmet会自动为你补全，比如输入p#foo，再按Tab键，会自动生成代码：
````
<p id="foo"></p>
````
![Emmet实现HTML初始化演示](emmet_html2.gif)

连续输入类和id，比如p.bar#foo，会自动生成：

````
<p class="bar" id="foo"></p>
````

输入h1{foo}和a[href=https://github.com]可以便捷添加内容和属性代码：
````
<h1>foo</h1>
<a href="https://github.com"></a>
````

[回到顶部](#emmet)  

### 3、嵌套

只需要1行代码就可以实现标签的嵌套。

- \>：子元素符号，表示嵌套的元素
- +：同级标签符号
- ^：可以使该符号前的标签提升一行

![Emmet实现HTML初始化演示](emmet_html3.gif)  


### 4、分组

可以通过嵌套和括号来快速生成一些代码块，比如输入(.foo>h1)+(.bar>h2)，会自动生成如下代码：

````
<div class="foo">
  <h1></h1>
</div>
<div class="bar">
  <h2></h2>
</div>
````  

[回到顶部](#emmet)  

### 5、隐式标签

在emmet下，输入div.item，就会生成`<div class="item"></div>`。

在过去版本中，可以省略掉div，即输入`.item`即可生成`<div class="item"></div>`。现在如果只输入`.item`，则Emmet会根据父标签进行判定。比如在`<ul>`中输入`.item`，就会生成`<li class="item"></li>`。

下面是所有的隐式标签名称：

- li：用于ul和ol中
- tr：用于table、tbody、thead和tfoot中
- td：用于tr中
- option：用于select和optgroup中  


### 6、定义多个元素  

要定义多个元素，可以使用*符号。比如，`ul>li*3`可以生成如下代码：

````
<ul>  
  <li></li>  
  <li></li>  
  <li></li>  
</ul>  
````  

[回到顶部](#emmet)  

### 7、定义多个带属性的元素

如果输入 `ul>li.item$*3`，将会生成如下代码：

````
<ul>  
  <li class="item1"></li>  
  <li class="item2"></li>  
  <li class="item3"></li>  
</ul>  
````  

[回到顶部](#emmet)  

## 二、CSS缩写

### 1、值

比如要定义元素的宽度，只需输入`w100`，即可生成
````
width: 100px;  
````  

除了px，也可以生成其他单位，比如输入`h10p+m5e`，结果如下：

````
height: 10%;  
margin: 5em;  
````

单位别名列表：

- p 表示%  
- e 表示 em
- x 表示 ex    

[回到顶部](#emmet)  

### 2、附加属性

可能你之前已经了解了一些缩写，比如 @f，可以生成：

````
@font-face {  
  font-family:;  
  src:url();  
}  
````  

一些其他的属性，比如background-image、border-radius、font、@font-face,text-outline、text-shadow等额外的选项，可以通过“+”符号来生成，比如输入`@f+`，将生成：

````
@font-face {  
  font-family: 'FontName';  
  src: url('FileName.eot');  
  src: url('FileName.eot?#iefix') format('embedded-opentype'),  
     url('FileName.woff') format('woff'),  
     url('FileName.ttf') format('truetype'),  
     url('FileName.svg#FontName') format('svg');  
  font-style: normal;  
  font-weight: normal;  
}  
````   

[回到顶部](#emmet)  

### 3、模糊匹配

如果有些缩写你拿不准，Emmet会根据你的输入内容匹配最接近的语法，比如输入`ov:h`、`ov-h`、`ovh`和`oh`，生成的代码是相同的：  

````
overflow: hidden;  
````  

[回到顶部](#emmet)  

### 4、供应商前缀

如果输入非W3C标准的CSS属性，Emmet会自动加上供应商前缀，比如输入`trs`，则会生成：

````
-webkit-transform: ;  
-moz-transform: ;  
-ms-transform: ;  
-o-transform: ;  
transform: ;  
````

你也可以在任意属性前加上“-”符号，也可以为该属性加上前缀。比如输入`-super-foo`：

````
-webkit-super-foo: ;  
-moz-super-foo: ;  
-ms-super-foo: ;  
-o-super-foo: ;  
super-foo: ;  
````  

如果不希望加上所有前缀，可以使用缩写来指定，比如`-wm-trf`表示只加上`-webkit`和`-moz`前缀：  

````
-webkit-transform: ;  
-moz-transform: ;  
transform: ;  
````
前缀缩写如下：

- w 表示 -webkit-
- m 表示 -moz-
- s 表示 -ms-
- o 表示 -o-   

[回到顶部](#emmet)  

### 5、渐变

输入`lg(left, #fff 50%, #000)`，会生成如下代码：

````
background-image: -webkit-gradient(linear, 0 0, 100% 0, color-stop(0.5, #fff), to(#000));  
background-image: -webkit-linear-gradient(left, #fff 50%, #000);  
background-image: -moz-linear-gradient(left, #fff 50%, #000);  
background-image: -o-linear-gradient(left, #fff 50%, #000);  
background-image: linear-gradient(left, #fff 50%, #000);  
````
