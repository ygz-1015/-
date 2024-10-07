# CSS是什么

CSS 是“Cascading Style Sheet”的缩写，中文意思为“层叠样式表”，它是一种标准的样式表语言，用于描述网页的表现形式（例如网页元素的位置、大小、颜色等）。

CSS 的主要作用是定义网页的样式（美化网页），对网页中元素的位置、字体、颜色、背景等属性进行精确控制。CSS 不仅可以静态地修饰网页，还可以配合 JavaScript 动态地修改网页中元素的样式，而且市面上几乎所有的浏览器都支持 CSS。

## CSS 的特点

CSS 是 Web 领域的一个突破，它为 HTML 提供了一种描述元素样式的方式，使用 CSS 和 HTML 可以制作出外形优美的网页。总体来说 CSS 具有以下特点：

### 1) 丰富的样式定义

CSS 提供了丰富的外观属性，可以在网页中实现各式各样的效果，例如：

- 为任何元素设置不同的边框，以及边框与元素之间的内外间距；
- 改变文字的大小、颜色、字体，为文字添加修饰（例如下划线、删除线）；
- 为网页设置背景颜色或者背景图片等等。

### 2) 易于使用和修改

CSS 的样式信息不仅可以定义在 HTML 元素的 style 属性中，也可以定义在 HTML 文档 <head> 标签内的 <style> 标签中，还可以定义在专门的 .css 格式的文件中，之后再将其引用到 HTML 文档。

推荐使用最后一种定义方式（定义单独的 .css 格式文件），这样可以将 CSS 样式统一存放，方便后期维护。

### 3) 多页面应用

前面说了可以将 CSS 样式单独存放在一个 .css 格式的文件中，这个文件不属于任何页面，我们可以在不同的页面引用这个 .css 格式的文件，这样就可以统一不同页面的风格。

### 4) 层叠

层叠就是指可以对同一个 HTML 元素多次定义 CSS 样式，后面定义的样式会覆盖前面定义的样式。

例如整个站点引用了同样的 CSS 样式文件，但想要调整其中某个页面的某些元素，这时就可以针对想要调整的元素单独定义一份样式文件并引用到页面中。这样后来单独定义的样式就会覆盖前面的样式，在浏览器同样只会看到最后设置的效果。

### 5) 页面压缩

一个网页其中通常包含大量的 HTML 元素，为了实现某些效果我们往往还需要为这些元素定义样式文件，如果将它们放到一起就会使得我们的 HTML 文档过于臃肿。而将 CSS 样式定义在单独的样式文件中，把 CSS 样式与 HTML 文档分开的话就可以大大减小 HTML 文档的体积，这样浏览器加载 HTML 文档所用的时间也会减少。

另外，CSS 样式可以重复使用，不同的元素可以使用相同的 CSS 样式，这样可以避免定义重复的样式，CSS 样式文件的体积也会相应的减小，从而进一步缩短页面加载的时间。





# CSS语法规则



CSS 样式由一系列规则组成，这些规则由 Web 浏览器解析，然后应用于 HTML 文档相应的元素上。CSS 样式规则由三个部分组成，分别是选择器、属性和值：

- 选择器：由 HTML 元素的 id、class 属性或元素名本身以及一些特殊符号构成，用来指定要为哪个 HTML 元素定义样式，例如选择器`p`就表示为页面中的所有`<p>`标签定义样式；
- 属性：您希望给 HTML 元素设置的样式名称，由一系列关键词组成，例如 color（颜色）、border（边框）、font（字体）等，CSS 中提供了众多属性，您可以通过[ W3C 官网](https://www.w3.org/TR/CSS2/propidx.html)查看；
- 值：由数值和单位或者关键字组成，用来控制某个属性的显示效果，例如 color 属性的值可以是 red 或 #F1F1F1 等。

您可以按照如下图所示的语法规则来定义 CSS 样式：



![1021421050-0](D:\software\Typora\复制的图片文件\1021421050-0.png)
图：CSS语法

通过上图可以看出，在 CSS 的语法规则中，属性和值之间需要使用冒号`:`进行分隔，每个属性和值的组合可以看作一个声明，每个声明的末尾都需要使用分号`;`作为结尾，属于同一选择器的声明需要使用花括号`{ }`包裹起来。

上图的语法示例中：

- 选择器 h1 表示要为网页中所有的`<h1>`标签定义样式；
- 属性 color 表示字体颜色，值 blue 则表示将字体设置为蓝色；
- 属性 text-align 表示文本的对齐方式，值 center 则表示将文本的对齐方式设置为居中对齐。

# CSS选择器

选择器由 HTML 元素的 id、class 属性或元素名本身以及一些特殊符号构成，用来指定要为哪个 HTML 元素定义样式。选择器是 CSS 样式规则中重要的组成部分，我们可以将选择器看作是 CSS 样式与 HTML 元素之间的匹配模式，与选择器关联的样式规则会应用于选择器所指定的 HTML 元素上。CSS 中提供了多种不同类型的选择器，您可以根据自己的喜好来选择使用。

## 1. 通用选择器

通用选择器用星号`*`表示，它不匹配某个特定的 HTML 元素，而是匹配 HTML 文档中的每个元素。在开发中，我们通常使用通用选择器来清除 HTML 元素中默认的内外边距，如下所示：

```css
* {
margin: 0 auto;
padding: 0;
}
```

注意：虽然通用选择器内的样式规则能够应用于 HTML 文档中的每个元素，但并不建议在生产环境中过于频繁地使用通用选择器。正是因为通用选择器会匹配网页上每个元素的特点，频繁的使用会给浏览器带来太多不必要的压力。

## 2. 标签选择器

一个完整的 HTML 文档由各式各样的标签组成，而标签选择器可以通过具体的标签名称来匹配文档内所有同名的标签，如下所示：

```css
p {
color: blue;
}
```

`p`选择器能够匹配文档中所有的`<p>`标签。

## 3. ID 选择器

ID 选择器用来匹配 HTML 文档中具有指定 ID 属性的标签，ID 选择器的定义需要用到井号`#`，后面紧跟 ID 属性的值，如下所示：

```css
#nav {
color: red;
}
```

`#nav`选择器能够匹配文档中具有`id="nav"`属性的标签。

## 4. 类选择器

类选择器可以根据标签的 class 属性匹配具体的 HTML 标签，所有符合条件的标签都会根据选择器内的样式进行格式化。类选择器的定义需要用到一个英文的句号`.`，后面紧跟 class 属性的值，如下所示：

```css
.black {
color: black;
}
```

`.black`选择器能够匹配文档中所有具有`class="black"`属性的标签。

由于 class 属性不是唯一的，可以应用于不同的标签，因此您还可以在定义类选择器时指定具体的标签，如下所示：

```css
p.black {
color: black;
}
```

`p.black`选择器仅会将其中的样式应用到所有具有`class="black"`属性的`<p>`标签中，对于其它的具有`class="black"`属性的标签则没有影响。

另外，一个 HTML 标签中 class 属性可能不止一个，例如：

```css
<p class="info selected"></p>
<p class="info"></p>
```

假如我们要为所有 class 属性包含 info 的元素设置粗体，为所有 class 属性包含 selected 的元素设置红色字体，为 class 属性中既包含 info 又包含 selected 的元素设置蓝色背景，则可以写成下面这样：

```CSS
.info {
font-weight:bold;
}
.selected {
color: red;
}
.info.selected {
background: blue;
}
```

这种由多个 class 属性值所组成的类选择器我们可以称之为“多类选择器”，而前面介绍的由单个 class 属性值定义的类选择器可以称为“单类选择器”。

注意：多类选择器中，多个 class 属性之间是紧挨着的（例如 .info.selected），不需要使用空格分开。

## 5. 后代选择器

当一个`<p>`标签嵌套在一个`<div>`标签内部的时候，就可以将这个`<p>`标签看作是`<div>`标签的后代。当我们需要选择一个标签的后代标签时，就可以使用后代选择器。后代选择器的定义方式就是将标签名、class 属性或 id 属性等按照标签的嵌套关系由外到内的依次罗列，中间使用空格分开，如下所示：

```css
ul li a {
text-decoration: none;
}
```

`ul li a`选择器仅会匹配无序列表`<ul>`标签的所有后代`<a>`标签。

## 6. 子选择器

子选择器与后代选择器类似，不过子选择器只会匹配某个元素的直接后代（元素与其子元素之间只有一层嵌套关系），子选择器由两个或多个选择器组成，选择器之间用大于号`>`分隔开，如下所示：

```css
p > strong {
color:red;
}
```

`p > strong`选择器会将下面代码中第一个`<p>`标签的子标签`<strong>`内的文字设置为红色，但对第二个`<p>`标签中的`<strong>`标签则没有影响。

```css
<p>欢迎访问<strong>编程帮</strong>！</p>
<p><em><strong>编程帮（biancheng.net）</strong></em>，一个在线学习编程的网站，专注于分享优质编程教程。</p>
```

## 7. 相邻兄弟选择器

相邻兄弟选择器用于匹配某个元素之后紧邻的另一个元素，这两个元素拥有同一个父级元素并且不存在嵌套关系。相邻兄弟选择器的定义需要用到加号`+`，加号两边为相邻的两个元素，选择器会匹配加号后面的元素，如下所示：

```css
h1 + p {
color: blue;
font-size: 18px;
}
ul.task + p {
color: #f0f;
text-indent: 30px;
}
```

`h1 + p`选择器会匹配同一父级元素下紧邻`<h1>`标签并在其后的`<p>`标签。`ul.task + p`选择器则会匹配同一父级元素下紧邻`<ul>`标签并在其后的`<p>`标签，但`<ul>`要具有`class="task"`属性。

## 8. 通用兄弟选择器

通用兄弟选择器与相邻兄弟选择器非常相似，但却没有那么严格。通用兄弟选择器同样会匹配同一父级元素下的兄弟元素，但兄弟元素之间无需紧邻。定义通用兄弟选择器需要用到波浪号`~`，波浪号两边为同一父级元素下的两个元素，选择器会匹配波浪号后面的元素，如下所示：

```css
h1 ∼ p {
color: blue;
font-size: 18px;
}
```

`h1 ∼ p`选择器会匹配同一父级元素下`<h1>`标签之后的所有`<p>`标签。

## 9. 分组选择器

分组选择器可以将同样的样式规则应用到多个选择器中，每个选择器之间使用逗号`,`进行分隔，这么做可以避免定义重复的样式规则，最大程度地减少 CSS 样式表中的代码。例如，在 CSS 样式表中，不同的选择器中可能包含同样的样式规则，如下所示：

```css
h1 {
font-size: 36px;
font-weight: normal;
}
h2 {
font-size: 28px;
font-weight: normal;
}
h3 {
font-size: 22px;
font-weight: normal;
}
```

我们可以看到选择器`h1`、`h2`、`h3`中包含相同的样式`font-weight: normal;`，这时就可以先使用分组选择器为`h1`、`h2`、`h3`定义它们之间同样的样式规则，然后再分别定义它们之间不同的样式规则，如下所示：

```css
h1, h2, h3 {
font-weight: normal;
}
h1 {
font-size: 36px;
}
h2 {
font-size: 28px;
}
h3 {
font-size: 22px;
}
```

## 10. 属性选择器

属性选择器用来匹配具有特定属性的元素。属性选择器的定义方式与标签选择器相似，只不过需要在标签的后面使用方括号`[ ]`来指定标签具有的属性信息，如下所示：

```css
input[type="text"] {
color: blue;
}
```

`input[type="text"]`选择器会匹配所有具有`type="text"`属性的`<input>`标签。

属性选择器中方括号`[ ]`内的属性信息还支持以下几种写法：

- [target]：选择所有带有`target`属性元素；
- [target=_blank]：选择所有具有`target="_blank"` 属性的元素；
- [title~=flower]：选择`title`属性包含单词“flower”的所有元素；
- [lang|=en]：选择`lang`属性正好是“en”或以“en”为开头的所有元素。

# CSS注释

在 CSS 中注释以`/*`开头（起始符），以`*/`结尾（结束符），`/*`与`*/`是成对出现的，所有在`/*`与`*/`之间的内容都会被看作注释的内容。CSS 中的注释只有这一种写法，无论是在单行中使用还是跨越多行使用，只要保证注释的内容在`/*`与`*/`之间即可。例如：

```css
/*单行注释*/

/*
  多行注释
*/
```



在 CSS 中添加注释的数量没有限制，您可以在自己认为需要的地方添加注释。但需要注意的是，在 CSS 中注释不能嵌套使用，注释开始符`/*`在遇到第一个注释结束符`*/`后就会结束注释，之后出现的`*/`会被浏览器当作 CSS 样式，这么做的后果就是会导致后续的 CSS 样式无法正常解析。



# CSS长度单位汇总





## 1. 相对长度单位

相对长度单位指的是这个单位没有一个固定的值，它的值受到其它元素属性（例如浏览器窗口的大小、父级元素的大小）的影响，在响应式布局方面相对长度单位非常适用。下表中列举了 CSS 中支持的相对长度单位：



| 单位 |                             描述                             | 示例                  |
| :--: | :----------------------------------------------------------: | --------------------- |
|  em  | 相对于自身 font-size（字体大小）属性的值，如果自身没有设置，则继承父元素 font-size 属性的值，1em 等同于 font-size 属性值，例如 font-size 的值为 16px，那么 1em 就等于 16px，2em 就等于 32px | p{line-height:2em;}   |
| rem  | 相对于根元素`<html>`的 font-size 属性的大小，比如根元素的 font-size 是 100px，那么 1.2rem 就相当于 120px | p{font-size: 1.2rem;} |
|  ex  | 相对于所用字体中小写英文字母 x 的高度，若无法确定 x 的高度则使用 0.5em 计算 | p{font-size: 1ex;}    |
|  ch  | 相对于所用字体中数字 0 的高度，若无法确定 0 的高度则使用 0.5em 计算 | p{line-height: 3ch}   |
|  vw  |         相对于浏览器窗口的宽度，1vw = 窗口宽度的 1%          | p{font-size: 5vw;}    |
|  vh  |         相对于浏览器窗口的高度，1vh = 窗口高度的 1%          | p{font-size: 5vh;}    |
| vmin |                     vw 与 vh 中较小的值                      | p{font-size: 5vmin;}  |
| vmax |                     vw 与 vh 中较大的值                      | p{font-size: 5vmax;}  |
|  %   |              相对于父元素宽度或字体大小的百分比              | div{width: 55%}       |

## 2. 绝对长度单位

绝对长度单位表示一个真实的物理尺寸，它的大小是固定的，不会因为其它元素尺寸的变化而变化。下表中列举了 CSS 中支持的绝对长度单位：



| 单位 |                             描述                             | 示例                 |
| :--: | :----------------------------------------------------------: | -------------------- |
|  cm  |                             厘米                             | p{font-size: 0.5cm;} |
|  mm  |                             毫米                             | p{font-size: 5mm;}   |
|  in  |                 英寸（1in = 96px = 2.54cm）                  | p{font-size: 1in;}   |
|  px  |                     像素（1px = 1/96in）                     | p{font-size: 16px;}  |
|  pt  | point，是一种专用的印刷单位“磅”，也可以称为“点”（1pt = 1/72in） | p{font-size: 16pt;}  |
|  pc  | pica，中文可称为“派卡”，印刷行业用于描述字体大小的单位，相当于我国新四号铅字的尺寸（1pc = 12pt） | p{font-size: 5pc;}   |

# CSS颜色设置（6种方法）

我们在显示屏上看到的各种颜色都是通过红（red）、绿（green）、蓝（blue）三原色组合而成的，按不同的比例混合这三种颜色就可以得到其它颜色，通过调整红、绿、蓝三种颜色的数值可以最大限度的控制颜色。

CSS 中提供了一些属性（例如 color、background）来设置 HTML 元素的颜色（例如元素的背景颜色或字体颜色），我们可以通过不同形式的值来指定颜色，如下表所示：



|     值     |                             描述                             |              实例              |
| :--------: | :----------------------------------------------------------: | :----------------------------: |
|  颜色名称  | 使用颜色名称来设置具体的颜色，比如 red、blue、brown、lightseagreen 等，颜色名称不区分大小写 |          color: red;           |
| 十六进制码 | 使用十六进制码以 #RRGGBB 或 #RGB（比如 #ff0000）的形式设置具体颜色，"#" 后跟 6 位或 3 位十六进制字符（0-9, A-F） |          color: #f03;          |
|    RGB     | 通过 rgb() 函数对 red、green、blue 三原色的强度进行控制，从而实现不同的颜色 |     color: rgb(255,0,51);      |
|    RGBA    | RGBA 扩展了 RGB，在 RGB 的基础上增加了 alpha 通道来设置颜色的透明度，需要使用 rgba() 函数实现 |   color: rgba(255,0,0,0.1);    |
|    HSL     | 通过 hsl() 函数对颜色的色调、饱和度、亮度进行调节，从而实现不同的颜色 |   color: hsl(120,100%,25%);    |
|    HSLA    | HSLA 扩展了 HSL，在 HSL 的基础上增加了 alpha 通道来设置颜色的透明度，需要使用 hsla() 函数实现 | color: hsla(240,100%,50%,0.5); |

## 1. 颜色名称

使用颜色名称来设置颜色是最简单的方法。CSS 中定义了一些表示颜色的关键字，如下表中所示，使用这些关键字可以轻松的为元素设置颜色。



| 颜色名 |  颜色  | 颜色名  |  颜色  |
| :----: | :----: | :-----: | :----: |
|  aqua  |  天蓝  |  black  |  黑色  |
|  blue  |  蓝色  | fuchsia |  品红  |
|  gray  |  灰色  |  green  |  绿色  |
|  lime  |  浅绿  | maroon  | 紫红色 |
|  navy  |  深蓝  |  olive  | 橄榄色 |
| orange |  橙色  | purple  |  紫色  |
|  red   |  红色  | silver  | 浅灰色 |
|  teal  | 蓝绿色 |  white  |  白色  |
| yellow |  黄色  |         |        |

除了上表中介绍的 17 个颜色外，浏览器中还支持很多的颜色名称，但不同的浏览器之间对颜色的解析可能存在差异，为了安全起见，不建议您在 CSS 中使用颜色名称来指定颜色。

## 2. 十六进制码

十六进制码是指通过一个以`#`开头的 6 位十六进制数（0~9，a~f）表示颜色的方式，这个六位数可以分为三组，每组两位，依次表示 red、green、blue 三种颜色的强度，例如：

```css
h1 {
color: #ffa500;
}
p {
color: #00ff00;
}
```

您可以使用 PhotoShop、Fireworks 等制图软件来获取颜色的十六进制码，如下图所示：



![110021F55-0](D:\software\Typora\复制的图片文件\110021F55-0.gif)
图：获取颜色的十六进制码

提示：在使用十六进制码表示颜色时，如果每组的两个十六进制数是相同的，例如 #00ff00、#ffffff、#aabbcc，则可以将它们简写为 #0f0、#fff、#abc。

## 3. RGB

RGB 是 red、green、blue 的缩写，它是一种色彩模式，可以通过对 red、green、blue 三种颜色的控制来实现各式各样的颜色。CSS 中要使用 RGB 模式来设置颜色需要借助 rgb() 函数，函数的语法格式如下：

rgb(red, green, blue)

其中 red、green、blue 分别表示三原色红、绿、蓝的强度，这三个参数的取值可以是 0~255 之间的整数，也可以是 0%~100% 之间百分比数值。如下例所示：

```css
h1 {
color: rgb(255, 165, 0);
}
p {
color: rgb(0%, 100%, 0%);
}
```

## 4. RGBA

RGBA 是 RGB 的扩展，在 RGB 的基础上又增加了对 Alpha 通道的控制，Alpha 通道可以设置颜色的透明度。

您需要借助 rgba() 函数来使用 RGBA 模式，该函数需要接收四个参数，除了 red、green、blue 三种颜色的强度外，还需要一个 0~1 之间的小数来表示颜色的透明度，其中 0 表示完全透明，1 表示完全不透明。rgba() 函数的语法格式如下：

rgba(red, green, blue, alpha);

其中 red、green、blue 分别表示三原色红、绿、蓝的强度，alpha 表示颜色的透明度，例如：

```css
h1 {
color: rgba(255, 0, 0, 0.5);
}
p {
color: rgba(0, 255, 0, 1);
}
```

## 5. HSL

HSL 是 Hue（色调）、Saturation（饱和度）、Lightness（亮度）的缩写，它同样也是一种色彩模式，可以通过对色调、饱和度、亮度三个属性的调节来实现不同颜色的。CSS 中使用 HSL 模式需要借助 hsl() 函数，函数的语法格式如下：

```css
hsl(hue, saturation, lightness)
```

语法说明如下：

### 1) hue

参数 hue 表示颜色在色盘上的度数（从 0 到 360），0 或 360 表示红色，120 表示绿色，240 表示蓝色，如下图所示；



!![110021E53-1](D:\software\Typora\复制的图片文件\110021E53-1.jpg)
图：hue参数说明

### 2) saturation

参数 saturation 为一个百分比数值，表示色彩的饱和度，0% 表示灰色，100% 表示全彩。



![110021M00-2](D:\software\Typora\复制的图片文件\110021M00-2.gif)
图：saturation 参数说明

### 3) lightness

参数 lightness 同样为一个百分比数值，表示颜色的亮度，0% 是黑色（没有亮度），50% 为最合适的亮度（既不发黑也不过亮），100% 是白色（曝光严重）。



![110021F05-3](D:\software\Typora\复制的图片文件\110021F05-3.gif)
图：lightness 参数说明

## 6. HSLA

HSLA 是 HSL 的扩展，在 HSLA 中增加了对颜色透明度的控制，其余与 HSL 相同。CSS 中使用 HSLA 模式需要借助 hsla() 函数，函数的语法格式如下：

```css
hsla(hue, saturation, lightness, alpha)
```

参数 alpha 是一个 0 ~ 1 之间小数，用来表示颜色的透明度，0 表示完全透明，而 1 表示完全不透明。

【示例】通过不同的方式来为 HTML 元素设置颜色：

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS颜色</title>
        <style>
         p {
             font-size: 16px;
             font-weight: bold;
            }
            #rgb {
                color: rgb(255, 0, 0);
            }
            #rgba {
                color: rgba(255, 0, 0, 0.5);
            }
            #hex {
                color: #EE82EE;
            }
            #short {
                color: #E8E;
            }
            #hsl {
                color: hsl(0, 50%, 50%);
            }
            #hsla {
                color: hsla(0, 50%, 50%, 0.5);
            }
            #built {
                color: green;
            }
        </style>
    </head>
    <body>
        <p id="rgb">
            color: rgb(255, 0, 0);
        </p>
        <p id="rgba">
            color: rgba(255, 0, 0, 0.5);
        </p>
        <p id="hex">
            color: #EE82EE;
        </p> 
        <p id="short">
            color: #E8E;
        </p>
        <p id="hsl">
            color: hsl(0, 50%, 50%);
        </p>
        <p id="hsla">
            color: hsla(0, 50%, 50%, 0.5);
        </p>
        <p id="built">
            color: green;
        </p>
    </body>
</html>
```

运行结果如下图所示：



![1100211U5-4](D:\software\Typora\复制的图片文件\1100211U5-4.gif)
图：CSS 中颜色的设置



# CSS background（背景）

在制作网页时我们往往需要在网页中添加一些背景颜色、背景图像让网页更加美观，吸引访问者的眼球。CSS 中提供了一系列用于设置 HTML 元素背景效果的属性，如下所示：

- background-color：设置元素的背景颜色；
- background-image：设置元素的背景图像；
- background-repeat：控制背景图像是否重复；
- background-attachment：控制背景图像是否跟随窗口滚动；
- background-position：控制背景图像在元素中的位置；
- background-size：设置背景图像的尺寸；
- background-origin：设置 background-position 属性相对于什么位置来定位背景图像；
- background-clip：设置背景图像的显示区域；
- background：背景属性的缩写，可以在一个声明中设置所有的背景属性。

## 1. background-color

您可以使用 background-color 属性为元素设置一个背景颜色，该属性支持以下几种属性值：



| 值          | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| color_name  | 使用具体颜色名称为元素设置背景颜色（例如 red）               |
| hex_number  | 使用十六进制码为元素设置背景颜色（例如 #ff0000）             |
| rgb_number  | 使用 rgb() 函数为元素设置背景颜色（例如 rgb(255,0,0)）       |
| transparent | 默认值，设置背景颜色为透明，大多数情况下我们并不会用到它。但如果您不希望某个元素拥有背景颜色，或者不希望用户对浏览器的设置（比如开启夜间模式、护眼模式）影响到您的设计，那么就可以使用 transparent 来将颜色设置为透明的 |
| inherit     | 从父元素继承对背景颜色的设置                                 |

【示例】使用 background-color 为元素设置背景颜色：

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS背景</title>
        <style>
            #bg {
                color: white;
                background-color: blue;
                margin: 20px;
                /*设置外边距为 20px*/
                padding: 20px;
                /*设置内边距为 20px*/
                border: 10px dotted yellow;
                /*设置一个宽 10px 的黄色虚线边框*/
            }
        </style>
    </head>
    <body>
        <p id="bg">background-color 属性</p>
    </body>
</html>
```



运行结果如下图所示：



![background-color 属性演示](D:\software\Typora\复制的图片文件\110425J21-0.gif)
图：background-color 属性演示

通过运行结果可以看出 background-color 属性能够为元素设置一种纯色的背景，这种颜色会填充元素的内容、内边距以及边框区域（也可以理解为边框及以内的所有区域），对于元素边框以外的区域（外边距）则没有影响。



## 2. background-image

background-image 用来为某个元素设置背景图像，默认情况下浏览器会从元素内容的左上角开始（若有内边距则从元素内边距区域的左上角开始），在水平和垂直方向上重复背景图像，以填充整个元素区域，您可以使用 background-repeat 属性来控制背景图像是否重复或如何重复。

background-image 属性的可选值如下：



|     值     |                             描述                             |
| :--------: | :----------------------------------------------------------: |
| url('URL') | 指向图像的路径，可以将 url() 看作是一个函数，括号中的 URL 为图像的具体路径 |
|    none    |                    默认值，不显示背景图像                    |
|  inherit   |                  从父元素继承背景图像的设置                  |

【示例】使用 background-image 属性将图片【![img](D:\software\Typora\复制的图片文件\1104253M8-1.gif)】设置为元素的背景图像：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        color: red;
        background-image: url('./bg-image.png');
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background-image 属性</p>
</body>
</html>
```



运行结果如下图所示：



![background-image 属性演示](D:\software\Typora\复制的图片文件\1104251357-2.gif)
图：background-image 属性演示

背景图像的覆盖区域与背景颜色相同，同样会填充元素的内容、内边距以及边框区域，对于元素边框以外的区域（外边距）则没有影响。

## 3. background-repeat

默认情况下背景图像会从元素内容的左上角开始（若有内边距则从元素内边距区域的左上角开始），在水平和垂直方向上重复背景图像以填充整个元素区域（不包括元素的外边距区域），您可以使用 background-repeat 属性用来设置背景图像是否重复或如何重复，该属性的可选值如下：



|    值     |                     描述                     |
| :-------: | :------------------------------------------: |
|  repeat   | 默认值，背景图像将在垂直方向和水平方向上重复 |
| repeat-x  |          背景图像仅在水平方向上重复          |
| repeat-y  |          背景图像仅在垂直方向上重复          |
| no-repeat |    背景图像仅显示一次，不在任何方向上重复    |
|  inherit  |  从父元素继承 background-repeat 属性的设置   |

【示例】使用 background-repeat 属性让背景图像只在水平方向上重复：



```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        color: black;
        background-image: url('./bg-image.png');
        background-repeat: repeat-x;
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background-repeat 属性</p>
</body>
</html>
```

运行结果如下图所示：



![background-repeat 属性演示](D:\software\Typora\复制的图片文件\1104254007-3.gif)
图：background-repeat 属性演示



## 4. background-position

background-position 属性用来设置背景图像的起始位置，该属性的可选值如下：



| 值                                                           |                             描述                             |
| :----------------------------------------------------------- | :----------------------------------------------------------: |
| left top（左上）、<br /> left center（左中）、<br /> left bottom（左下）、<br /> right top（右上）、<br /> right center（右中）、<br /> right bottom（右下）、<br /> center top（中上）、<br /> center center（居中）、<br /> center bottom（中下） | 使用一些关键词表示背景图像的位置，如果您仅设置第一个关键词，那么第二个将默认为 center |
| x% y%                                                        | 使用百分比表示背景图像距离元素左上角的距离，x% 为水平方向，y% 为垂直方向，左上角为 0% 0%，右下角是 100% 100%，如果您仅设置第一个值，那么另一个值将是 50%，默认值为 0% 0% |
| xpos ypos                                                    | 使用像素（px）或者其它 CSS 单位表示背景图像距离元素左上角的距离，xpos 为水平方向，ypos 为垂直方向，左上角为 0px 0px，右下角视元素的尺寸而定，百分比和单位的形式可以混用，如果您仅设置第一个值，那么另一个值将默认为 50% |

【示例】使用 background-position 属性来设置背景图像的位置：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        color: black;
        background-image: url('./bg-image.png');
        background-repeat: no-repeat;
        background-position: 0% 50%;
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background-position 属性</p>
</body>
</html>
```



运行结果如下图所示：



![background-position 属性演示](D:\software\Typora\复制的图片文件\1104252619-4.gif)
图：background-position 属性演示

## 5. background-attachment

background-attachment 属性用来设置背景图像是固定在某个位置还是跟随页面一起滚动，该属性的可选值如下：



|   值    |                     描述                      |
| :-----: | :-------------------------------------------: |
| scroll  |   默认值，背景图像随着页面元素的滚动而移动    |
|  fixed  |   当页面的其余部分滚动时，背景图像固定不动    |
| inherit | 从父元素继承 background-attachment 属性的设置 |

【示例】使用 background-attachment 属性将背景图像固定在屏幕的顶部：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    body {
        background-image: url('./bg-image.png');
        background-repeat: repeat-x;
        background-attachment: fixed;
    }
    </style>
</head>
<body>
    <p>background-position 属性</p>
    <p>background-position 属性</p>
    <p>background-position 属性</p>
    <p>background-position 属性</p>
    <p>background-position 属性</p>
    <p>background-position 属性</p>
</body>
</html>
```



运行结果如下图所示：



![background-attachment 属性演示](D:\software\Typora\复制的图片文件\1104255K9-5.gif)
图：background-attachment 属性演示

## 6. background-size

background-size 属性用来设置背景图像的尺寸，该属性的可选值如下：



|    值     |                             描述                             |
| :-------: | :----------------------------------------------------------: |
| xpos ypos | 使用像素（px）或其它 CSS 单位来设置背景图像的高度和宽度，xpos 表示宽度，ypos 表示高度，如果只设置第一个值，那么第二个值将被设置为默认值 auto（自动） |
|   x% y%   | 使用百分比表示背景图像相对于所在元素宽度与高度的百分比，x% 表示宽度，y% 表示高度，如果只设置第一个值，那么第二个值将被设置为默认值 auto（自动） |
|   cover   | 保持背景图像的横纵比例并将图像缩放至足够大，使背景图像可以完全覆盖元素所在的区域，这么做可能会导致背景图像的某些部分超出元素区域而无法显示 |
|  contain  | 保持背景图像的横纵比例并将图像缩放至足够大，使背景图像可以完整的显示在元素所在区域，背景图像可能无法完全覆盖整个元素区域 |

【示例】使用 background-size 属性设置背景图像的尺寸，并将背景图像横向铺满整个元素区域：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    body {
        background-image: url('./bg-image.png');
        background-repeat: repeat-x;
        background-size: contain;
    }
    </style>
</head>
<body>
    <p>background-size 属性</p>
</body>
</html>
```

运行结果如下图所示：



![background-size 属性演示](D:\software\Typora\复制的图片文件\1104255293-6.gif)
图：background-size 属性演示

## 7. background-origin

background-origin 是 CSS3 中新增的属性。在使用 background-position 属性来设置背景图像的位置时，默认是以元素左上角的位置来计算的。您还可以使用 background-origin 属性来设置 background-position 属性相对哪个位置来定位背景图像，background-origin 属性的可选值如下：



|     值      |                 描述                 |
| :---------: | :----------------------------------: |
| padding-box | 相对于元素的内边距区域来定位背景图像 |
| border-box  |  相对于元素的边框区域来定位背景图像  |
| content-box |  相对于元素的内容区域来定位背景图像  |

【示例】使用 background-origin 属性设置背景图像相对于元素的边框区域来定位：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        color: black;
        background-image: url('./bg-image.png');
        background-repeat: no-repeat;
        background-origin: border-box;
        background-position: 5px 5px;
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background-origin 属性</p>
</body>
</html>
```

运行结果如下图所示：



![background-origin 属性演示](D:\software\Typora\复制的图片文件\1104251225-7.gif)
图：background-origin 属性演示

## 8. background-clip

background-clip 是 CSS3 中新增的属性，通过它可以设置背景图像的显示区域。background-clip 属性的可选值如下：



|     值      |                    说明                    |
| :---------: | :----------------------------------------: |
| border-box  | 默认值，在元素边框及以内的区域显示背景图像 |
| padding-box |    在元素内边距及以内的区域显示背景图像    |
| content-box |         在元素内容区域显示背景图像         |

【示例】通过 background-clip 属性设置背景图像仅在元素内容区域显示：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        background-image: url('./bg-image.png');
        background-clip: content-box;
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background-clip 属性</p>
</body>
</html>
```

运行结果如下图所示：



![background-clip 属性演示](D:\software\Typora\复制的图片文件\1104252L8-8.gif)
图：background-clip 属性演示

## 9. background

background 是背景属性的简写形式，通过它不仅可以为元素设置某个背景属性，还可以同时设置多个或者所有的背景属性。在设置多个背景属性时并没有固定的顺序，但推荐使用如下顺序进行设置：

background-color || background-image || background-position [/ background-size]? || background-repeat || background-attachment || background-origin || background-clip

在设置多个背景属性时，有以下几点需要注意：

- 每个属性之间使用空格进行分隔；
- 如果同时设置 background-position 和 background-size 属性，这两个属性之间需要使用斜线`/`分隔，并且需要遵循 background-position 属性在前 background-size 属性在后的顺序；
- 如果同时设置 background-origin 和 background-clip 属性，需要遵循 background-origin 属性在前 background-clip 属性在后的顺序。如果 background-origin 与 background-clip 属性的值相同，则可以只设置一个值。

【示例】通过 background 同时设置多个背景属性：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    #bg {
        background: #ccc url('./bg-image.png') 0px 0px/contain repeat-x border-box;
        margin: 20px;   /*设置外边距为 20px*/
        padding: 20px;  /*设置内边距为 20px*/
        border: 10px dotted red;  /*设置一个宽 10px 的红色虚线边框*/
    }
    </style>
</head>
<body>
    <p id="bg">background 属性</p>
</body>
</html>
```

运行结果如下图所示：



![background 属性演示](D:\software\Typora\复制的图片文件\110425OI-9.gif)
图：background 属性演示

background 属性还支持设置多组属性值（比如上面示例中的`#ccc url('./bg-image.png') 0px 0px/contain repeat-x border-box`就可以看作是一组属性），每组属性值之间使用逗号`,`分隔。但需要注意的是 background-color 属性不能设置多个，并且只能在最后一组属性值中设置。

如果设置的多组属性中，背景图像之间存在重叠，那么前面设置的背景图像会覆盖在后面的背景图像之上。示例代码如下：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS背景</title>
    <style>
    body {
        background: url("./css.png") 10px 10px/60px 60px no-repeat padding-box,
                    url("./css.png") 50px 30px/120px 120px no-repeat content-box,
                    url("./css.png") 140px 40px/200px 100px no-repeat content-box #58a;
    }
    </style>
</head>
<body>
</body>
</html>
```

运行结果如下图所示：



![多重背景层叠效果 ](D:\software\Typora\复制的图片文件\1104253K6-10.gif)
图：多重背景层叠效果 



# CSS字体样式（font）



字体设置也是网页设计中的重要组成部分，合适的字体不仅会使页面更加美观，也可以提升用户体验。CSS 中提供了一系列用于设置文本字体样式的属性，比如更改字体，控制字体大小和粗细等等。

- font-family：设置字体；
- font-style：设置字体的风格，例如倾斜、斜体等；
- font-weight：设置字体粗细；
- font-size：设置字体尺寸；
- font-variant：将小写字母转换为小型大写字母；
- font-stretch：对字体进行伸缩变形（使用较少，并且主流浏览器都不支持）；
- font：字体属性的缩写，可以在一个声明中设置多个字体属性。

## 1. font-family

font-family 属性用来设置元素内文本的字体。由于字体的种类成千上万，而且有些还不是免费的，因此我们的电脑上几乎不可能拥有所有的字体。为了最大程度的保证我们设置的字体能够正常显示，可以通过 font-family 属性定义一个由若干字体名称组成的列表，字体名称之间使用逗号`,`分隔，浏览器会首先尝试列表中的第一个字体，如果不支持则尝试下一个，以此类推。

font-family 属性的可选值如下：



|              值              |                             描述                             |
| :--------------------------: | :----------------------------------------------------------: |
| family-name、 generic-family | family-name：字体名称，一个字体名称就代表一种字体，比如“微软雅黑”就是一种字体； generic-family：字体族，也就是某种类型的字体组合，一个字体族代表一种类型的字体，其中包含很多相似但又不同的字体，比如“sans-serif”就是一种无衬线字体，其中包含很多种相似的字体。 字体的默认值取决于浏览器设置 |
|           inherit            |                    从父元素继承字体的设置                    |

下表中列举了一些常用的字体族（generic-family）：



|   字体族   |                             说明                             |                             字体                             |
| :--------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|   serif    |     有衬线字体，即在文字笔画的结尾添加特殊的装饰线或衬线     | "Lucida Bright"、"Lucida Fax"、Palatino、"Palatino Linotype"、Palladio、"URW Palladio"、serif |
| sans-serif |            无衬线字体，即在文字笔画结尾处是平滑的            | "Open Sans"、"Fira Sans"、"Lucida Sans"、"Lucida Sans Unicode"、"Trebuchet MS"、"Liberation Sans"、"Nimbus Sans L"、sans-serif |
| monospace  |             等宽字体，即每个文字的宽度都是相同的             | "Fira Mono"、"DejaVu Sans Mono"、Menlo、Consolas、"Liberation Mono"、Monaco、"Lucida Console"、monospace |
|  cursive   | 草书字体，该字体有连笔或者特殊的斜体效果，会给人一种手写的感觉 | "Brush Script MT"、"Brush Script Std"、"Lucida Calligraphy"、"Lucida Handwriting"、"Apple Chancery"、cursive |
|  fantasy   |                    具有特殊艺术效果的字体                    | Papyrus、Herculanum、"Party LET"、"Curlz MT"、Harrington、fantasy |

【示例】使用 font-family 属性为 HTML 元素设置字体样式：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
        body {
            font-family: "Lucida Calligraphy", cursive, serif, sans-serif;
        }
    </style>
</head>
<body>
    <h1>font-family 属性</h1>
</body>
</html>
```

运行结果如下图所示：



![font-family 属性演示](D:\software\Typora\复制的图片文件\11093QB4-0.gif)
图：font-family 属性演示

注意：如果字体族或字体名称中包含空格或多个单词，则必须将它们使用引号包裹起来，例如"Times New Roman"、"Courier New"、"Segoe UI" 等，如果是在元素的 style 属性中使用则必须使用单引号。

在网页设计中最常用的字体族是 serif 和 sans-serif，因为它们适合阅读。在显示一些程序代码是通常使用等宽字体，这样可以使用程序代码看起来更加工整。



## 2. font-style

font-style 属性用来设置字体的样式，例如斜体、倾斜等，该属性的可选值如下：



|   值    |            描述            |
| :-----: | :------------------------: |
| normal  | 默认值，文本以正常字体显示 |
| italic  |       文本以斜体显示       |
| oblique |        文本倾斜显示        |
| inherit |    从父元素继承字体样式    |

【示例】使用 font-style 属性设置字体的样式：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
        body {
            font-style: oblique;
        }
        .normal {
            font-style: normal;
        }
        .italic {
            font-style: italic;
        }
        .oblique {
            font-style: oblique;
        }
        .inherit {
            font-style: inherit;
        }
    </style>
</head>
<body>
    <p class="normal">normal：显示一个标准的字体</p>
    <p class="italic">italic：显示一个斜体的字体</p>
    <p class="oblique">oblique：显示一个倾斜的字体</p>
    <p class="inherit">inherit：从父元素继承字体样式</p>
</body>
</html>
```



运行结果如下图所示：



![font-style 属性演示](D:\software\Typora\复制的图片文件\11093V450-1.gif)
图：font-style 属性演示

乍看之下，您可能觉得 italic 和 oblique 的效果是一样的。其实不然，italic 显示的字体的斜体版本，而 oblique 则只是一个倾斜的普通字体。

## 3. font-weight

font-weight 属性能够设置字体的粗细，可选值如下：



|                     值                      |                             描述                             |
| :-----------------------------------------: | :----------------------------------------------------------: |
|                   normal                    |                       默认值，标准字体                       |
|                    bold                     |                           粗体字体                           |
|                   bolder                    |                          更粗的字体                          |
|                   lighter                   |                          更细的字体                          |
| 100、200、300、400、500、600、700、800、900 | 由细到粗的设置字体粗细，100 为最细的字体，400 等同于 normal，700 等同于 bold |
|                   inherit                   |                    从父元素继承字体的粗细                    |

【示例】使用 font-weight 属性设置字体粗细：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
    p.weight-100 {
        font-weight: 100;
    }
    p.weight-200 {
        font-weight: 200;
    }
    p.normal {
        font-weight: normal;
    }
    p.bold {
        font-weight: bold;
    }
    p.bolder {
        font-weight: bolder;
    }
    </style>
</head>
<body>
    <p class="weight-100">font-weight: 100;</p>
    <p class="weight-200">font-weight: 200;</p>
    <p class="normal">font-weight: normal;</p>
    <p class="bold">font-weight: bold;</p>
    <p class="bolder">font-weight: bolder;</p>
</body>
</html>
```

运行结果如下图所示：



![font-weight 属性演示](D:\software\Typora\复制的图片文件\11093U324-2.gif)
图：font-weight 属性演示

## 4. font-size

font-size 属性用来设置字体的大小（字号），可选值如下：



|                             值                             |                             描述                             |
| :--------------------------------------------------------: | :----------------------------------------------------------: |
| xx-small、x-small、small、medium、large、x-large、xx-large | 以关键字的形式把字体设置为不同的大小，从 xx-small 到 xx-large 依次变大，默认值为 medium |
|                          smaller                           |               为字体设置一个比父元素更小的尺寸               |
|                           larger                           |               为字体设置一个比父元素更大的尺寸               |
|                           length                           |  以数值加单位的形式把字体设置为一个固定尺寸，例如 18px、2em  |
|                             %                              |      以百分比的形式为字体设置一个相对于父元素字体的大小      |
|                          inherit                           |                    从父元素继承字体的尺寸                    |

【示例】使用 font-size 属性设置字体的大小：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
        .xx_small {
            font-size: xx-small;
        }
        .x_small {
            font-size: x-small;
        }
        .small {
            font-size: x-small;
        }
        .medium {
            font-size: x-small;
        }
        .large {
            font-size: large;
        }
        .x-large {
            font-size: x-large;
        }
        .xx-large {
            font-size: xx-large;
        }
        .smaller {
            font-size: smaller;
        }
        .larger {
            font-size: larger;
        }
        .font-20 {
            font-size: 20px;
        }
    </style>
</head>
<body>
    <p class="xx_small">将字体大小设置为：xx-small</p>
    <p class="x_small">将字体大小设置为：x-small</p>
    <p class="small">将字体大小设置为：x-small</p>
    <p class="medium">将字体大小设置为：medium</p>  
    <p class="large">将字体大小设置为：large</p>   
    <p class="x-large">将字体大小设置为：x-large</p>   
    <p class="xx-large">将字体大小设置为：xx-large</p>   
    <p class="smaller">将字体大小设置为：smaller</p>   
    <p class="larger">将字体大小设置为：larger</p>
    <p class="font-20">将字体大小设置为 20 像素</p> 
</body>
</html>
```



运行结果如下图所示：



![font-size 属性演示](D:\software\Typora\复制的图片文件\11093S0P-3.gif)
图：font-size 属性演示

## 5. font-variant

font-variant 属性可以将文本中的小写英文字母转换为小型大写字母（转换后的大写字母与转换前小写字母的大小相仿，所以称之为小型大写字母）。font-variant 属性的可选值如下：



|     值     |                   描述                   |
| :--------: | :--------------------------------------: |
|   normal   |    默认值，浏览器会显示一个标准的字体    |
| small-caps | 将文本中的小写英文字母转换为小型大写字母 |
|  inherit   |    从父元素继承 font-variant 属性的值    |

【示例】使用 font-variant 属性设置小型大写字母：



```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
        .normal {
            font-variant: normal
        }
        .small {
            font-variant: small-caps
        }
    </style>
</head>
<body>
    <p class="normal">This is a paragraph</p>
    <p class="small">This is a paragraph</p>
</body>
</html>
```

运行结果如下图所示：



![font-variant 属性演示](D:\software\Typora\复制的图片文件\11093T4b-4.gif)
图：font-variant 属性演示

## 6. font

font 属性与前面介绍的 background 属性的功能类似，通过 font 属性可以同时设置多个字体属性，不同的是，使用 font 属性需要遵循以下顺序：

font：[[font-style||font-variant||font-weight||font-stretch]?font-size[ /line-height]?font-family] | caption | icon | menu | message-box | small-caption | status-bar

在使用 font 属性时，有以下几点需要注意：

- 使用 font 属性时必须按照如上所示的顺序，并且 font-size 和 font-family 两个属性不可忽略；
- font 属性中的每个参数仅允许设置一个值，除 font-size 和 font-family 属性外，被忽略的属性将被设置为各自的默认值；
- 若要定义 line-height 属性，则需要使用斜线`/`将 font-size 和 line-height 属性分开。

【示例】使用 font 属性同时定义多个字体效果：

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS字体</title>
    <style>
    p.info {
        font: italic bold 12px/30px arial, sans-serif;
    }
    </style>
</head>
<body>
    <p>使用 font 属性需要遵循以下顺序：</p>
    <p class="info">font：[[font-style||font-variant||font-weight||font-stretch]?font-size[ /line-height]?font-family] | caption | icon | menu | message-box | small-caption | status-bar</p>
</body>
</html>
```



运行结果如下图所示：



![font 属性演示](D:\software\Typora\复制的图片文件\11093R4C-5.gif)
图：font 属性演示



# CSS文本格式化

通过 CSS 中的文本属性您可以像操作 Word 文档那样定义网页中文本的字符间距、对齐方式、缩进等等，CSS 中常用的文本属性如下所示：

- text-align：设置文本的水平对齐方式；
- text-decoration：设置文本的装饰；
- text-transform：设置文本中英文的大小写转换方式；
- text-indent：设置文本的缩进方式；
- line-height：设置行高；
- letter-spacing：设置字符间距；
- word-spacing：设置单词与单词之间的间距（对中文无效）；
- text-shadow：设置文本阴影；
- vertical-align：设置文本的垂直对齐方式；
- white-space：设置文本中空白的处理方式；
- direction：设置文本方向。

## 1. text-align

text-align 属性用来设置元素中文本的水平对齐方式，属性的可选值如下：



| 值      | 描述                             |
| ------- | -------------------------------- |
| left    | 默认值，左对齐                   |
| right   | 右对齐                           |
| center  | 居中对齐                         |
| justify | 两端对齐                         |
| inherit | 从父元素继承 text-align 属性的值 |

当 text-align 设置为 justify 时，将拉伸每一行文本（增加字符之间的间距），以使每行文本具有相同的宽度（最后一行除外），这种对齐方式通常用于出版物，例如杂志和报纸。需要特别注意的是，如果元素中的文本不足一行时，是无法实现两端对齐的（默认会以左对齐的效果显示）。只有当元素中的文本足够长，并且在元素中发生了自动换行时，才会将除最后一行以外的文本实现两端对齐。

## 2. text-decoration

text-decoration 属性用于设置或删除文本的装饰，最常用的做法就是使用 text-decoration 属性来删除`<a>`标签的默认下划线。当然了，使用 text-decoration 属性也可以在需要的地方为元素中的文本添加一些装饰，达到突出显示的效果。

text-decoration 属性的可选值如下：



| 值           | 描述                                                       |
| ------------ | ---------------------------------------------------------- |
| none         | 默认值，标准文本，没有额外装饰，可以用来删除已有的文本装饰 |
| underline    | 在文本下方添加一条下滑线                                   |
| overline     | 在文本上方添加一条上滑线                                   |
| line-through | 在文本的中间定义一条横向贯穿文本的线（类似于删除线）       |
| blink        | 定义闪烁的文本（目前主流浏览器不再支持）                   |
| inherit      | 从父元素继承 text-decoration 属性的值                      |

## 3. text-transform

text-transform 属性用来控制文本中英文字母的大小写，通过该属性您可以在不修改原文的基础上，将文本中的英文统一更改为小写字母、大写字母或者首字母大写的形式。

text-transform 属性的可选值如下：



| 值         | 描述                                         |
| ---------- | -------------------------------------------- |
| none       | 默认值，以原文显示，对文本中的英文不做更改   |
| capitalize | 将文本中的每个单词更改为以大写字母开头的形式 |
| uppercase  | 将文本中的英文字母全部更改为大写             |
| lowercase  | 将文本中的英文字母全部更改为小写             |
| inherit    | 从父元素继承 text-transform 属性的值         |

## 4. text-indent

text-indent 属性用来为元素中的文本添加首行缩进的效果，属性的可选值如下：



| 值      | 描述                                                       |
| ------- | ---------------------------------------------------------- |
| length  | 以固定的值加单位的形式（例如 2em）定义缩进距离，默认值为 0 |
| %       | 以基于父元素宽度的百分比来定义缩进距离                     |
| inherit | 从父元素继承 text-indent 属性的值                          |

提示：不论是使用具体的值还是使用百分比的形式，都可以设置为负值，但这么做可能会造成文本内容溢出元素区域。

注意：文本是从左侧还是从右侧缩进取决于 direction 属性定义的文本方向。

## 5. line-height

line-height 属性用来设置文本的行高，属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| normal  | 默认值，使用默认的行高，不对行高进行额外设置                 |
| number  | 以具体的数字设置行高，这个数字会与当前的字体大小相乘，并将得到的值设置为行高 |
| length  | 以数字加单位的形式设置固定的行高                             |
| %       | 以百分比的形式设置基于当前字体尺寸百分比的行高               |
| inherit | 从父元素继承 line-height 属性的值                            |

## 6. letter-spacing

letter-spacing 属性用来设置字符之间的间距，属性的可选值如下：



| 值      | 描述                                                     |
| ------- | -------------------------------------------------------- |
| normal  | 默认值，表示字符之间没有额外的间距                       |
| length  | 以数值加单位的形式设置字符之间的固定间距（允许使用负值） |
| inherit | 从父元素继承 letter-spacing 属性的值                     |

## 7. word-spacing

word-spacing 属性用来设置单词与单词之间的间距，但对中文无效，属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| normal  | 默认值，表示单词与单词之间没有额外的间距                     |
| length  | 以数值加单位的形式设置单词与单词之间的固定间距（允许使用负值） |
| inherit | 从父元素继承 word-spacing 属性的值                           |

## 8. text-shadow 

text-shadow 属性用来为文本添加阴影及模糊效果，属性的语法格式如下：

text-shadow: h-shadow v-shadow blur color;

语法说明如下：

- h-shadow：必填值，设置阴影的水平位置，允许为负值；
- v-shadow：必填值，设置阴影的垂直位置，允许为负值；
- blur：可选值，设置模糊的距离；
- color：可选值，设置阴影的颜色。

注意：text-shadow 属性可以设置一个或多个阴影效果，只需要将每组的值使用逗号`,`分隔即可（类似于 background 属性的用法）。

## 9. vertical-align

vertical-align 属性用来定义元素内文本的垂直对齐方式，属性的可选值如下：



| 值          | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| baseline    | 默认值，将元素的基线与父元素的基线对齐                       |
| sub         | 下标对齐，将元素的基线相对于父元素的基线降低                 |
| super       | 上标对齐，将元素的基线相对于父元素的基线升高                 |
| top         | 顶部对齐，将元素行内框的顶端与行框的顶端对齐                 |
| text-top    | 文本顶部对齐，把元素的顶端与父元素字体的顶端对齐             |
| middle      | 居中对齐，通常使用在图片上，将图片垂直方向的中线与文本的中线（文字元素行内框的中线）对齐 |
| bottom      | 底部对齐，将元素行内框的顶端与行框的底端对齐                 |
| text-bottom | 文本底部对齐，是将元素行内框的底端与行框的底线对齐           |
| length      | 以数字加单位的形式设置元素基线距离父元素基线的距离（可以为负值） |
| %           | 使用 "line-height" 属性的百分比值来排列此元素，允许使用负值  |
| inherit     | 从父元素继承 vertical-align 属性的值                         |

上表中提到了基线、底线、顶线、中线等概念，它们到底指什么呢？

- 顶线：中文汉字的上边沿；
- 中线：贯穿小写英文字母 x 中间的线；
- 基线：小写英文字母 x 的下边沿；
- 底线：中文汉字的下边沿；
- 内容区：指底线与顶线包裹的区域；
- 行高：包括内容区与以内容区为基础对称拓展的空白区域，我们称之为行高，也可以认为是相邻文本行基线间的距离；
- 行距：指相邻文本行间上一个文本行底线和下一文本行顶线之间的距离；
- 行内框：是一个浏览器渲染模型中的概念，无法显示出来，但是它又确实存在，它的高度与行高相同；
- 行框：同行内框类似的概念，行框是指本行的一个虚拟的矩形框，也是浏览器渲染模式中的一个概念。行框高度等于本行内所有元素中行内框最大的值（以行高值最大的行内框为基准，其他行内框采用自己的对齐方式向基准对齐，最终计算行框的高度）。

![基线、底线、顶线、中线、内容区、行高、行距、行内框、行框示意图](D:\software\Typora\复制的图片文件\1113593623-9.png)
图：基线、底线、顶线、中线、内容区、行高、行距、行内框、行框示意图

## 10. white-space

white-space 属性用来设置如何处理元素内的空白，属性的可选值如下：



| 值       | 描述                                                     |
| -------- | -------------------------------------------------------- |
| normal   | 默认值，忽略文本中的空白                                 |
| pre      | 保留文本中的空白，类似于`<pre>`标签的效果                |
| nowrap   | 文本会在一行中显示，不会自动换行，直到遇到`<br>`标签为止 |
| pre-wrap | 保留文本中的空白，但是正常地进行换行                     |
| pre-line | 合并文本中的空白，但是保留换行符                         |
| inherit  | 从父元素继承 white-space 属性的值                        |

## 11. direction

direction 属性用来设置文本的方向，属性的可选值如下：



| 值      | 描述                             |
| ------- | -------------------------------- |
| ltr     | 默认值，文本按从左到右的方向输出 |
| rtl     | 文本按从右到左的方向输出         |
| inherit | 从父元素继承 direction 属性的值  |

# CSS链接样式（4种）

链接是网站的重要组成部分，几乎在每个网页上都能看到不少的链接，合理的设计链接的样式能够给网页的颜值加分。链接有四种不同的状态，分别是 link、visited、active 和 hover，可以通过以下伪类选择器来为链接的四种状态设置不同的样式：

- `:link`：定义普通或未访问链接的样式；
- `:visited`：定义已经访问过链接的样式；
- `:hover`：定义当鼠标经过或悬停在链接上时的样式；
- `:active`：定义点击链接时的样式。

通过上面的四个伪类选择器，您可以像给普通文本定义样式那样，为链接定义任何想要的 CSS 样式，例如颜色、字体、背景、边框等。

注意：在定义四个伪类选择器时需要按照一定的顺序，一般情况下`:hover`必须位于`:link`和`:visited`之后，`:active`必须位于`:hover`之后。

在 Chrome、Firefox、Safari 等主流的 Web 浏览器中，都为链接定义了一套默认的样式，如果不专门为链接设置样式，浏览器则会使用默认的链接样式。

- 普通链接：带有下划线的蓝色文本；
- 已访问的链接：带有下划线的紫色文本；
- 点击链接时：带有下划线的红色文本；
- 经过或悬停在链接上时：链接的外观并没有变化，它将保持先前状态的颜色。

# CSS边框样式（border）

CSS 中的边框是围绕着元素内容和内边距的一条或多条线段，您可以自定义这些线段的样式、宽度以及颜色。您可以通过下面几个属性分别定义边框的样式、宽度和颜色：

- border-style：设置边框的样式，例如实线、虚线等；
- border-width：设置边框的宽度（厚度）；
- border-color：设置边框的颜色；
- border：上面三个边框属性的缩写。

## 1. border-style

border-style 属性用来设置元素中所有边框的样式，或者单独为某个边框设置样式，其语法格式如下：

border-style: border-top-style border-right-style border-bottom-style border-left-style;

border-style 属性的可选值如下：



| 值      | 描述                                                   |
| ------- | ------------------------------------------------------ |
| none    | 无边框                                                 |
| hidden  | 隐藏边框，与 "none" 类似                               |
| dotted  | 定义点状虚线边框                                       |
| dashed  | 定义虚线边框                                           |
| solid   | 定义实线边框                                           |
| double  | 定义双实线边框，双实线边框的宽度等于 border-width 的值 |
| groove  | 定义 3D 凹槽边框，其效果取决于 border-color 的值       |
| ridge   | 定义 3D 垄状边框，其效果取决于 border-color 的值       |
| inset   | 定义 3D 嵌入边框，其效果取决于 border-color 的值       |
| outset  | 定义 3D 突出边框，其效果取决于 border-color 的值       |
| inherit | 从父元素继承边框样式                                   |

border-style 属性有多种不同的用法：

- 如果提供全部的四个参数，则会按照上、右、下、左的顺序分别设置边框四个边的样式；
- 如果提供三个参数，那么第一个参数会作用在上边框，第二个参数会作用在左、右两个边框上，第三个参数会作用在下边框上；
- 如果提供两个参数，那么第一个参数会作用在上、下两个边框上，第二个参数会作用在左、右两个边框上；
- 如果只提供一个参数，这个参数将同时作用在四个边框上。

除了可以使用 border-style 属性设置元素的边框样式外，您还可以使用下面的属性分别设置元素上、下、左、右四个边框的样式：

- border-bottom-style：设置下边框的样式；
- border-top-style：设置上边框的样式；
- border-left-style：设置左边框的样式；
- border-right-style：设置右边框的样式。

## 2. border-width

border-width 属性用来设置元素中所有边框的宽度，或者单独为某个边框设置宽度，其语法格式如下：

border-width: border-top-width border-right-width border-bottom-width border-left-width;

border-width 属性的可选值如下：



| 值      | 描述                                             |
| ------- | ------------------------------------------------ |
| thin    | 定义较细的边框                                   |
| medium  | 默认值，定义中等宽度的边框                       |
| thick   | 定义较粗的边框                                   |
| length  | 使用数值加单位的形式设置具体的边框宽度，例如 2px |
| inherit | 从父元素继承边框的宽度                           |

thin、medium、thick 三个关键字并没有固定的值，它们的值取决于浏览器，例如在 Chrome 浏览器中三个关键字的值分别为 1px、3px、5px。

同 border-style 属性相同，border-width 属性同样支持多种不同的用法：

- 如果提供全部的四个参数，则会按照上、右、下、左的顺序分别设置边框四个边的宽度；
- 如果提供三个参数，那么第一个参数会作用在上边框，第二个参数会作用在左、右两个边框上，第三个参数会作用在下边框上；
- 如果提供两个参数，那么第一个参数会作用在上、下两个边框上，第二个参数会作用在左、右两个边框上；
- 如果只提供一个参数，这个参数将同时作用在四个边框上。

除了可以使用 border-width 属性设置元素的边框宽度外，您还可以使用下面的属性分别设置元素上、下、左、右四个边框的宽度：

- border-bottom-width：设置下边框的宽度；
- border-top-width：设置上边框的宽度；
- border-left-width：设置左边框的宽度；
- border-right-width：设置右边框的宽度。

## 3. border-color

border-color 属性用来设置元素中所有边框的颜色，或者单独为某个边框设置颜色，其语法格式如下：

border-color: border-top-color border-right-color border-bottom-color border-left-color;

border-color 属性的可选值如下：



| 值          | 描述                                               |
| ----------- | -------------------------------------------------- |
| color_name  | 使用颜色名称来设置边框的颜色，例如 red             |
| hex_number  | 使用颜色的十六进制值来设置边框的颜色，例如 #ff0000 |
| rgb_number  | 使用 rgb() 函数设置边框的颜色，例如 rgb(255,0,0)   |
| transparent | 默认值，设置边框颜色为透明                         |
| inherit     | 从父元素继承边框的颜色                             |

同 border-style 属性相同，border-color 属性同样支持多种不同的用法：

- 如果提供全部的四个参数，则会按照上、右、下、左的顺序分别设置边框四个边的颜色；
- 如果提供三个参数，那么第一个参数会作用在上边框，第二个参数会作用在左、右两个边框上，第三个参数会作用在下边框上；
- 如果提供两个参数，那么第一个参数会作用在上、下两个边框上，第二个参数会作用在左、右两个边框上；
- 如果只提供一个参数，这个参数将同时作用在四个边框上。

除了可以使用 border-color 属性设置元素的边框颜色外，您还可以使用下面的属性分别设置元素上、下、左、右四个边框的颜色：

- border-bottom-color：设置下边框的颜色；
- border-top-color：设置上边框的颜色；
- border-left-color：设置左边框的颜色；
- border-right-color：设置右边框的颜色。

## 4. border

border 属性是上面介绍的 border-width、border-style、border-color 三种属性的简写，使用 border 属性可以同时定义上述三个属性，语法格式如下：

border: border-width border-style border-color;

其中 border-width 用来设置边框的宽度；border-style 用来设置边框的样式；border-color 用来设置边框的颜色。

除了可以使用 border 属性统一设置边框的宽度、样式、颜色外，您还可以使用下面的属性分别设置元素上、下、左、右四个边框的宽度、样式、颜色：

- border-bottom：统一设置下边框的宽度、样式、颜色；
- border-top：统一设置上边框的宽度、样式、颜色；
- border-left：统一设置左边框的宽度、样式、颜色；
- border-right：统一设置右边框的宽度、样式、颜色。

# CSS表格样式（table）

在网页中我们通常使用表格来展示一些数据，例如成绩表、财务报表等，但是默认情况下表格的样式并不美观，甚至不符合页面的风格。CSS 中提供了一些属性，通过这些属性您可以修改表格的样式，大大改善表格的外观。

- table-layout：设置表格的布局算法，布局算法有两种，分别为固定表格布局算法和自动表格布局算法；
- border-collapse：设置表格中单元格的边框是合并在一起还是按照标准的 HTML 样式分开；
- border-spacing：设置当表格边框分开时，相邻两个边框在横向和纵向上的间距；
- caption-side：设置表格标题相对于表格的位置；
- empty-cells：设置当表格的单元格中没有内容时，是否显示该单元格的边框。

## 1. table-layout

table-layout 属性用来设置表格布局时所用的布局算法，属性的可选值如下：



| 值        | 描述                                                         |
| --------- | ------------------------------------------------------------ |
| automatic | 默认值，自定表格布局，表示表格中每列的宽度视单元格中的内容而定 |
| fixed     | 固定表格布局，表示表格的宽度由列宽度、单元格边框、单元格之间的间距等因素而定 |
| inherit   | 从父元素继承 table-layout 属性的值                           |

### 1) 固定表格布局

固定表格布局允许浏览器更快地对表格进行布局。在固定表格布局中，表格的水平宽度仅取决于列宽度、表格边框宽度、单元格间距等因素，与单元格中的内容无关。也就是说，表格中超出表格宽度的内容可能会被忽略。

### 2) 自动表格布局

在自动表格布局中，列的宽度视单元格中的内容（没有换行的最宽内容）而定，也就是说如果某个单元格的宽度为 100px，但单元格中内容所占据的宽度要大于 100px，这就会导致单元格中的内容将单元格撑大。正是因为这一特点，此种算法可能会比较慢。

## 2. border-collapse

border-collapse 属性用来设置是否合并表格中相邻的边框，属性的可选值如下：



| 值       | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| separate | 默认值，相邻的两个边框是分开的，使用它不会忽略 border-spacing 和 empty-cells 属性 |
| collapse | 相邻的两个边框会合并为一个单一的边框，使用它会忽略 border-spacing 和 empty-cells 属性 |
| inherit  | 从父元素继承 border-collapse 属性的值                        |

## 3. border-spacing

border-spacing 属性可以设置相邻单元格边框之间的距离（仅在 border-collapse 属性为 separate 时才有效），它的效果等同于`<table>`标签的 cellspacing 属性（即`border-spacing:0;`等同于`cellspacing="0"`）。border-spacing 属性的语法格式如下：

border-spacing: length length;

参数 length 由数值和单位组成，表示相邻单元格边框之间的距离，其可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| length  | 以数值加单位的形式设置相邻边框之间的间距，例如 2px，不允许使用负值。如果只定义一个 length 参数，那么这个值将同时作用于横向和纵向的间距；如果同时定义两个 length 参数，那么第一个 length 参数表示相邻边框的横向间距，第二个 length 参数表示相邻边框的纵向间距 |
| inherit | 从父元素继承 border-spacing 属性的值                         |

## 4. caption-side

caption-side 属性可以设置表格标题的位置，属性的可选值如下：



| 值      | 描述                               |
| ------- | ---------------------------------- |
| top     | 默认值，将表格标题定位在表格正上方 |
| bottom  | 将表格标题定位在表格正下方         |
| inherit | 从父元素继承 caption-side 属性的值 |

## 5. empty-cells

empty-cells 属性用来设置当某个单元格中没有内容时，是否显示这个空单元格（仅在 border-collapse 属性为 separate 时才有效），属性的可选值如下：



| 值      | 描述                              |
| ------- | --------------------------------- |
| hide    | 隐藏空单元格周围的边框            |
| show    | 默认值，显示空单元格周围的边框    |
| inherit | 从父元素继承 empty-cells 属性的值 |

# CSS list-style（列表样式）

在网页中很多地方都会用到列表，例如导航菜单、新闻列表、商品分类等等。您除了可以使用 HTML 中的一些属性来对列表进行简单的设置外，在 CSS 中也提供了几种专门用来设置和格式化列表的属性，如下所示：

- list-style-type：设置列表项前面标记的形状（外观）；
- list-style-position：设置标记和列表中文本之间的距离；
- list-style-image：使用图像代替默认的标记；
- list-style：统一设置上面的三个属性。

## 1. list-style-type

使用 list-style-type 属性可以设置列表中每个列表项前标记的样式，属性的可选值如下：



| 值                   | 描述                                                |
| -------------------- | --------------------------------------------------- |
| none                 | 无标记                                              |
| disc                 | 默认值，标记为实心圆                                |
| circle               | 将标记设置为空心圆                                  |
| square               | 将标记设置为实心方块                                |
| decimal              | 将标记设置为数字                                    |
| decimal-leading-zero | 将标记设置为以 0 开头的数字标记，例如 01、02、03    |
| lower-roman          | 将标记设置为小写罗马数字，例如 i、ii、iii、iv、v    |
| upper-roman          | 将标记设置为大写罗马数字，例如 I、II、III、IV、V    |
| lower-alpha          | 将标记设置为小写英文字母，例如 a、b、c、d、e        |
| upper-alpha          | 将标记设置为大写英文字母，例如 A、B、C、D、E        |
| lower-greek          | 将标记设置为小写希腊字母，例如 α、β、γ、δ、ε        |
| lower-latin          | 将标记设置为小写拉丁字母，例如 a、b、c、d、e        |
| upper-latin          | 将标记设置为大写拉丁字母，例如 A、B、C、D、E        |
| hebrew               | 将标记设置为传统的希伯来编号                        |
| armenian             | 将标记设置为传统的亚美尼亚编号                      |
| georgian             | 将标记设置为传统的乔治亚编号                        |
| cjk-ideographic      | 将标记设置为中文数字，例如 一、二、三、四、五       |
| hiragana             | 将标记设置为日文平假名字符，例如 あ、い、う、え、お |
| katakana             | 将标记设置为日文片假名字符，例如 ア、イ、ウ、エ、オ |
| hiragana-iroha       | 将标记设置为日文平假名序号                          |
| katakana-iroha       | 将标记设置为日文片假名序号                          |

## 2. list-style-position

使用 list-style-position 属性可以设置在何处放置列表项前的标记，属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| inside  | 列表项前的标记放置在之后的文本以内，列表项中的文本会根据标记对齐 |
| outside | 默认值，保持标记位于文本的左侧，列表项前的标记放置在文本以外，并且列表项中的文本不会根据标记对齐 |
| inherit | 从父元素继承 list-style-position 属性的值                    |

## 3. list-style-image

通过 list-style-image 属性可以将列表项前的标记替换为一个图像，属性的可选值如下：



| 值      | 描述                                   |
| ------- | -------------------------------------- |
| URL     | 图像的路径                             |
| none    | 默认值，不显示任何图像                 |
| inherit | 从父元素继承 list-style-image 属性的值 |

## 4. list-style

list-style 属性是上述三个属性（list-style-type、list-style-position、list-style-image）的简写，使用 list-style 可以同时设置上面的三个属性，其语法格式如下：

list-style: list-style-type || list-style-position || list-style-image;

提示：在使用 list-style 属性时，需要按照上面的顺序来为参数赋值，只要遵守参数的顺序，即使忽略其中的一项或多项也是可以的，例如`list-style: none;`、`list-style:circle inside;`，被忽略的参数会设置为参数对应的默认值。

# CSS盒子模型

盒子模型是网页设计中经常用到的一种思维模型，由四个部分构成，从内到外分别为内容区（content）、内边距（padding）、边框（border）和外边距（margin），CSS 为这四个部分提供了一系列相关属性，通过对这些属性的设置可以丰富盒子的表现效果。

网页中的每个元素都可以看作是如下图所示一个盒子模型：



![盒子模型](D:\software\Typora\复制的图片文件\145231E13-0.gif)
图：盒子模型

## 内容区（content）

内容区是整个盒子模型的中心，其中存放了盒子的主要内容，这些内容可以是文本、图像等资源。内容区有 width、height、overflow 三个属性，其中 width 和 height 属性用来指定盒子内容区域的宽度和高度，当内容信息过多，超出内容区所设置的范围时，则可以使用 overflow 属性设置溢出内容的处理方式，overflow 属性有四个可选值：

- hidden：表示隐藏溢出的部分；
- visible：表示显示溢出的部分（溢出的部分将显示在盒子外部）；
- scroll：表示为内容区添加一个滚动条，您可以通过滑动这个滚动条来查看内容区的全部内容；
- auto：表示由浏览器决定如何处理溢出部分。

## 内边距（padding）

内边距是内容区和边框之间的空间，您可以通过 padding-top、padding-right、padding-bottom、padding-left 以及它们的简写属性 padding 来设置内容区各个方向上与边框之间的距离。在为盒子模型设置背景属性时，背景属性可以覆盖到内边距区域。

## 边框（border）

边框是环绕内容区和内边距的边界，您可以使用 border-style、border-width 和 border-color 以及它们的简写属性 border 来设置边框的样式。其中 border-style 属性为边框中最主要的属性，如果没有设置该属性的话，其它的边框属性也会被忽略。

注意：在 IE 浏览器中背景属性不会覆盖到边框区域，但是在其它主流浏览器中，背景属性则可以覆盖到边框区域，当将边框设置为虚线时就可以透过虚线看到后面的背景。



## 外边距（margin）

外边距位于盒子模型的最外围，是边框之外的空间，通过外边距可以使盒子与盒子之间不会紧凑的连接在一起，是 CSS 布局中的一种重要手段。您可以使用 margin-top、margin-bottom、margin-left、margin-right 以及它们的简写属性 margin 来设置各个方向上外边距的宽度。

对于两个相邻的（水平或垂直方向 ）且都设置有外边距的盒子，它们之间的距离并不是两者外边距相加的和，而是它们之中较大的那个值。另外，您也可以将外边距的值设置为负值，当外边距的值为负时整个盒子将向反方向移动，当到达一定程度时盒子之间会产生重叠效果。

## 元素的宽度和高度

当您使用 CSS 中的 width 和 height 属性设置元素的宽度和高度时，实际上设置的只是元素内容区域的宽度和高度，元素的实际宽度和高度还取决于一些其它因素：

- 总宽度：width + padding-left + padding-right + border-left + border-right + margin-left + margin-right
- 总高度：height + padding-top + padding-bottom + border-top + border-bottom + margin-top + margin-bottom

# CSS width和height（宽度和高度）

CSS 尺寸属性指的就是元素的宽度和高度属性，虽然说非常简单，但却是必须掌握的技能。CSS 中提供了 width、height、max-width、min-width、max-height 和 min-height 等几个属性来设置元素的宽度和高度，这些元素使用起来非常简单，下面我们就来简单介绍一下。

## 1. width

通过 width 属性可以设置元素内容区的宽度，属性的可选值如下：



| 值      | 描述                                     |
| ------- | ---------------------------------------- |
| auto    | 默认值，浏览器自动计算元素的实际宽度     |
| length  | 使用具体数值配合 px、cm 等单位来定义宽度 |
| %       | 定义基于父元素宽度百分比的宽度           |
| inherit | 从父元素继承 width 属性的值              |

提示：对于`<img>`标签来说，若仅指定 width 属性，那么它的 height 属性将根据原图片尺寸进行等比例缩放。

一般情况下 width 属性需要与 height 属性配合使用来同时定义元素的宽度和高度，因为某些元素没有默认的宽度或高度（或者宽度与高度默认为 0px），若不定义宽度或高度而且元素中又没有内容（子元素、文本等）时，这个元素的宽度或高度就会被设置为 0px，从外表看起来就像被压缩成了一条线。



## 2. height

height 属性用来定义元素内容区的高度，属性的可选值如下：



| 值      | 描述                                     |
| ------- | ---------------------------------------- |
| auto    | 默认值，浏览器自动计算元素的实际高度     |
| length  | 使用具体数值配合 px、cm 等单位来定义高度 |
| %       | 定义基于父元素高度百分比的高度           |
| inherit | 从父元素继承 width 属性的值              |

提示：无论是 width 属性还是 height 属性，它们的值都不能设置为负数。

默认情况下，浏览器会将某些元素的宽度设置为 100%，例如`<div>`、`<p>`，而元素的高度则是根据元素中的内容来确定的，所以有些情况下您不必为元素设置固定的宽度或高度。

## 3. max-width 和 max-height

max-width 和 max-height 属性分别用来设置元素内容区的最大宽度和最大高度。当定义了 max-width 和 max-height 属性时，不论 width 或 height 属性的实际值是多少，width 和 height 属性的实际值都会小于等于 max-width 和 max-height 属性的值。max-width 和 max-height 属性的可选值如下：



| 值      | 描述                                                     |
| ------- | -------------------------------------------------------- |
| none    | 默认值，表示对元素的最大宽度或高度没有限制               |
| length  | 使用具体数值配合 px、cm 等单位来定义元素的最大宽度或高度 |
| %       | 定义基于父元素宽度和高度百分比的最大宽度或高度           |
| inherit | 从父元素继承 max-width 或 max-height 属性的值            |

以 max-width 属性为例：（max-height 属性的特性与之相似）

- 当 max-width 属性的值小于 width 属性时，width 属性的值会被重新定义为与 max-width 属性相同的值；
- 当 max-width 属性的值大于 width 时，max-width 属性将会被忽略；
- 当 max-width 属性的值小于 min-width 时，max-width 属性将会被忽略。

## 4. min-width 和 min-height

min-width 和 min-height 属性用来设置元素内容区的最小宽度和最小高度，当定义了 min-width 和 min-height 属性时，不论 width 或 height 属性的实际值是多少，width 和 height 属性的实际值都会大于等于 min-width 和 min-height 属性的值。min-width 和 min-height 属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| length  | 使用具体数值配合 px、cm 等单位来定义元素的最小宽度或高度，默认值取决于浏览器 |
| %       | 定义基于父元素宽度和高度百分比的最小宽度或高度               |
| inherit | 从父元素继承 min-width 和 min-height 属性的值                |

以 min-width 属性为例：（min-height 属性的特性与之相似）

- 当 min-width 属性的值小于 width 时，min-width 属性将会被忽略；
- 当 min-width 属性的值大于 width 时，min-width 属性的值将被重新定义为与 min-width 属性相同的值；
- 当 min-width 属性的值大于 max-width 时，max-width 属性将会被忽略。

# CSS margin（外边距）

元素的外边距（margin）是围绕在元素边框以外（不包括边框）的空白区域，这片区域不受 background 属性的影响，始终是透明的。

## 为元素设置外边距

默认情况下如果不设置外边距属性，HTML 元素就是不会有外边距，但也有例外的情况，因为浏览器会为一些 HTML 元素设置默认的外边距，例如`<p>`元素。您可以使用下面的属性来为 HTML 元素设置外边距：

- margin-top：设置元素上方的外边距；
- margin-bottom：设置元素下方的外边距；
- margin-right：设置元素右侧的外边距；
- margin-left：设置元素左侧的外边距；
- margin：外边距的简写属性，可以同时设置元素四个方向（上下左右）的外边距。

上述外边距属性的可选值如下表所示：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| auto    | 由浏览器计算外边距的尺寸                                     |
| length  | 使用具体数值配合 px、cm 等单位来定义元素外边距的尺寸，可以为负值，默认值为 0px |
| %       | 定义基于父元素的宽度百分比的外边距，可以为负值               |
| inherit | 从父元素继承外边距属性的值                                   |

这里需要特别说明一下 margin 属性，与其它几个属性不同，margin 属性可以接受 1~4 个参数（参数之间使用空格分隔）：

- 如果提供四个参数，那么将按照上、右、下、左的顺序分别作用于元素四个方向的外边距；
- 如果提供三个参数，那么第一个参数会作用在元素上方的外边距，第二个参数会作用在元素左右两侧的外边距，第三个参数则作用在元素下方的外边距；
- 如果提供两个参数，那么第一个参数会作用在元素上方和下方的外边距，第二个参数会作用在元素的左右两侧的外边距；
- 如果只提供一个参数，那么这个值将同时作用于元素上下左右四个方向的外边距。

## 外边距折叠

外边距折叠指的是相邻的两个或多个外边距会在垂直方向上发生合并，合并为一个外边距。关于外边距折叠有以下几点需要注意：

- margin 折叠只发生在块级元素上；
- 浮动元素的外边距不会与任何外边距发生折叠；
- 设置了 overflow 属性且值不为 visible 的块级元素，将不会与它的子元素发生外边距折叠；
- 绝对定位元素的外边距不与任何外边距发生折叠；
- 根元素（例如`<body>`）的外边距不与其它任何外边距发生折叠。
- 在相邻的两个兄弟元素之间：



- 如果相邻两个元素外边距的值都为正数，那么两个元素的实际间距为两个外边距中较大的那个；
- 如果相邻两个元素外边距的值都为负数，那么两个元素的实际间距为两个外边距中较小的那个；
- 如果相邻两个元素外边距的值一个为正数、一个为负数，那么两个元素之间的实际间距为两个外边距相加的和。

![相邻兄弟元素之间的外边距折叠](D:\software\Typora\复制的图片文件\15035G055-2.gif)
图：相邻兄弟元素之间的外边距折叠

2) 在父元素与其子元素之间：（注意：父元素不能定义边框和内边距，且父元素与子元素之间不能有其它元素）



- 如果父元素与子元素外边距的值都为正数，那么折叠后的外边距为两个外边距中较大的那个；
- 如果父元素与子元素外边距的值都为负数，那么折叠后的外边距为两个外边距中较小的那个；
- 如果父元素与子元素外边距的值一个为正数、一个负数，那么折叠后的外边距为两个外边距相加的和。

![父元素与其子元素之间的外边距折叠](D:\software\Typora\复制的图片文件\15035G3U-3.gif)
图：父元素与其子元素之间的外边距折叠

# CSS padding（内边距）

内边距（padding）是指元素内容区与边框之间的区域，与外边距不同，内边距会受到背景属性的影响。您可以通过下面的属性来设置元素内边距的尺寸：

- padding-top：设置元素内容区上方的内边距；
- padding-right：设置元素内容区右侧的内边距；
- padding-bottom：设置元素内容区下方的内边距；
- padding-left：设置元素内容区左侧的内边距；
- padding：内边距属性的缩写形式，可以同时设置上下左右四个方向上的内边距。

上述属性的可选值如下表所示：



| 值      | 说明                                                         |
| ------- | ------------------------------------------------------------ |
| length  | 使用具体数值配合 px、cm 等单位来定义元素内边距的尺寸，不能为负值，默认值为 0px |
| %       | 定义基于父元素的宽度百分比的内边距，不能为负值               |
| inherit | 从父元素继承内边距属性的值                                   |

## 定义各个方向上的内边距

您可以使用 padding-top、padding-bottom、padding-left 和 padding-right 属性来分别设置元素上下左右四个方向上的内边距。

## 内边距简写形式

padding 属性是其余四个属性的简写形式，在实际开发中我们使用最多的也是这个简写属性。与 margin 属性相似，paddiing 属性同样可以接受 1~4 个参数（参数之间使用空格分隔）：

- 如果提供四个参数，那么将按照上、右、下、左的顺序依次设置元素四个方向上的内边距；
- 如果提供三个参数，那么第一个参数将用来设置元素上方的内边距，第二个参数将用来设置元素左、右两个方向上的内边距，第三个参数将用来设置元素下方的内边距；
- 如果提供两个参数，那么第一个参数将用来设置元素上、下两个方向上的内边距，第二个参数用来设置元素左、右两个方向上的内边距；
- 如果只提供一个参数，那么这个参数将同时作用于元素四个方向上的外边距。

# CSS cursor（鼠标样式）

在浏览网页的过程中，当我们将鼠标移动到一些元素上时，鼠标的样式会发生相应的改变，例如当鼠标指向文本时，鼠标的样式会变成类似大写字母`I`的样子；当鼠标指向链接时，鼠标会变成一个小手的形状等。

除了这些默认的变化外，您还可以通过 CSS 中的 cursor 属性来改变网页中鼠标（光标）的样式，下表中列举了 cursor 属性的可选值：



| 属性值        | 示意图                                                       | 描述                                                         |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| auto          |                                                              | 默认值，由浏览器根据当前上下文确定要显示的光标样式           |
| default       | ![默认光标](D:\software\Typora\复制的图片文件\150S0N27-0.gif) | 默认光标，不考虑上下文，通常是一个箭头                       |
| none          |                                                              | 不显示光标                                                   |
| initial       |                                                              | 将此属性设置为其默认值                                       |
| inherit       |                                                              | 从父元素基础 cursor 属性的值                                 |
| context-menu  | ![上下文菜单光标](D:\software\Typora\复制的图片文件\150S052A-1.gif) | 表示上下文菜单可用                                           |
| help          | ![帮助光标](D:\software\Typora\复制的图片文件\150S05W2-2.gif) | 表示有帮助                                                   |
| pointer       | ![指针光标](D:\software\Typora\复制的图片文件\150S045S-3.gif) | 表示一个链接                                                 |
| progress      | ![进度游标](D:\software\Typora\复制的图片文件\150S04130-4.gif) | 进度指示器，表示程序正在执行一些处理，但是您仍然可以在该界面进行一些操作（与 wait 不同） |
| wait          | ![等待光标](D:\software\Typora\复制的图片文件\150S01548-5.gif) | 表示程序繁忙，您应该等待程序指向完成                         |
| cell          | ![单元游标](D:\software\Typora\复制的图片文件\150S050C-6.gif) | 表示可以选择一个单元格（或一组单元格）                       |
| crosshair     | ![十字准线光标](D:\software\Typora\复制的图片文件\150S03P6-7.gif) | 一个简单的十字准线                                           |
| text          | ![文字游标](D:\software\Typora\复制的图片文件\150S0O53-8.gif) | 表示可以选择的文本                                           |
| vertical-text | ![垂直文本光标](D:\software\Typora\复制的图片文件\150S03J2-9.gif) | 表示可以选择的垂直文本                                       |
| alias         | ![别名光标](D:\software\Typora\复制的图片文件\150S031L-10.gif) | 表示要创建别名或快捷方式                                     |
| copy          | ![复制光标](D:\software\Typora\复制的图片文件\150S032P-11.gif) | 表示可以复制某些内容                                         |
| move          | ![移动光标](D:\software\Typora\复制的图片文件\150S06019-12.gif) | 表示可以移动鼠标下方的对象                                   |
| no-drop       | ![无丢游标](D:\software\Typora\复制的图片文件\150S04022-13.gif) | 表示所拖动的项目不能放置在当前位置                           |
| not-allowed   | ![不允许的游标](D:\software\Typora\复制的图片文件\150S01915-14.gif) | 表示无法完成某事                                             |
| all-scroll    | ![全滚动光标](D:\software\Typora\复制的图片文件\150S03556-15.gif) | 表示对象可以沿任何方向滚动（平移）                           |
| col-resize    | ![彩色游标](D:\software\Typora\复制的图片文件\150S02507-16.gif) | 表示可以水平调整列的大小                                     |
| row-resize    | ![行大小调整游标](D:\software\Typora\复制的图片文件\150S03460-17.gif) | 表示可以垂直调整行的大小                                     |
| n-resize      | ![N尺寸游标](D:\software\Typora\复制的图片文件\150S0B57-18.gif) | 表示对象的边缘可以向上（向北）移动                           |
| e-resize      | ![电子调整游标](D:\software\Typora\复制的图片文件\150S05555-19.gif) | 表示对象的边缘可以向右（向东）移动                           |
| s-resize      | ![S调整游标](D:\software\Typora\复制的图片文件\150S023U-20.gif) | 表示对象的边缘可以向下（向南）移动                           |
| w-resize      | ![W尺寸游标](D:\software\Typora\复制的图片文件\150S05b3-21.gif) | 表示对象的边缘可以向左（向西）移动                           |
| ne-resize     | ![NE调整大小的游标](D:\software\Typora\复制的图片文件\150S064O-22.gif) | 表示对象的边缘可以向上和向右（北/东）移动                    |
| nw-resize     | ![NW调整游标](D:\software\Typora\复制的图片文件\150S01250-23.gif) | 表示对象的边缘可以向上和向左（北/西）移动                    |
| se-resize     | ![SE调整游标](D:\software\Typora\复制的图片文件\150S01212-24.gif) | 表示对象的边缘可以向下和向右（向南/向东）移动                |
| sw-resize     | ![SW调整游标](D:\software\Typora\复制的图片文件\150S04439-25.gif) | 表示对象的边缘可以向下和向左（南/西）移动                    |
| ew-resize     | ![EW调整游标](D:\software\Typora\复制的图片文件\150S033E-26.gif) | 表示可以双向调整对象大小的光标                               |
| ns-resize     | ![NS调整大小的游标](D:\software\Typora\复制的图片文件\150S05346-27.gif) |                                                              |
| nesw-resize   | ![NESW调整大小的游标](D:\software\Typora\复制的图片文件\150S044L-28.gif) |                                                              |
| nwse-resize   | ![NWSE调整大小的游标](D:\software\Typora\复制的图片文件\150S033B-29.gif) |                                                              |
| zoom-in       | ![放大光标](D:\software\Typora\复制的图片文件\150S05K0-30.gif) | 表示可以放大某些内容                                         |
| zoom-out      | ![缩小光标](D:\software\Typora\复制的图片文件\150S05118-31.gif) | 表示可以缩小某些内容                                         |
| grab          | ![抓取光标](D:\software\Typora\复制的图片文件\150S03b0-32.gif) | 表示可以抓取（拖动）某些东西                                 |
| grabbing      | ![抓取光标](D:\software\Typora\复制的图片文件\150S05K4-33.gif) | 表示已经抓取到某些东西                                       |
| url("")       |                                                              | 自定义光标的样式，括号中的内容为光标图像的源文件路径         |

 提示：由于计算机系统的不同，鼠标的样式会存在一定的差异。

## 自定义光标样式

除了可以使用上表中介绍的光标样式外，您也可以使用图像文件来自定义光标的样式，如下所示：

cursor: url("custom.gif"), url("custom.cur"), default;

您可以使用 url() 定义多个光标的样式文件，每个 url() 之间使用逗号`,`分隔，上面示例中 custom.gif、custom.cur 就是自定义的光标文件。需要注意的是，在自定义光标样式时，要在最后定义一个上表中的通用光标样式，防止使用 url() 中定义的光标图像资源失效。

提示：.cur 格式是光标文件的标准格式，您可以使用一些在线工具（例如 https://convertio.co/zh/cur-converter/）将 .jpg、.gif 等格式的图像文件转换为 .cur 格式。

# CSS outline（轮廓）

轮廓（outline）是绘制于元素周围的一条线，位于边框的外围（紧贴着边框），主要用来突出显示某个元素，如下图所示：



![轮廓（outline）](D:\software\Typora\复制的图片文件\15095L004-0.gif)
图：轮廓（outline)

轮廓和边框看起来非常相似，但它们之间也并非没有区别，例如：

- 元素上下左右四个方向上边框的样式、宽度、颜色可以单独设置，而轮廓在元素四个方向的宽度、样式、颜色都是相同的，不能单独设置；
- 边框的宽度会直接影响元素的尺寸，而轮廓不会占用页面空间，不会影响页面的布局，但是轮廓会与页面上的其它元素发声重叠；
- 除了会与周围的元素发声重叠外，轮廓对周围的元素没有任何影响；
- 边框是元素尺寸的一部分，而轮廓不是，也就是说无论轮廓的宽度是多少，元素的尺寸都不会改变；
- 轮廓可以不是矩形的，但您不能直接创建圆形轮廓。

您可以使用下面几个属性来为元素设置轮廓：

- outline-color：设置轮廓的颜色；
- outline-style：设置轮廓的样式；
- outline-width：设置轮廓的宽度；
- outline：轮廓的简写属性，可以使用 outline 属性中同时设置上面的三个轮廓属性；
- outline-offset：设置轮廓与边框之间的距离。

## 1. outline-style

outline-style 属性可以设置轮廓得样式，属性得可选值如下所示：



| 值      | 描述                                                        |
| ------- | ----------------------------------------------------------- |
| none    | 默认值，没有轮廓                                            |
| dotted  | 定义点状的轮廓                                              |
| dashed  | 定义虚线轮廓                                                |
| solid   | 定义实线轮廓                                                |
| double  | 定义双实线轮廓，两条实线之间的宽度等同于 outline-width 的值 |
| groove  | 定义 3D 凹槽轮廓，具体效果取决于 outline-color 的值         |
| ridge   | 定义 3D 凸槽轮廓，具体效果取决于 outline-color 的值         |
| inset   | 定义 3D 凹边轮廓，具体效果取决于 outline-color 的值         |
| outset  | 定义 3D 凸边轮廓，具体效果取决于 outline-color 的值         |
| inherit | 从父元素继承轮廓样式的设置                                  |

## 2. outline-width

outline-width 属性用来设置轮廓的宽度，只有当 outline-style 属性的值不为 none 时，outline-width 属性才会生效。outline-width 属性的可选值如下：



| 值      | 描述                                                    |
| ------- | ------------------------------------------------------- |
| thin    | 设置较细的轮廓                                          |
| medium  | 默认值，设置中等宽度的轮廓                              |
| thick   | 设置较粗的轮廓                                          |
| length  | 使用具体数值加单位（px、em、cm 等）的形式设置轮廓的宽度 |
| inherit | 从父元素继承轮廓的宽度                                  |

## 3. outline-color

outline-color 属性用来设置轮廓的颜色，属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| color   | 指定轮廓颜色，与使用 color、border-color 等属性设置颜色相同，您可以使用颜色名称、十六进制码和 RGB 值等形式定义具体颜色 |
| invert  | 使用背景色的反色来设置轮廓的颜色，仅在 IE 和 Opera 浏览器下有效 |
| inherit | 从父元素继承轮廓颜色的设置                                   |

注意：如果只设置 outline-width 或 outline-color 属性的话，轮廓的设置并不会生效。您必须使用 outline-style 属性设置了轮廓的样式之后，才可以使用 outline-width 和 outline-color 属性来设置轮廓的宽度和颜色。

## 4. outline

outline 属性是上述 outline-width、outline-style、outline-color 三个属性的简写形式，使用 outline 属性可以同时设置这三个属性中的一个或多个，语法格式如下：

outline: outline-width outline-style outline-color;

在使用 outline 属性时，outline-width、outline-style、outline-color 这几个参数的顺序并不是固定的，您可以按照上面语法中介绍的顺序，也可以根据自己的喜好改变它们的顺序。

## 5. outline-offset

默认情况下轮廓是紧贴着边框的，通过 outline-offset 属性可以设置轮廓与边框之间的距离，属性的可选值如下：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| length  | 使用具体数值加单位的形式设置轮廓与边框之间的距离，可以为负值 |
| inherit | 从父元素继承 outline-offset 属性的值                         |

# CSS精灵图（Sprite）

当用户访问一个网站时，浏览器会向服务器发送一系列请求，比如说网页上的每张图像都需要经过一次请求才能最终展示给用户。然而，一个网页中往往包含大量的图像资源（例如在页面中展示的图片、网页的背景图像以及一些装饰性的图像等），这就会导致浏览器频繁的请求服务器，大大降低网页的加载速度。为了有效的减少请求服务器的次数，提高页面加载的速度，就出现了 CSS Sprites 技术，也被称为精灵技术。

简单来讲，精灵技术就是一种处理网页背景图像的方式，它需要将一个页面中涉及到的所有或一部分较小的背景图像合并到一张较大的图片中，然后再将这个图片应用到网页种。通常情况下，我们只是将背景图像中那些较小的、零碎的图像集中到一个大的图像中，这个较大的图像被称为精灵图（也被称为雪碧图），如下图所示就是淘宝网上应用的一个精灵图：



![淘宝网中的精灵图](D:\software\Typora\复制的图片文件\1512021630-0.gif)
图：淘宝网中的精灵图

精灵图的使用也非常简单，只需要借助 background 或者 background-position 属性来定位背景图像的位置即可。

简单来说，精灵图就是一个大的背景图，您只需要使用 background-position 来移动背景图，从而只显示背景图的一部分。目前为止，精灵图发展的已经非常成熟，阿里巴巴、百度、谷歌、京东、淘宝等大型网站中都可以看到精灵图的影子，使用精灵图可以减少图片的体积，也可以显著的减少对服务器的请求次数，提高网页的加载速度。当然，使用精灵图也不是没有弊端，比如：

- 在图片合并的时候，需要把多张图片有序的、合理的合并成一张图片，每个小图之间需要预留足够的空间；
- 在宽屏或者高分辨率的屏幕下来自适应页面宽度时，如果图片不够宽，会出现背景断裂；
- 精灵图在维护的时候比较麻烦，如果页面背景有少许改动，就需要修改整个精灵图。

# CSS滚动条样式（overflow）

通过《[CSS盒子模型](https://c.biancheng.net/css3/box-model.html)》一节的学习我们知道，页面中的每个元素都可以看作是一个矩形的盒子，我们可以使用 CSS 来控制盒子的大小、位置等等信息。默认情况下，当元素中的内容超出盒子的大小时，例如元素内容区的宽度和高度所组成的矩形区域中不足以容纳元素中的内容时，一部分内容就会溢出盒子。

## 1. overflow

为了能更好的处理溢出的内容，CSS 中提供了一个名为 overflow 的属性，该属性可以设置如何处理溢出元素内容区的内容，属性的可选值如下表所示：



| 值      | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| visible | 默认值，对溢出的内容不做处理，内容会在元素内容区之外显示     |
| hidden  | 隐藏溢出元素内容区的内容                                     |
| scroll  | 隐藏溢出元素内容区的内容，并在元素的左侧和下方分别创建一个滚动条，通过滑动滚动条可以查看元素中的所有内容 |
| auto    | 如果出现内容溢出，则会在元素左侧创建一个滚动条，通过滑动滚动条可以查看元素中的全部内容 |
| inherit | 从父元素继承 overflow 属性的值                               |

## 2. overflow-x、overflow-y

在 CSS3 中还提供了 overflow-x 和 overflow-y 两个属性，它们的作用与 overflow 属性相似，属性的可选值与 overflow 属性相同，其中：

- overflow-x：设置当元素内容区的内容在水平方向上溢出元素时如何处理溢出的内容；
- overflow-y：设置当元素内容区的内容在垂直方向上溢出元素时如何处理溢出的内容。

提示：当单独设置 overflow-x 或 overflow-y 其中的一个属性为非 visible 时，另外一个属性将自动设置为 auto。另外，因为 CSS3 还没有最终定稿，所以这两个属性的作用可能会变更或调整。

# CSS计数器

CSS 中的计数器类似于变量，可以实现简单的计数功能，并将结果显示在页面上，在早期的网站上应用比较广泛。要实现计数器需要用到以下几个属性：

- counter-reset：创建或者重置计数器；
- counter-increment：递增变量；
- content：插入生成的内容；
- counter() 或 counters()：将计数器的值添加到元素。

下面我们就来看一下 CSS 中的计数器是如何使用的。

## 初始化计数器

要使用计数器首先需要使用 counter-reset 属性来创建一个计数器，这一过程便叫做初始化计数器。counter-reset 属性的语法格式如下：

counter-reset：none | [<identifier> <integer>]

参数说明如下：

- none：阻止计数器复位；
- <identifier>：定义计数器的名称；
- <integer>：定义计数器的起始值，默认值为 0，可以为负值。

## 计数器自增

初始化计数器后，可以通过 counter-increment 属性来指定计数器何时自增，语法格式如下：

counter-increment：none | [<identifier> <integer>]

参数说明如下：

- none：阻止计数器增加；
- <identifier>：定义要自增的计数器名称；
- <integer>：定义计数器每次增加的数值，默认值为 1，可以为负值。

## 显示计数器

最后，就是如何显示计数器了。要显示计数器您可以使用 counter() 或 counters() 函数，这两个函数的语法格式如下：

counter(name)
counters(name, string, list-style-type)

参数说明如下：

- name：计数器的名称；
- string：当计数器嵌套使用时，用来拼接的字符串；
- list-style-type：计数器显示的风格，可以是 CSS 中允许的任何《[list-style-type 属性](https://c.biancheng.net/css3/list-style.html)》的值。

## 计数器嵌套

另外，计数器还可以嵌套使用，而且使用 counters() 函数可以在不同级别的嵌套计数器之间插入一个字符串

使用 CSS 计数器可以在不借助其它编程语言（例如 JavaScript、PHP 等）的情况下实现简单的计数功能，当需要为某些内容添加序号时非常适用。

# CSS visibility（元素可见性）

CSS 中的 visibility 属性用来设置元素是否可见，您可以将该属性与 JavaScript 一起使用，来创建非常复杂的菜单或网页布局，比如在网页中做一些测试题时您可以使用 visibility 属性将题目的答案或解析隐藏起来，需要时再将其展示出来。

visibility 属性的可选值如下：



| 值       | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| visible  | 默认值，表示元素是可见的                                     |
| hidden   | 隐藏元素                                                     |
| collapse | 主要用来隐藏表格的行和列，隐藏的行或列所占的空间可以被其他表格内容使用；如果在其他元素上使用，其效果等同于“hidden” |
| inherit  | 从父元素继承 visibility 属性的值                             |

提示：visibility 属性虽然会隐藏元素，但会保留元素在页面中所占的空间。如果您希望元素隐藏的同时又不占用页面空间的话，请使用 display 属性。

注意：对于隐藏的元素，虽然我们在页面中看不到了，但是源代码中仍然包含这些隐藏的内容，因此您尽量不要使用它来隐藏敏感信息，例如用户信息、密码等等。

# CSS display（元素显示类型）

display 属性是 CSS 中最重要的属性之一，主要用来控制元素的布局，通过 display 属性您可以设置元素是否显示以及如何显示。

根据元素类型的不同，每个元素都有一个默认的 display 属性值，例如`<div>`默认的 display 属性值为 block（块级元素），而`<span>`默认的 display 属性值为 inline（行内元素），您也可以手动将元素的 display 属性转换为其它值。display 属性的可选值如下：



| 值                 | 描述                                                         |
| ------------------ | ------------------------------------------------------------ |
| none               | 隐藏元素                                                     |
| block              | 将元素设置为块级元素                                         |
| inline             | 将元素设置为内联元素                                         |
| list-item          | 将元素设置为列表项目                                         |
| inline-block       | 将元素设置为行内块元素                                       |
| table              | 将元素设置为块元素级的表格（类似`<table>`）                  |
| inline-table       | 将元素设置为内联元素级的表格（类似`<table>`）                |
| table-caption      | 将元素设置为表格的标题（类似`<caption>`）                    |
| table-cell         | 将元素设置为表格的单元格（类似`<td>`和`<th>`）               |
| table-row          | 将元素设置为表格的行（类似`<tr>`）                           |
| table-row-group    | 将元素设置为表格的内容部分（类似`<tbody>`）                  |
| table-column       | 将元素设置为表格的列（类似`<col>`）                          |
| table-column-group | 将元素设置为表格中一个或多个列的分组（类似`<colgroup>`）     |
| table-header-group | 将元素设置为表格的头部（类似`<thead>`）                      |
| table-footer-group | 将元素设置为表格的脚（类似`<tfoot>`）                        |
| box                | CSS3 中新增的属性值，表示将对象设置为弹性伸缩盒（伸缩盒的最老版本） |
| inline-box         | CSS3 中新增的属性值，表示将对象设置为内联元素级的弹性伸缩盒（伸缩盒的最老版本） |
| flexbox            | CSS3 中新增的属性值，表示将对象设置为弹性伸缩盒（伸缩盒的过渡版本） |
| inline-flexbox     | CSS3 中新增的属性值，表示将对象设置为内联元素级的弹性伸缩盒（伸缩盒的过渡版本） |
| flex               | CSS3 中新增的属性值，表示将对象设置为弹性伸缩盒（伸缩盒的最新版本） |
| inline-flex        | CSS3 中新增的属性值，表示将对象设置为内联元素级的弹性伸缩盒（伸缩盒的最新版本） |
| run-in             | 根据上下文来决定将元素设置为块级元素或内联元素               |
| inherit            | 从父元素继承 display 属性的值                                |

伸缩盒子（弹性盒子）是 CSS3 中一种新的布局模式，引入伸缩盒子的目的是提供一种更加有效的方式来对页面中的元素进行排列、对齐和分配空间，当页面需要适应不同的屏幕大小以及设备类型时这种布局方式能够确保元素拥有恰当尺寸和位置。

下面通过几个常用的属性值来介绍以下 display 属性的使用：

## display: none

display 的属性值 none 可以用来隐藏元素，与前面我们介绍《[CSS visibility](https://c.biancheng.net/css3/visibility.html)》时提到的`visibility: hidden;`功能相似，不同的是`display: none;`在隐藏元素的同时，它还会将元素所占的位置一并隐藏。`display: none;`通常会与 JavaScript 结合使用来隐藏或显示某个元素

## display: block

display 属性的属性值 block 可以将元素强制转换为块级元素

## display: inline

display 属性的属性值 inline 可以将元素强制转换为行内元素，让元素拥有行内元素的特性，例如可以与其他行内元素共享一行等

## display: inline-block

display 属性的属性值 inline-block 可以将元素强制转换为行内块元素，inline-block 既具有 block 能够设置宽高的特性又具有 inline 不独占一行的特性

# CSS position定位（5种方式）

CSS 中的 position 属性用来设置元素在页面中的位置，通过该属性您可以把任何属性放置在任何您认为合适的位置。position 属性有 5 个可选值，分别对应 5 种不同的定位方式，如下所示：

| 取值     | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| static   | 默认值，静态定位，表示没有定位，元素会按照正常的位置显示，此时 top、bottom、left 和 right 4 个定位属性也不会被应用。 |
| relative | 相对定位，即相对于元素的正常位置进行定位，您可以通过 top、right、bottom、left 这 4 个属性来设置元素相对于正常位置的偏移量，在此过程中不会对其它元素造成影响。 |
| absolute | 绝对定位，相对于第一个非 static 定位的父级元素进行定位，可以通过 top、right、bottom、left 这 4 个属性来设置元素相对于父级元素位置的偏移量。如果没有满足条件的父级元素，则会相对于浏览器窗口来进行定位。使用绝对定位的元素不会对其它元素造成影响。 |
| fixed    | 固定定位，相对于浏览器的创建进行定位，可以使用 top、right、bottom、left 这 4 个属性来定义元素相对于浏览器窗口的位置。使用固定定位的元素无论如何滚动浏览器窗口元素的位置都是固定不变的。 |
| sticky   | 粘性定位，它是 relative 和 fixed 的结合体，能够实线类似吸附的效果，当滚动页面时它的效果与 relative 相同，当要滚动到屏幕之外时则会自动变成 fixed 的效果。 |

## 1. 静态定位：static

static 是 position 属性的默认值，表示没有定位，使用静态定位的元素会按照元素正常的位置显示，并且不会受到 top、bottom、left、right 和 z-index 属性的影响。

## 2. 相对定位：relative

相对定位就是元素相对于自己默认的位置来进行位置上的调整，您可以通过 top、bottom、left 和 right 四个属性的组合来设置元素相对于默认位置在不同方向上的偏移量。



![top、bottom、left、right 属性演示](D:\software\Typora\复制的图片文件\104U424H-1.gif)
图：top、bottom、left、right 属性演示

注意：相对定位的元素可以移动并与其他元素重叠，但会保留元素默认位置处的空间。

## 3. 绝对定位：absolute

绝对定位就是元素相对于第一个非静态定位（static）的父级元素进行定位，如果找不到符合条件的父级元素则会相对与浏览器窗口来进行定位。您同样可以使用 top、bottom、left 和 right 四个属性来设置元素相对于父元素或浏览器窗口不同方向上的偏移量。



![top、bottom、left、right 属性在绝对定位中的使用](D:\software\Typora\复制的图片文件\104U46010-3.gif)
图：top、bottom、left、right 属性在绝对定位中的使用

使用绝对定位的元素会脱离原来的位置，不再占用网页上的空间。与相对定位相同，使用绝对定位的元素同样会与页面中的其它元素发声重叠，另外使用绝对定位的元素可以有外边距，并且外边距不会与其它元素的外边距发生重叠。

## 4. 固定定位：fixed

固定定位就是将元素相对于浏览器窗口进行定位，使用固定定位的元素不会因为浏览器窗口的滚动而移动，就像是固定在了页面上一样，我们经常在网页上看到的返回顶部按钮就是使用固定定位实现的。

## 5. 粘性定位：sticky

粘性定位与前面介绍的四种定位方式不太一下，它像是相对定位和固定定位的结合体，当滚动页面时它的效果与相对定位相同，当元素滚动到一定程度时它又会呈现出固定定位的效果。比如一些网页上的导航菜单，当页面加载完成时它在自己默认的位置，当我们向下滚动页面时它又会固定在页面的最顶端。

在使用粘性定位时，需要注意以下几点：

- 在设置`position:sticky;`时，必须再定义 top、bottom、right、left 四个属性之一，否则只会处于相对定位的状态；
- 使用粘性定位元素的父元素不能定义`overflow:hidden`或者`overflow:auto`属性；
- 父元素的高度不能低于粘性定位元素的高度；
- 粘性定位的元素仅在其父元素内有效。

# CSS z-index：元素堆叠

通常我们可能会认为 HTML 网页是个二维的平面，因为页面中的文本、图像或者其它元素都是按照一定顺序排列在页面上的，每个元素之间都有一定的间隙，不会重叠。然而，实际的网页其实是三维的，元素之间可能会发生堆叠（重叠），您可以通过 CSS 中的 z-index 属性来设置元素的堆叠顺序，如下图所示：



![元素堆叠演示](D:\software\Typora\复制的图片文件\110131OI-0.gif)
图：元素堆叠演示

每个元素都有一个默认的 z-index 属性，将 z-index 属性与 position 属性相结合可以创建出类似 PhotoShop 中的图层效果。z-index 属性可以设置元素的层叠级别（当元素出现重叠时，该元素在其它元素之上还是之下），拥有更高层叠级别的元素会处于层叠级别较低的元素的前面（或者说上面）。

通过 z-index 属性您可以创建更加复杂的网页布局，z-index 属性的可选值如下表所示：



| 值      | 描述                                   |
| ------- | -------------------------------------- |
| auto    | 默认值，堆叠顺序与父元素相等           |
| number  | 使用具体数值（整数）设置元素的堆叠顺序 |
| inherit | 从父元素继承 z-index 属性的值          |

关于元素的层级关系有以下几点需要注意：

- 对于未设置 position 属性的元素或者 position 属性的值为 static 时，后定义的元素会覆盖前面的元素；
- 对于设置有 position 属性且属性值不为 static 的元素，这些元素会覆盖没有设置 position 属性或者 position 属性值为 static 的元素；
- 对于 position 属性值不为 static 且定义了 z-index 属性的元素，z-index 属性值大的元素会覆盖 z-index 属性值小的元素，即 z-index 属性值越大优先级越高，若 z-index 属性值相同，则后定义的元素会覆盖前面定义的元素；
- z-index 属性仅在元素定义了 position 属性且属性值不为 static 时才有效。

# CSS float（浮动）

浮动可以使一个元素脱离自己原本的位置，并在父元素的内容区中向左或向右移动，直到碰到父元素内容区的边界或者其它浮动元素为止。另外，在浮动元素之后定义的文本或者行内元素都将环绕在浮动元素的一侧，从而可以实现文字环绕的效果，类似于 Word 中图文混排。

注意：浮动（float）属性仅对非绝对定位的元素有效，跟随浮动元素的文本或行内元素将围绕在浮动元素的另一侧，例如向左浮动的话其它元素将围绕在浮动元素的右侧。

float 属性有三个可选值，如下表所示：



| 值      | 描述                        |
| ------- | --------------------------- |
| left    | 元素向左浮动                |
| right   | 元素向右浮动                |
| none    | 默认值，元素不浮动          |
| inherit | 从父元素继承 float 属性的值 |

另外，在使用 float 属性时还需要注意以下几点：

- 如果设置了 float 属性且属性的值不为 none 时，若 display 属性的值为 inline-table，那么 display 实际会被设置为 table，若 display 的属性值为 inline、inline-block、run-in、table-* 等值，那么 display 实际会被设置为 block，其它情况则没有变化；
- 当元素设置了绝对定位或者 display 属性的值为 none 时，float 属性无效；
- 相邻的浮动元素，如果空间足够它们会紧挨在一起，排列成一行。

## 清除浮动

元素浮动之后，会对周围的元素造成一定的影响，为了消除这种影响您可以使用 clear 属性来清除浮动，属性的可选值如下：



| 值      | 描述                               |
| ------- | ---------------------------------- |
| left    | 左侧不允许浮动元素                 |
| right   | 右侧不允许浮动元素                 |
| both    | 左右两侧均不允许浮动元素           |
| none    | 默认值，允许浮动元素出现在左右两侧 |
| inherit | 从父元素继承 clear 属性的值        |

# CSS伪类选择器

伪类是 W3C 制定的一套选择器的特殊状态，通过伪类您可以设置元素的动态状态，例如悬停（hover）、点击（active）以及文档中不能通过其它选择器选择的元素（这些元素没有 ID 或 class 属性），例如第一个子元素（first-child）或者最后一个子元素（last-child）。

伪类的名称不区分大小写，但需要以冒号`:`开头。另外，伪类需要与 CSS 中的选择器结合使用，语法格式如下：

selector:pseudo-class {
  property: value;
}

其中 selector 为选择器名称，pseudo-class 为伪类的名称。

CSS 中提供了各种各样的伪类，如下表所示：



| 选择器               | 例子                  | 例子描述                                                     |
| -------------------- | --------------------- | ------------------------------------------------------------ |
| :active              | a:active              | 匹配被点击的链接                                             |
| :checked             | input:checked         | 匹配处于选中状态的 <input> 元素                              |
| :disabled            | input:disabled        | 匹配每个被禁用的 <input> 元素                                |
| :empty               | p:empty               | 匹配任何没有子元素的 <p> 元素                                |
| :enabled             | input:enabled         | 匹配每个已启用的 <input> 元素                                |
| :first-child         | p:first-child         | 匹配父元素中的第一个子元素 <p>，<p> 必须是父元素中的第一个子元素 |
| :first-of-type       | p:first-of-type       | 匹配父元素中的第一个 <p> 元素                                |
| :focus               | input:focus           | 匹配获得焦点的 <input> 元素                                  |
| :hover               | a:hover               | 匹配鼠标悬停其上的元素                                       |
| :in-range            | input:in-range        | 匹配具有指定取值范围的 <input> 元素                          |
| :invalid             | input:invalid         | 匹配所有具有无效值的 <input> 元素                            |
| :lang(language)      | p:lang(it)            | 匹配每个 lang 属性值以 "it" 开头的 <p> 元素                  |
| :last-child          | p:last-child          | 匹配父元素中的最后一个子元素 <p>， <p> 必须是父元素中的最后一个子元素 |
| :last-of-type        | p:last-of-type        | 匹配父元素中的最后一个 <p> 元素                              |
| :link                | a:link                | 匹配所有未被访问的链接                                       |
| :not(selector)       | :not(p)               | 匹配每个非 <p> 元素的元素                                    |
| :nth-child(n)        | p:nth-child(2)        | 匹配父元素中的第二个子元素 <p>                               |
| :nth-last-child(n)   | p:nth-last-child(2)   | 匹配父元素的倒数第二个子元素 <p>                             |
| :nth-last-of-type(n) | p:nth-last-of-type(2) | 匹配父元素的倒数第二个子元素 <p>                             |
| :nth-of-type(n)      | p:nth-of-type(2)      | 匹配父元素的第二个子元素 <p>                                 |
| :only-of-type        | p:only-of-type        | 匹配父元素中唯一的 <p> 元素                                  |
| :only-child          | p:only-child          | 匹配父元素中唯一的子元素 <p>                                 |
| :optional            | input:optional        | 匹配不带 "required" 属性的 <input> 元素                      |
| :out-of-range        | input:out-of-range    | 匹配值在指定范围之外的 <input> 元素                          |
| :read-only           | input:read-only       | 匹配指定了 "readonly" 属性的 <input> 元素                    |
| :read-write          | input:read-write      | 匹配不带 "readonly" 属性的 <input> 元素                      |
| :required            | input:required        | 匹配指定了 "required" 属性的 <input> 元素                    |
| :root                | root                  | 匹配元素的根元素，在 HTML 中，根元素永远是 HTML              |
| :target              | #news:target          | 匹配当前活动的 #news 元素（单击包含该锚名称的 URL）          |
| :valid               | input:valid           | 匹配所有具有有效值的 <input> 元素                            |
| :visited             | a:visited             | 匹配所有已经访问过的链接                                     |

# CSS伪元素

伪元素是一个附加在选择器末尾的关键词，通过伪元素您不需要借助元素的 ID 或 class 属性就可以对被选择元素的特定部分定义样式。例如通过伪元素您可以设置段落中第一个字母的样式，或者在元素之前、之后插入一些内容等等。

在 CSS1 和 CSS2 中，伪元素的使用与伪类相同，都是使一个冒号`:`与选择器相连。但在 CSS3 中，将伪元素单冒号的使用方法改为了使用双冒号`::`，以此来区分伪类和伪元素。因此，建议在使用伪元素时使用双冒号而不是单冒号。

selector::pseudo-element {
  property: value;
}

其中，selector 为选择器，pseudo-element 为伪元素的名称，property 为 CSS 中的属性，value 为属性对应的值。

注意：一个选择器中只能使用一个伪元素，而且伪元素必须紧跟在选择器之后。按照最新的 W3C 规范，在定义伪元素时您应该使用双冒号`::`而不是单个冒号`:`，以便区分伪类和伪元素。但由于旧版本的 W3C 规范并未对此进行特别区分，因此目前绝大多数的浏览器都同时支持使用单冒号和双冒号两种方式来定义伪元素。

CSS 中提供了一系列的伪元素，如下表所示：



| 伪元素         | 例子               | 例子描述                                              |
| -------------- | ------------------ | ----------------------------------------------------- |
| ::after        | p::after           | 在每个 <p> 元素之后插入内容                           |
| ::before       | p::before          | 在每个 <p> 元素之前插入内容                           |
| ::first-letter | p::first-letter    | 匹配每个 <p> 元素中内容的首字母                       |
| ::first-line   | p::first-line      | 匹配每个 <p> 元素中内容的首行                         |
| ::selection    | p::selection       | 匹配用户选择的元素部分                                |
| ::placeholder  | input::placeholder | 匹配每个表单输入框（例如 <input>）的 placeholder 属性 |

## 1. ::after

伪元素 ::after 能够在指定元素的后面插入一些内容，在 ::after 中需要使用 content 属性来定义要追加的内容，而且在 ::after 中必须定义 content 属性才会生效（没有需要插入的内容时可以将 content 属性的值定义为空`""`）。

## 2. ::before

伪元素 ::before 能够在指定元素的前面插入一些内容。与 ::after 相似，::before 中也需要使用 content 属性来定义要追加的内容，而且在 ::before 中必须定义 content 属性才会生效（没有需要插入的内容时可以将 content 属性的值定义为空`""`）。

## 3. ::first-letter

伪元素 ::first-letter 用来设置指定元素中内容第一个字符的样式，通常用来配合 font-size 和 float 属性制作首字下沉效果。需要注意的是，伪元素 ::first-letter 仅可以用于块级元素，行内元素想要使用该伪元素，则需要先将其转换为块级元素。

## 4. ::first-line

伪元素 ::first-line 用来设置指定元素中内容第一行的样式，与 ::first-letter 类似，伪元素 ::first-line 也仅可以用于块级元素，行内元素想要使用该伪元素，则需要先将其转换为块级元素。

## 5. ::selection

伪元素 ::selection 用来设置对象被选中时的样式，需要注意的是，伪元素 ::selection 中只能定义元素被选中时的 color、background、cursor、outline 以及 text-shadow（IE11 尚不支持定义该属性）等属性。

## 6. ::placeholder

伪元素 ::placeholder 用来设置表单元素（<input>、<textarea> 元素）的占位文本（通过 HTML 的 placeholder 属性设置的文本）

# CSS透明度（opacity）

前面在学习《[CSS颜色](https://c.biancheng.net/css3/color.html)》时我们已经了解，通过 rgba()、hsla() 可以设置颜色的透明度，但是它们只能在定义颜色的同时设置透明度，无法对图像或者其它元素设置透明度。

CSS 中提供了一个 opacity 属性用来设置元素的透明度，它不仅对颜色有效，对图像或者页面中其它的元素也有效。其语法格式如下：

opacity: number;

其中 number 为一个 0~1 之间的浮点数（小数），用来表示元素的透明度，值越小则越透明（0 表示完全透明，1 表示完全不透明）。

另外，在使用 opacity 属性时，还需要注意以下几点：

- 当一个元素定义了 opacity 属性，并且其值小于 1 时，那么它的子元素也会拥有同样的透明度；
- 当一个元素定义了 opacity 属性，并且其值小于 1 时，将会重新定义该元素默认的 z-index 属性，如果其它的元素为非定位元素，那么该元素的堆叠级别将会高于其它元素；
- 如果定义的 opacity 属性值超过了指定的范围，那么则截取与之最相近的值，例如 1.5 将截取为 1。

IE8 或者更早版本的 IE 浏览器不支持 opacity 属性，若想要在这些浏览器中实现透明效果可以使用 filter 属性，语法格式如下：

filter: alpha(opacity = number);

其中 number 的取值范围为 0~100，值越小则越透明。



为了让所有浏览器都可以实现透明效果，您可以同时定义 opacity 和 filter 两个属性，如下所示：

```css
p {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
```



# CSS @规则

在 CSS 中包含两种语法规则：

- 普通规则：由选择器、属性和值构成，在之前的学习中我们主要使用的就是这种规则；
- @规则：以`@`开头后面跟随一个关键字的形式构成，也被称为“AT规则”，根据使用方法的不同又可以分为“常规规则”与“嵌套规则”两种。

本节我们主要来介绍一下 CSS 中的 @ 规则。

## 1、常规规则

所谓“常规规则”指的是语法类似下面的规则：

@[KEYWORD] (RULE);

#### 1) @charset

@charset 用来设置 CSS 文件使用的字符编码，语法格式如下：

@charset "<charset>";

其中 <charset> 为具体的字符编码，默认值为“utf-8”。

在使用时需要注意以下几点：

- 如果设置 @charset 的话，那么它必须出现在 CSS 文件的最前面，@charset 之前不能出现任何字符；
- 字符编码需要使用双引号`""`包裹起来；
- @规则名称（@charset）与具体的字符编码之间需要使用一个空格分隔；
- 规则后面的分号不能省略；
- 如果设置多个 @charset，那么只有第一个声明有效；
- 不能在 HTML 元素或者 <style> 标签中使用 @charset；
- 如果以不同的方式定义了多种字符编码规则，它们的优先级顺序如下：
  - HTML 文件开头的字符编码声明；
  - HTTP 请求头中的字符编码声明；
  - CSS 文件中使用 @charset 定义的字符编码声明；
  - <link> 标签中 charset 属性设置的字符编码声明（HTML5 中已废弃）。

下面示例中演示了 @charset 的使用，以及几个错误的示例：

```css
/* 设置 CSS 的编码格式为 Unicode UTF-8 */
@charset "UTF-8";      
@charset "utf-8";       /*大小写不敏感*/
/*错误演示*/
@charset 'iso-8859-15'; /* 无效的, 使用了错误的引号 */
@charset 'UTF-8';       /* 无效的, 使用了错误的引号 */
@charset  "UTF-8";      /* 无效的, @charset 与字符编码之间多用了一个空格 */
@charset "UTF-8";       /* 无效的, @规则之前多了一个空格 */
@charset UTF-8;         /* 无效的, 字符编码需要使用双引号包裹 */
```

#### 2) @import

@import 用来向当前 CSS 样式文件中导入其它样式文件。通过 @import 可以引入其他样式表文件中除 @charset 以外的所有内容，另外 @import 也必须放在样式文件的最前面。@import 的语法格式如下：

@import <url> <media_query_list>

其中，<url> 为使用绝对或相对路径指定的要导入的外部样式表文件路径，也可以使用 url() 函数来指定文件路径；<media_query_list> 为可选参数，用来指定媒体查询的条件，多个条件之间使用逗号`,`分隔。

在实际项目中不建议过多的使用 @import，因为它会造成很多额外的请求，阻塞其它文件的加载。

在使用 @import 时，还需要注意以下几点：

- @import 必须在样式表文件的开头最先声明，并且声明的末尾必须使用分号结尾，如果省略了结尾的分号，可能会导致外部样式表无法正确导入；
- 在 IE 浏览器使用 @import 最多只能引入 35 条样式表。

下面示例中演示了 @import 的使用：

```css
@import url("global.css");
@import url(global.css);
@import "global.css";
@import url("fineprint.css") print;
@import url("bluish.css") projection, tv;
@import 'custom.css';
@import url("chrome://communicator/skin/");
@import "common.css" screen, projection;
@import url('landscape.css') screen and (orientation:landscape);
```

以上几种定义方式都是有效的，当使用 url() 来设置样式表文件的路径时，包裹路径的引号可有可无；当直接使用具体路径来设置样式表文件的路径时，包裹路径的引号则必须保留。

#### 3) @namespace

@namespace 用来定义 CSS 样式表中 XML 命名空间的 @规则，可以为当前样式文件内的所有选择器都设置指定的命名空间。@namespace 通常用来处理包含多个命名空间的文档，比如 HTML5 里内联的 SVG、MathML 或者混合多个词汇表的 XML。

@namespace 必须定义在所有 @charset 和 @import 的之后，并且在样式表中要位于其他任何样式声明之前。@namespace 可以用来定义默认命名空间，当指定默认命名空间后，所有的通用选择器和类选择器（但不包括属性选择器）都只会应用在这个命名空间的元素中。@namespace 也可以用于定义命名空间前缀，当一个通用、类、属性选择器前面有命名空间前缀修饰时，这个选择器将只匹配那些命名空间与元素名或属性匹配的元素。

下面示例中演示了 @namespace 的使用：

```css
/* 默认命名空间 */
@namespace url(XML-namespace-URL);
@namespace "XML-namespace-URL";
/* 命名空间前缀 */
@namespace prefix url(XML-namespace-URL);
@namespace prefix "XML-namespace-URL";
```

## 2、嵌套规则

所谓“嵌套规则”指的就是在 @规则后面需要跟随一个花括号`{ }`，其中包含了一些其它的规则声明，类似于下面这样：

```
@[KEYWORD] {
  /* 嵌套语句 */
}
```

### 1) @media

@media 用来根据一个或多个媒体查询的结果来应用样式表的某一部分（花括号中的样式信息），使用 @media 您可以指定一组媒体查询和一个 CSS 样式块，当且仅当媒体查询与正在使用的设备匹配时，指定的 CSS 样式才会应用于文档。

媒体查询是用于判断设备信息的一组条件，如设备的宽高值，宽高比，颜色，分辨率等，当条件匹配时，才会执行其内嵌套的样式信息。

@media 可以放置在样式表中的任意位置，也可以放置于其它 @规则中，示例代码如下：



```css
@media all and (min-width: 1280px) {
    /* 宽度大于1280 */
}
@media
(-webkit-min-device-pixel-ratio: 1.5),
(min-resolution: 2dppx) {
    /* Retina屏幕 */
}
@media print {
    /* 打印 */
}
@media \0screen\,screen\9 {
    /* IE7,IE8 */
}
@media screen\9 {
    /* IE7*/
}
```

### 2) @page

@page 用于在打印文档时修改某些 CSS 属性，需要注意的是，使用 @page 您只能修改部分 CSS 属性，例如外间距属性 margin，打印相关的 orphans、widows 属性，以及 page-break-* 等属性，其他的 CSS 属性会被忽略。

```css
/* 表示打印时 第一页的上、左外边距均为 50% */
@page :first {
  margin-left: 50%;
  margin-top: 50%;
}
```

### 3) @supports

@supports 用于检查浏览器是否支持某个 CSS 特性，也被称为“特性查询”，该规则的语法结构如下：

```
@supports (rule)[operator (rule)]* { sRules };
```



其中，rule 为某个具体的 CSS 样式，必须使用括号包裹；operator 的可选值为 or、and、not，通过 operator 参数可以指定多条 CSS 样式。

@supports 既可以在样式文件的顶部定义，也可以在其它嵌套规则内部定义。但是 @supports 目前还在实验阶段，在使用时要先确定浏览器是否支持。

下面示例中演示了 @supports 的使用：

```css
/* 当浏览器支持 display: grid 属性时要使用的 CSS 样式 */
@supports (display: grid) {
  div {
    display: grid;
  }
}
/* 当浏览器不支持 display: grid 属性时要使用的 CSS 样式 */
@supports not (display: grid) {
  div {
    float: right;
  }
}
/* 同时检查多个条件 */
@supports (display: flex) and (-webkit-appearance: checkbox) {
  .module { display: flex; }
}
```

### 4) @font-face

@font-face 用于从远程服务器或者用户本地加载指定的字体，语法格式如下：

```css
@font-face {
  font-family: <identifier>;
  src: <url> [format(<string>)] [, <url> [format(<string>)]]*;
  <font>;
}
```



参数说明如下：

- <identifier>：字体名称；
- <url>：使用 url()（远程字体）或者 local()（本地字体）来指定字体的存放路径，可以是相对路径也可以是绝对路径；
- <string>：用来指定自定义字体的格式，例如以下几种类型 truetype、opentype、embedded-opentype、svg 等；
- <font>：定义字体相关样式。

提示：@font-face 可以放在 css 样式表的顶部，也可以放在其它嵌套规则中。如果同时使用 local() 函数和 url() 函数加载字体，则会优先加载 local() 函数中定义的本地字体，如果没有找到则会加载 url() 函数中定义的远程字体。

下面示例中演示了 @font-face 的使用：

```css
/* 定义 @font-face 规则 */
@font-face {
    /* 指定字体名称 */
    font-family: "Open Sans";
    /* 指定字体文件的路径 */
    src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2"),
         url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
}
/* 字体的应用 */
p {
    font-family: "Open Sans";
}
```

#### 5) @keyframes

@keyframes 用来定义 CSS3 中 animation 动画关键帧（或 waypoints）的样式，以此来控制动画序列中的中间步骤。定义该规则后，需要通过 animation-name 属性来使用。关键帧序列是由百分比来标识命名的，起始状态和结束状态分别为 from 和 to 代表 0% 和 100% 。

@keyframes 的语法格式如下：

```css
@keyframes <identifier> {
  <keyframes-blocks>
}
```



其中 <identifier> 用来定义动画名称；<keyframes-blocks> 用来定义动画在每个阶段的样式，即帧动画。

下面示例中演示了 @keyframes 的使用：

```css
/* 声明 */
@keyframes slidein {
  from {
    margin-left: 100%;
    width: 300%;
  }
  to {
    margin-left: 0%;
    width: 100%;
  }
}
@keyframes slideout {
  0% {
    top: 0;
  }
  50% {
    top: 30px;
  }
  100% {
    top: 60px;
  }
}
/* 应用 */
p {
  animation-name: slidein;
  animation-duration: 4s;
}
div {
  animation-name: slideout;
  animation-duration: 4s;
}
```

#### 6) @document

@document 用来根据文档的 URL 限制文档中样式的作用范围，通过该属性可以为指定用户定义专属的样式。目前 @document 还在实验阶段，具体标准会在 CSS4 中确定。

@document 中的可用函数如下所示：

- url()：匹配整个 URL；
- url-prefix()：匹配文档的 URL 是否以参数指定的值开头；
- domain()：匹配文档的域名是否为参数中指定的域名或者为它的子域名；
- regexp()：匹配文档的 URL 是否和参数中指定的正则表达式匹配，该表达式必须匹配整个 URL。

提示：提供给 url()、url-prefix() 和 domain() 函数的参数可以不使用引号包裹，但提供给 regexp() 函数的参数必须使用引号包裹起来。

下面示例中演示了 @document 的使用：

```css
@document url(http://www.weixueyuan.net/),
            url-prefix(http://www.weixueyuan.net/Style/),
            domain(weixueyuan.net),
            regexp("https:.*")
{
  /* 该条 CSS 规则会应用在下面的网页:
    + URL 为"http://www.weixueyuan.net/"的页面.
    + 任何 URL 以"http://www.weixueyuan.net/Style/"开头的网页
    + 域名"weixueyuan.net"下的所有网页
    + 任何 URL 以"https:"开头的网页 */
  /* 定义样式 */
    body {
        color: purple;
        background: yellow;
    }
}
```

# CSS媒体查询（@media）全面解析

随着移动设备的快速普及，用户不再只是通过传统的电脑系来浏览 Web 内容，越来越多的用户开始使用各种尺寸的智能手机、平板电脑或者其它设备来浏览 Web 内容，为了确保使用不同设备的用户都能拥有不错的体验就需要用到媒体查询。

媒体查询是 CSS 样式表最重要的功能之一，所谓媒体查询指的就是根据不同的媒体类型（设备类型）和条件来区分各种设备（例如：电脑、手机、平板电脑、盲文设备等），并为它们分别定义不同的 CSS 样式。媒体查询能让 CSS 可以更精确的作用于不同的设备或同一设备的不同条件，让所有用户都能得到很好的用户体验。

## 1. 媒体类型

媒体类型用来表示设备的类别，CSS 中提供了一些关键字来表示不同的媒体类型，如下表所示：



| 媒体类型   | 描述                                                 |
| ---------- | ---------------------------------------------------- |
| all        | 表示所有的媒体设备                                   |
| aural      | 表示语音和音频合成器（听觉设备）                     |
| braille    | 表示盲人用点字法触觉回馈设备                         |
| embossed   | 表示盲人用点字法打印机                               |
| handheld   | 表示小型手持设备，如手机、平板电脑                   |
| print      | 表示打印机                                           |
| projection | 表示投影设备                                         |
| screen     | 表示电脑显示器                                       |
| tty        | 表示使用固定密度字母栅格的媒体，比如打字机或终端设备 |
| tv         | 表示电视机类型的设备                                 |

## 2. 媒体特性

除了具体的类型外，还可以通过一些属性来描述设备的具体特征，例如宽度、高度、分辨率等，如下表所示：



| 值                      | 描述                                                         |
| ----------------------- | ------------------------------------------------------------ |
| aspect-ratio            | 输出设备页面可见区域的宽高比                                 |
| color                   | 输出设备每个像素的比特值，常见的有 8、16、32 位。如果设备不支持输出彩色，则该值为 0 |
| color-index             | 输出设备的颜色查询表中的条目数量。如果没有使用颜色查询表，则该值等于 0 |
| device-aspect-ratio     | 输出设备的宽高比                                             |
| device-height           | 输出设备屏幕的可见高度                                       |
| device-width            | 输出设备屏幕的可见宽度                                       |
| grid                    | 查询输出设备使用的是网格屏幕还是点阵屏幕                     |
| height                  | 页面可见区域的高度                                           |
| max-aspect-ratio        | 输出设备屏幕可见区域宽度与高度的最大比率                     |
| max-color               | 输出设备每个像素比特值的最大值                               |
| max-color-index         | 输出设备的颜色查询表中的最大条目数                           |
| max-device-aspect-ratio | 输出设备屏幕可见区域宽度与高度的最大比率                     |
| max-device-height       | 输出设备屏幕可见区域的最大高度                               |
| max-device-width        | 输出设备屏幕的最大可见宽度                                   |
| max-height              | 页面可见区域的最大高度                                       |
| max-monochrome          | 输出设备单色帧缓冲区中每个像素的最大位深度。如果设备并非黑白屏幕，则该值为 0 |
| max-resolution          | 设备的最大分辨率                                             |
| max-width               | 页面可见区域的最大宽度                                       |
| min-aspect-ratio        | 输出设备屏幕可见区域宽度与高度的最小比率                     |
| min-color               | 输出设备每个像素比特值的最小值                               |
| min-color-index         | 输出设备的颜色查询表中的最小条目数                           |
| min-device-aspect-ratio | 输出设备的屏幕可见区域宽度与高度的最小比率                   |
| min-device-width        | 输出设备的屏幕的最小可见宽度                                 |
| min-device-height       | 输出设备的屏幕的最小可见高度                                 |
| min-height              | 页面可见区域的最小高度                                       |
| min-monochrome          | 输出设备单色帧缓冲区中每个像素的最小位深度。如果设备并非黑白屏幕，则该值为 0 |
| min-resolution          | 设备的最小分辨率                                             |
| min-width               | 页面可见区域的最小宽度                                       |
| monochrome              | 输出设备单色帧缓冲区中每个像素的位深度。如果设备并非黑白屏幕，则该值为 0 |
| orientation             | 页面可见区域的旋转方向                                       |
| resolution              | 设备的分辨率。如：96dpi、300dpi、118dpcm                     |
| scan                    | 电视类设备的扫描工序                                         |
| width                   | 页面可见区域的宽度                                           |

## 3. 逻辑操作符

逻辑操作符包含 not、and 和 only 三个，通过逻辑操作符可以构建复杂的媒体查询，您还可以通过逗号来分隔多个媒体查询，将它们组合为一个规则。

- and：用于将多个媒体查询组合成一条媒体查询，当每个查询规则都为真时则该条媒体查询为真，另外通过 and 操作符还可以将媒体特性与媒体类型结合在一起；
- not：用于否定媒体查询，当查询规则不为真时则返回 true，否则返回 false。如果使用 not 操作符，则还必须指定媒体类型；
- only：仅在整个查询匹配时才会生效，当不使用 only 时，旧版的浏览器会将 screen and (max-width: 500px) 简单地解释为 screen，忽略查询的其余部分，并将样式应用于所有屏幕。 如果使用 only 运算符，则还必须指定媒体类型。

## 4. 定义媒体查询

目前您可以通过以下两种方式来定义媒体查询：

- 使用 @media 或 @import 规则在样式表中指定对应的设备类型；
- 用 media 属性在 <style>、<link>、<source> 或其他 HTML 元素中指定特定的设备类型。

# CSS圆角（border-radius）

在制作网页的过程中，有时我们可能需要实现圆角的效果，以前的做法是通过切图（将设计稿切成便于制作成页面的图片），使用多个背景图像来实现圆角。在 CSS3 出现之后就不需要这么麻烦了，CSS3 中提供了一系列属性来设置元素的圆角效果，如下所示：

- border-top-left-radius：为元素左上角设置圆角效果；
- border-top-right-radius：为元素右上角设置圆角效果；
- border-bottom-right-radius：为元素右下角设置圆角效果；
- border-bottom-left-radius：为元素左下角设置圆角效果；
- border-radius：上面四个属性的简写形式，可以同时为元素的四个角设置圆角效果。

上述函数的可选值如下表所示：



| 值         | 描述                               |
| ---------- | ---------------------------------- |
| length     | 通过数值加单位的形式定义圆角的形状 |
| percentage | 以百分比的形式定义圆角的形状       |

## border-*-radius

通过上面的介绍我们知道，通过 border-*-radius 系列函数能够分别为元素的四个角设置圆角效果，函数的语法格式如下：

```css
border-*-radius：[ <length> | <percentage> ]{1,2}
```

语法的含义为，需要为 border-*-radius 属性提供 1~2 个参数，参数之间使用空格进行分隔。其中第一个参数表示圆角水平方向的半径或半轴，第二个参数表示圆角垂直方向的半径或半轴，如果省略第二个参数，那么该参数将直接沿用第一个参数的值。



![元素四角](D:\software\Typora\复制的图片文件\1522091456-0.gif)
图：元素四角

## border-radius

border-radius 属性是 border-top-left-radius、border-top-right-radius、border-bottom-right-radius、border-bottom-left-radius 四个属性的简写形式，使用 border-radius 可以同时设置四个 border-*-radius 属性。border-radius 属性的格式如下：

```css
border-radius：[ <length> | <percentage> ]{1,4} [ / [ <length> | <percentage> ]{1,4} ]?
```

语法说明如下：

- border-radius 属性可以接收两组参数，参数之间使用斜杠`/`进行分隔，每组参数都允许设置 1~4 个参数值，其中第一组参数代表圆角水平方向上的半径或半轴，第二组参数代表圆角垂直方向上的半径或半轴，如果省略第二组参数的值，那么该组参数将直接沿用第一组参数的值。
- 第一组参数中，如果提供全部的四个参数，那么将按照上左 top-left、上右 top-right、下右 bottom-right、下左 bottom-left 的顺序作用于元素的四个角；如果提供三个参数，那么第一个参数将作用于元素的左上角 top-left，第二个参数将作用于元素的右上角 top-right 和左下角 bottom-left，第三个参数将作用于元素的右下角 bottom-right；如果提供两个参数，那么第一个参数将作用于元素的左上角 top-left 和右下角 bottom-right，第二个参数将作用于元素的右上角 top-right 和左下角 bottom-left；如果只提供一个参数，那么该参数将同时作用于元素的四个角。
- 第二组参数同样遵循第一组参数的规律，只是作用的方向不同。

# CSS border-image（边框图片）

对于元素的边框我们除了可以使用《[CSS 边框](https://c.biancheng.net/css3/border.html)》一节中介绍的一些默认样式外，还可以通过 CSS3 中的 border-image 属性使用图像来作为元素的边框，以创建出丰富多彩边框效果。

border-image 属性可以通过一些简单的规则，将一副图像划分为 9 个单独的部分，浏览器会自动使用相应的部分来替换边框的默认样式。border-image 属性是五个 border-image-* 属性的简写，其语法格式如下：

```css
border-image：border-image-source || border-image-slice [ / border-image-width | / border-image-width ? / border-image-outset ]? || border-image-repeat
```

通过语法可以看出 border-image 是 border-image-source、border-image-slice、border-image-width、border-image-outset 和 border-image-repeat 属性的简写，其中：

- border-image-source：定义边框图像的路径；
- border-image-slice：定义边框图像从什么位置开始分割；
- border-image-width：定义边框图像的厚度（宽度）；
- border-image-outset：定义边框图像的外延尺寸（边框图像区域超出边框的量）；
- border-image-repeat：定义边框图像的平铺方式。

接下来我们通过如下所示的图片来演示一下 border-image-source、border-image-slice、border-image-width、border-image-outset 和 border-image-repeat 几个属性的使用。



![边框图片](D:\software\Typora\复制的图片文件\1532491419-0.png)
图：边框图片

## 1. border-image-source

border-image-source 属性用来定义边框要使用的图像，通过该属性可以指定一个图像来替换边框的默认样式，当 border-image-source 属性的值为 none 或者指定的图像不可用时，则会显示边框默认的样式。

另外，border-image-source 属性除了可以使用图像来替换边框的默认样式外，您还可以使用渐变来定义边框样式，属性的语法格式如下：

```css
border-image-source：none | <image>
```

其中，none 为 border-image-source 属性的默认值，表示不使用图像来替换边框的默认样式；<image> 为使用 url() 函数指定的图像路径或者使用 linear-gradient() 函数定义的渐变色，用来替换默认的边框样式。

## 2. border-image-slice

border-image-slice 属性用来分割通过 border-image-source 属性加载的图像，属性的语法格式如下：

```css
border-image-slice：[ <number> | <percentage> ]{1,4} && fill?
```

border-image-slice 属性可以接收三种类型的值：

- <number>：数值，用具体数值指定图像分割的位置，数值代表图像的像素位置或向量坐标，不允许负值；
- <percentage>：百分比，相对于图像尺寸的百分比，图像的宽度影响水平方向，高度影响垂直方向；
- fill：保留边框图像的中间部分。

border-image-slice 属性可以指定上、下、左、右四个方位来分割图像，并将图像分成 4 个角、4条边和中间区域等 9 个部份，中间区域始终是透明的（即没图像填充），除非加上关键字 fill，如下图所示：



![img](D:\software\Typora\复制的图片文件\15324912F-2.gif)

除 fill 关键字外，border-image-slice 属性可以接受 1~4 个参数值：

- 如果提供全部四个参数值，那么将按上、右、下、左的顺序对图像进行分割；
- 如果提供三个参数，那么第一个参数用于上方，第二个参数用于左、右两侧，第三个参数用于下方；
- 如果提供两个参数，那么第一个参数用于上方和下方，第二个参数用于左、右两个；
- 如果只提供一个参数，那么上、右、下、左都将使用该值进行分割。

## 3. border-image-width

border-image-width 属性用来设置通过 border-image-source 属性加载的图像厚度（宽度），属性的语法格式如下：

```css
border-image-width：[ <length> | <percentage> | <number> | auto ]{1,4}
```

语法说明如下：

- <length>：使用数值加单位的形式指定图像边框的宽度，不允许为负值；
- <percentage>：用百分比的形式指定图像边框的宽度，参照图像边框区域的宽和高进行换算，不允许负值；
- <number>：使用浮点数指定图像边框的宽度，该值对应 border-width 的倍数，例如值为 2，则参数的实际值为 2 * border-width，不允许负值；
- auto：由浏览器自动设定，当 border-image-width 设置为 auto 时，它的实际值与 border-image-slice 相同的值。

提示：border-image-width 属性的默认值为 1，也就是说当我们省略 border-image-width 属性的值时，该属性的值会被设置为 1 * border-width，相当于会直接使用 border-width 的值。

border-image-width 属性同样可以接受 1~4 个参数值：

- 如果提供全部四个参数值，那么将按照上、右、下、左的顺序设置图像边框四个方向上的宽度；
- 如果提供三个参数，那么第一个参数用于上边框，第二个参数用于左、右两个边框，第三个参数用于下边框；
- 如果提供两个参数，那么第一个参数用于上、下两个边框，第二个参数用于左、右两个边框；
- 如果只提供一个参数，那么上、右、下、左都将使用该值设置图像边框的宽度。

## 4. border-image-outset

border-image-outset 属性用来定义图像边框相对于边框边界向外偏移的距离（使图像边框延伸到盒子模型以外），该属性的语法格式如下：

```css
border-image-outset：[ <length> | <number> ]{1,4}
```

语法说明如下：

- <length>：用具体的数值加单位的形式指定图像边框向外偏移的距离，不允许为负值；
- <number>：用浮点数指定图像边框向外偏移的距离，该值表示 border-width 的倍数，例如值为 2，则表示偏移量为 2 * border-width，不允许为负值。

border-image-outset 属性同样可以接受 1~4 个参数值：

- 如果提供全部四个参数值，那么将按上、右、下、左的顺序作用于四边；
- 如果提供三个参数值，那么第一个参数将用于上边框，第二个参数将用于左、右两个边框，第三个参数将用于下边框；
- 如果提供两个参数，那么第一个参数将用于上、下两个边框，第二个参数将用于左、右两个边框；
- 如果只提供一个参数，那么该参数将同时作用于四边。

## 5. border-image-repeat

border-image-repeat 属性用来设置如何填充使用 border-image-slice 属性分割的图像边框，例如平铺、拉伸等等，该属性的语法格式如下：

```css
border-image-repeat：[ stretch | repeat | round | space ]{1,2}
```

语法说明如下：

- stretch：将被分割的图像使用拉伸的方式来填充满边框区域；
- repeat：将被分割的图像使用重复平铺的方式来填充满边框区域，当图像碰到边界时，超出的部分会被截断；
- round：与 repeat 关键字类似，不同之处在于，当背景图像不能以整数次平铺时，会根据情况缩放图像；
- space：与 repeat 关键字类似，不同之处在于，当背景图像不能以整数次平铺时，会用空白间隙填充在图像周围。

border-image-repeat 属性能够接受 1~2 个参数值：

- 如果提供两个参数，那么第一个参数将用于水平方向，第二个将用于垂直方向；
- 如果只提供一个参数，那么将在水平和垂直方向都应用该值。

## 6. border-image

了解完 border-image-source、border-image-slice、border-image-width、border-image-outset 和 border-image-repeat 这几个属性，我们回头再来看看 border-image 属性。border-image 属性是五个 border-image-* 属性的简写，通过 border-image 属性可以同时设置五个 border-image-* 属性。



# CSS渐变色（颜色渐变）

CSS 中的渐变指的是两种或多种颜色之间的平滑过渡，以前我们必须使用事先定义好的图像来实现渐变效果，在 CSS3 出现以后则简单了很多，CSS3 为实现渐变效果提供了一种灵活的解决方案。

通过 CSS3 您可以定义三种类型的渐变，分别为线性渐变（通过 linear-gradient() 函数创建）、径向渐变（通过 radial-gradient() 函数创建）和圆锥渐变（通过 conic-gradient() 函数创建）。另外，您还可以使用 repeating-linear-gradient()、repeating-radial-gradient() 和 repeating-conic-gradient() 函数来创建重复渐变。

通过 CSS 创建的渐变不仅简单灵活，而且还省去了使用图像时所需的加载过程，节省了网页的加载时间。另外，通过 CSS 创建的渐变元素可以按任意比例放大或缩小，而且不会降低质量。

## 1. 线性渐变

线性渐变指的是颜色沿一条直线进行渐变（例如右上到下，从左到右等），要创建线性渐变，您至少需要定义两个色标（色标指的是想要平滑过渡的颜色），若要创建更加复杂的渐变效果，则需要定义更多的色标。创建线性渐变的基本语法如下：

```css
linear-gradient(direction, color-stop1, color-stop2, ...);
```

参数说明如下：

- direction 可选值，定义渐变的方向（例如从左到右，从上到下），可以是具体角度（例如 90deg），也可以通过 to 加 left、right、top、bottom 等关键字来表示渐变方向，例如：
  - to left：表示从右到左，相当于 270deg；
  - to right：表示从左到右，相当于 90deg；
  - to top：表示从下到上，相当于 0deg；
  - to bottom：默认值，表示从上到下，相当于 180deg；
  - to right bottom：表示从左上到右下；
  - to right top：表示从左下到右上；
  - to left bottom：表示从右上到左下；
  - to left top：表示从右下到左上。
- color-stop1、color-stop2、...：表示定义的多个色标，在每个色标中除了可以定义颜色外，还可以通过数值加单位或者百分比的形式定义颜色的起止位置。

## 2. 径向渐变

径向渐变与线性渐变类型，不同之处在于径向渐变是由中心向外延申的渐变，您可以指定中心点的位置，也可以设置渐变的形状。定义径向渐变的基本语法如下所示：

```css
radial-gradient(shape size at position, color-stop1, color-stop2, ...);
```

参数说明如下：

- at：一个关键字，需要放置在参数 position 的前面；
- position：指定渐变起点的坐标，您可以使用数值加单位、百分比或者关键字（例如 left、bottom 等）等形式指定渐变起点的坐标，如果提供 2 个参数，那么第一个参数用来表示横坐标，第二个参数用来表示纵坐标，如果只提供一个参数，那么第二个参数将被默认设置为 50%，即 center；
- shape：指定渐变的形状，可选值为 circle（圆形）、ellipse（椭圆）；
- size：指定渐变形状的大小，除了可以使用具体的数值来指定 circle、ellipse 的半径外，还可以使用下面所示的关键字来指定渐变形状的大小：
  - closest-side：指定径向渐变的半径长度为从圆心到离圆心最近的边；
  - closest-corner：指定径向渐变的半径长度为从圆心到离圆心最近的角；
  - farthest-side：默认值，指定径向渐变的半径长度为从圆心到离圆心最远的边；
  - farthest-corner：指定径向渐变的半径长度为从圆心到离圆心最远的角。
- color-stop1、color-stop2、...：表示定义的多个色标，在每个色标中除了可以定义颜色外，还可以通过数值加单位或者百分比的形式定义颜色的起止位置。

## 3. 圆锥渐变

圆锥渐变类似于径向渐变，两者都有一个中心点作为色标的源点，不同的是圆锥渐变是围绕中心点旋转（而不是从中心点向往辐射），定义圆锥渐变的基本语法如下：

```css
conic-gradient(from angle at position, start-color, ..., last-color);
```

语法说明如下：

- from：一个关键字，需要放置在参数 angle 之前；
- angle：定义圆锥渐变的起始角度，可以为空，默认值为 0deg；
- at：一个关键字，需要放置在参数 position 之前；
- position：定义圆锥渐变锥心的坐标，您可以使用数值加单位、百分比或者关键字（例如 left、bottom 等）等形式指定锥心的坐标，如果提供 2 个参数，那么第一个参数用来表示横坐标，第二个参数用来表示纵坐标，如果只提供一个参数，那么第二个参数将被默认设置为 50%，即 center（居中）；
- start-color、...、last-color：表示定义的多个色标，在每个色标中除了可以定义颜色外，还可以通过百分比或者角度来定义颜色的起始位置。

## 4. 重复渐变

在 CSS 中，您还可以使用 repeating-linear-gradient()、repeating-radial-gradient() 和 repeating-conic-gradient() 等函数来分别创建线性渐变、径向渐变和圆锥渐变的重复渐变，所谓重复渐变就是指将渐变的过程重复多次，以铺满整个元素。

提示： repeating-linear-gradient()、repeating-radial-gradient() 和 repeating-conic-gradient() 函数的语法分别与 linear-gradient()、radial-gradient() 和 conic-gradient() 函数的语法相同。



# CSS阴影效果

在网页设计中常常要使用到阴影效果，通过阴影效果可以很好的突出一个元素，在 CSS3 出现之前，我们想要为文本或者元素添加阴影效果需要借助图像才能实现，很不方便。而 CSS3 出现之后，我们通过 text-shadow 和 box-shadow 两个属性就可以为文本或元素添加阴影效果，不需要借助任何图像。

## 1. text-shadow

使用 CSS 的 text-shadow 属性我们可以为文本设置阴影效果，属性的语法格式如下：

```css
text-shadow: offset-x offset-y blur color;
```

语法说明如下：

- offset-x：必填参数，设置阴影的水平偏移量，可以为负值；
- offset-y：必填参数，设置阴影的垂直偏移量，可以为负值；
- blur：可选参数，设置模糊的半径，值越大，模糊越大，阴影的边缘越模糊，不允许使用负值；
- color：可选参数，设置阴影的颜色，如果省略或未指定该值，则采用 color 属性的值。

提示：使用 text-shadow 属性可以同时设定多组阴影效果，每组之间使用逗号分隔，定义的多组阴影效果会按照定义顺序依次罗列，第一个阴影在最上面，以此类推。另外，若要取消文本的阴影效果则可以将 text-shadow 属性的值设置为 none。

## 2. box-shadow

使用 CSS 的 box-shadow 属性我们可以为 HTML 元素设置阴影效果，属性的语法格式如下：

```css
box-shadow: h-shadow v-shadow blur spread color inset;
```

语法说明如下：

- h-shadow：必填参数，设置阴影水平方向的偏移量，可以为负值；
- v-shadow：必填参数，设置阴影垂直方向的偏移量，可以为负值；
- blur：可选参数，设置模糊的半径，值越大，模糊越大，阴影的边缘越模糊，不允许使用负值；
- spread：可选参数，设置阴影的尺寸；
- color：可选参数，设置阴影的颜色；
- inset：可选参数，将默认的外部阴影 (outset) 改为内部阴影。

提示：与 text-shadow 属性相似，box-shadow 属性也可以同时设定多组阴影效果，每组之间使用逗号分隔，定义的多组阴影效果会按照定义顺序依次罗列，第一个阴影在最上面，以此类推。



# CSS 2D转换

CSS 中的 2D 转换允许我们在二维空间中执行一些基本的变换操作，例如移动、旋转、缩放或扭曲等，变换后的元素与绝对定位的元素类似，不会影响周围的元素，但可以和周围的元素重叠，不同的是，转换后的元素在页面中任然会占用为转换之前的空间。

借助 CSS 中的 transform 属性以及下列转换函数就可以实现 2D 转换：

- matrix()：以一个包含六个值（a, b, c, d, e, f）的变换矩阵的形式指定一个 2D 变换，相当于直接应用一个 [a,b,c,d,e,f] 的变换矩阵；
- translate()：将对象沿 X 轴和 Y 轴平移，该函数需要提供 1~2 个参数，第一个参数对应 X 轴，第二个参数对应 Y 轴，如果未提供第二个参数，则默认值为 0；
- translatex()：将对象沿 X 轴（水平方向）的平移；
- translatey()：将对象沿 Y 轴（垂直方向）的平移；
- rotate()：旋转指定对象，在函数的参数中可以指定旋转的角度；
- scale()：将对象进行缩放，该函数需要提供 1~2 个参数，第一个参数对应 X 轴，第二个参数对应 Y 轴，如果未提供第二个参数，则默认取第一个参数的值；
- scalex()：将对象进行缩放（改变元素的宽度）；
- scaley()：将对象进行缩放（改变元素的高度）；
- skew()：将对象沿 X 轴和 Y 轴方向进行倾斜扭曲，该函数需要提供 1~2 个参数，第一个参数对应 X 轴，第二个参数对应 Y 轴。如果未提供第二个参数，则默认值为 0；
- skewx()：将对象沿 X 轴的（水平方向）扭曲；
- skewy()：将对象沿 Y 轴的（垂直方向）扭曲。

## 1. translate()

translate() 函数用来根据指定的参数将元素沿水平（X轴）或垂直（Y轴）方向移动，函数的语法格式如下：

```css
translate(tx, ty)
```

其中 tx 对应元素在水平（X轴）方向的移动距离，ty 对应元素在垂直（Y轴）方向的移动距离，参数 ty 可以忽略（默认为 0），两个参数均可以为负值。

如果只是将元素水平移动或者只是将元素垂直移动，也可以使用 translateX()（将元素水平移动）或 translateY()（将元素垂直移动），translateX() 和 translateY() 函数均只需要提供一个参数即可，例如：

```css
translateX(100px);   /* 等同于 translate(100px, 0px); */
translateY(10px);    /* 等同于 translate(0px, 10px); */
```

## 2. rotate()

rotate() 函数用来按照给定的角度来旋转元素，函数的语法格式如下：

```css
rotate(a)
```

其中参数 a 表示元素要旋转的角度，若 a 为正值则表示顺时针旋转，若 a 为负值则表示逆时针旋转。

## 3. scale()

scale() 函数用来缩放（放大或缩小）指定的元素，函数的语法格式如下：

```css
scale(sx, sy)
```

其中 sx 表示水平方向的缩放比例，sy 表示垂直方向的缩放比例。另外，参数 sy 可以省略，它的默认值等于 sx。

提示：当 scale() 中，给定的参数值在 -1~1 范围之外时，元素将被放大；当在参数值在 -1~1 范围之内时，元素将被缩小。

与 translate() 函数类似，如果是仅在水平方向或者仅在垂直方向上缩放元素大小，也可以使用 scaleX()（在水平方向缩放元素）和 scaleY()（在垂直方向缩放元素）函数。scaleX() 和 scaleY() 函数仅需要提供一个参数即可，例如：

```css
scaleX(0.5);  /* 等同于 scale(0.5, 1); */
scaleY(0.5);  /* 等同于 scale(1, 0.5); */
```



## 4. skew()

skew() 函数用来将元素沿水平方向（X轴）和垂直方向（Y轴）倾斜扭曲，函数的语法格式如下：

```css
skew(ax, ay)
```



其中，参数 ax 表示元素水平方向的扭曲角度，参数 ay 表示元素垂直方向的扭曲角度。另外，参数 ay 可以省略，若省略参数 ay，则其默认值为 0。

另外，如果是仅在水平方向或者仅在垂直方向上对元素进行扭曲，也可以使用 skewX()（在水平方向缩放元素）和 skewY()（在垂直方向缩放元素）函数来完成。skewX() 和 skewY() 函数仅需要提供一个参数即可，例如：

```css
skewX(15deg);  /* 等同于 skew(15deg, 0deg); */
skewY(15deg);  /* 等同于 skew(0deg, 15deg); */
```



## 5. matrix()

matrix() 函数可以看作是 skew()、scale()、rotate() 和 translate() 几个函数的缩写形式，通过 matrix() 函数可以同时定义所有 2D转换操作，函数的语法格式如下：

```css
matrix(a, b, c, d, tx, ty)
```



matrix() 函数中的 6 个参数分别对应 scaleX()、skewY()、skewX()、scaleY()、translateX()、translateY() 几个函数，您可以使用 matrix() 来实现各种 2D转换操作，例如：

- `translate(tx, ty) = matrix(1, 0, 0, 1, tx, ty);`：其中 tx 和 ty 是水平和垂直平移值；
- `rotate(a) = matrix(cos(a), sin(a), -sin(a), cos(a), 0, 0);`：其中，a 是度数的值。您可以交换 sin(a) 和 -sin(a) 值来进行反向旋转；
- `scale(sx, sy) = matrix(sx, 0, 0, sy, 0 ,0);`：其中 sx 和 sy 是水平和垂直缩放比例值；
- `skew(ax, ay) = matrix(1, tan(ay), tan(ay), 1, 0 ,0);`：其中 ax 和 ay 是以 deg 为单位的水平和垂直值。

# CSS 3D转换

在 CSS 中，除了可以对页面中的元素进行 [2D 转换](https://c.biancheng.net/css3/2d-3d-transform.html)外，您也可以对象元素进行 3D转换（将页面看作是一个三维空间来对页面中的元素进行移动、旋转、缩放和倾斜等操作）。与 2D 转换相同，3D 转换同样不会影响周围的元素，而且可以与其它元素重叠。但是，变换后的元素任然会占用其默认位置（未变换前）的空间。

3D 转换同样需要使用 transform 属性以及一些函数来实现，例如：

- matrix3d()：以一个 4x4 矩阵的形式指定一个 3D 转换；
- translate3d()：指定对象的 3D 位移，第 1 个参数对应 X 轴，第 2 个参数对应 Y 轴，第 3 个参数对应 Z 轴，参数不允许省略；
- translateZ()：指定对象在 Z 轴的平移；
- rotate3d()：指定对象的 3D 旋转角度，其中前 3 个参数分别表示旋转的方向 X、Y、Z，第 4 个参数表示旋转的角度，参数不允许省略；
- rotateX()：指定对象在 X 轴上的旋转角度；
- rotateY()：指定对象在 Y 轴上的旋转角度；
- rotateZ()：指定对象在 Z 轴上的旋转角度；
- scale3d()：指定对象的 3D 缩放，第 1 个参数对应 X 轴，第 2 个参数对应 Y 轴，第 3 个参数对应 Z 轴，参数不允许省略；
- scaleZ()：指定对象的 Z 轴缩放；
- perspective()：指定透视距离。

## 1. translate3d()

translate3d() 函数用于移动元素在 3D 空间中的位置，这种变换的特点是通过三维矢量坐标来定义元素在每个方向上（X轴、Y轴、Z轴）的偏移量。函数的语法格式如下：

```css
translate3d(tx, ty, tz)
```

参数说明如下：

- tx：表示元素在水平方向（X 轴）移动的距离；
- ty：表示元素的垂直方向（Z 轴）移动的距离；
- tz：表示元素在 Z 轴移动的距离，该参数不能使用百分比值。

3D 转换使用的是三维坐标系，但是沿 Z轴方向的移动并不能很明显的显现出来，因为我们往往会将网页看作是一个二维的平面，并没有深度。您可以使用 perspective 和 perspective-origin 属性来为元素添加深度感，即 Z 轴越高的元素显示的越大，反之则越小。

## 2. translateZ()

函数 translateZ() 用来沿三维坐标系的 Z 轴来移动元素，函数的语法格式如下：

```css
translateZ(tz);
```

其中参数 tz 用来设置元素在 Z轴上移动的距离。

提示：translateZ(tz); 相当于 translate3d(0, 0, tz); 的简写形式。

## 3. rotate3d()

rotate3d() 函数用来设置元素沿 X轴、Y轴或 Z轴方向旋转的角度，该函数只会使元素按照固定的轴旋转，不会使元素变形。rotate3d() 函数的语法格式如下：

```css
rotate3d(x, y, z, a)
```

参数说明如下：

- x：设置旋转轴的 X轴坐标；
- y：设置旋转轴的 Y轴坐标；
- z：设置旋转轴的 Z轴坐标；
- a：设置元素旋转的角度，正角度表示顺时针旋转，负角度表示逆时针旋转。

除了 rotate3d() 函数外，CSS 中还提供了 rotateX()（沿 X 轴旋转元素）、rotateY() （沿 Y 轴旋转元素）和 rotateZ()（沿 Z 轴旋转元素）三个函数来按照不同的坐标轴旋转元素。rotateX()、rotateY()、rotateZ() 函数的语法格式如下：

```css
rotateX(a) /* 等同于 rotate3D(1, 0, 0, a); */
rotateY(a) /* 等同于 rotate3D(0, 1, 0, a); */
rotateZ(a) /* 等同于 rotate3D(0, 0, 1, a); */
```



## 4. scale3d()

scale3d() 函数可以改变元素的大小（缩放），函数的语法格式如下：

```css
scale3d(sx, sy, sz)
```

参数说明如下：

- sx：表示元素在 X 轴方向的缩放比例；
- sy：表示元素在 Y 轴方向的缩放比例；
- sz：表示元素在 Z 轴方向的缩放比例。

提示：当 scale3d() 函数的参数数值超出 [-1，1] 范围时，将在对应的方向上放大元素；当参数值在 [-1，1] 范围内时，将在当前方向上缩小元素；当参数值等于 1 时，则不会改变元素的大小。

除了 scale3d() 函数外，CSS 中还提供了 scaleX()（沿 X 轴缩放元素）、scaleY() （沿 Y 轴缩放元素）和 scaleZ()（沿 Z 轴缩放元素）三个函数来按照不同的坐标轴缩放元素。scaleX()、scaleY()、scaleZ() 函数的语法格式如下：

```css
scaleX(sx) /* 等同于 scale(sx, 1); 和 scale3d(sx, 1, 1); */
scaleY(sy) /* 等同于 scale(1, sy); 和 scale3d(1, sy, 1); */
scaleZ(sz) /* 等同于 scale3d(1, 1, sz); */
```



## 5. matrix3d()

matrix3d() 函数与前面我们学习的 matrix() 函数非常相似，不过 matrix3d() 函数可以使用一个 4 × 4 的矩阵来描述一个三维（3D）转换。通过 matrix3d() 函数可以一次执行所有的 3D转换操作，函数的语法格式如下：

```css
matrix3d(a1, b1, c1, d1, a2, b2, c2, d2, a3, b3, c3, d3, a4, b4, c4, d4)
```

参数说明如下：

- a1、b1、c1、d1、a2、b2、c2、d2、a3、b3、c3、d3、d4：用来描述各种 3D 转换；
- a4、b4、c4：表示元素变换的量。

# CSS transition（过渡效果）

通常当 CSS 的属性值更改后，浏览器会立即更新相应的样式，例如当鼠标悬停在元素上时，通过 :hover 选择器定义的样式会立即应用在元素上。在 CSS3 中加入了一项过渡功能，通过该功能您可以将元素从一种样式在指定时间内平滑的过渡到另一种样式，类似于简单的动画，但无需借助 flash 或 JavaScript。

CSS 中提供了 5 个有关过渡的属性，如下所示：

- transition-property：设置元素中参与过渡的属性；
- transition-duration：设置元素过渡的持续时间；
- transition-timing-function：设置元素过渡的动画类型；
- transition-delay：设置过渡效果延迟的时间，默认为 0；
- transition：简写属性，用于同时设置上面的四个过渡属性。

要成功实现过渡效果，必须定义以下两项内容：

- 元素中参数与过渡效果的属性；
- 过渡效果持续的时间。

提示：过渡效果通常会在鼠标悬停在元素上时发生，如果未设置过渡持续的时间，则过渡效果不会生效，因为过渡时间的默认值为 0。

## 1. transition-property

transition-property 属性用来设置元素中参与过渡的属性名称，语法格式如下：

```css
transition-property: none | all | property;
```

参数说明如下：

- none：表示没有属性参与过渡效果；
- all：表示所有属性都参与过渡效果；
- property：定义应用过渡效果的 CSS 属性名称列表，多个属性名称之间使用逗号`,`进行分隔。

## 2. transition-duration

transition-duration 属性用来设置过渡需要花费的时间（单位为秒或者毫秒），语法格式如下：

```css
transition-duration: time;
```

其中，time 为完成过渡效果需要花费的时间（单位为秒或毫秒），默认值为 0，意味着不会有效果。

如果有多个参与过渡的属性，也可以依次为这些属性设置过渡需要的时间，多个属性之间使用逗号进行分隔，例如`transition-duration: 1s, 2s, 3s;`。除此之外，也可以使用一个时间来为所有参与过渡的属性设置过渡所需的时间.

## 3. transition-timing-function

transition-timing-function 属性用来设置过渡动画的类型，属性的可选值如下：



| 值                       | 描述                                                         |
| ------------------------ | ------------------------------------------------------------ |
| linear                   | 以始终相同的速度完成整个过渡过程，等同于 cubic-bezier(0,0,1,1) |
| ease                     | 以慢速开始，然后变快，然后慢速结束的顺序来完成过渡过程，等同于 cubic-bezier(0.25,0.1,0.25,1) |
| ease-in                  | 以慢速开始过渡的过程，等同于 cubic-bezier(0.42,0,1,1)        |
| ease-out                 | 以慢速结束过渡的过程，等同于 cubic-bezier(0,0,0.58,1)        |
| ease-in-out              | 以慢速开始，并以慢速结束的过渡效果，等同于 cubic-bezier(0.42,0,0.58,1) |
| cubic-bezier(n, n, n, n) | 使用 cubic-bezier() 函数来定义自己的值，每个参数的取值范围在 0 到 1 之间 |

## 4. transition-delay

transition-delay 属性用来设置过渡效果何时开始，属性的语法格式如下：

```css
transition-delay: time;
```

其中，参数 time 用来设置在过渡效果开始之前需要等待的时间，单位为秒或毫秒。

## 5. transition

transition 属性是上面四个属性的简写形式，通过该属性可以同时设置上面的四个属性，属性的语法格式如下：

```css
transition: transition-property transition-duration transition-timing-function transition-delay;
```

transition 属性中，transition-property 和 transition-duration 为必填参数，transition-timing-function 和 transition-delay 为选填参数，如非必要可以省略不写。另外，通过 transition 属性也可以设置多组过渡效果，每组之间使用逗号进行分隔

# CSS动画（animation）

通过《[CSS过渡](https://c.biancheng.net/css3/transition.html)》一节的学习我们知道，利用 transition 属性可以实现简单的过渡动画，但过渡动画仅能指定开始和结束两个状态，整个过程都是由特定的函数来控制的，不是很灵活。本节我们再来介绍一种更为复杂的动画 —— animation。

CSS 中的动画类似于 flash 中的逐帧动画，表现细腻并且非常灵活，使用 CSS 中的动画可以取代许多网页中的动态图像、Flash 动画或者 JavaScript 实现的特殊效果。

## @keyframes 规则

要创建 CSS 动画，您首先需要了解 @keyframes 规则，@keyframes 规则用来定义动画各个阶段的属性值，类似于 flash 动画中的关键帧，语法格式如下：

```css
@keyframes animationName {
    from {
        properties: value;
    }
    percentage {
        properties: value;
    }
    to {
        properties: value;
    }
}
// 或者
@keyframes animationName {
    0% {
        properties: value;
    }
    percentage {
        properties: value;
    }
    100% {
        properties: value;
    }
}
```

语法说明如下：

- animationName：表示动画的名称；
- from：定义动画的开头，相当于 0%；
- percentage：定义动画的各个阶段，为百分比值，可以添加多个；
- to：定义动画的结尾，相当于 100%；
- properties：不同的样式属性名称，例如 color、left、width 等等。

下面我们来看一个简单的 @keyframes 规则示例：

```css
@keyframes ball {
    0% { top: 0px; left: 0px;}
    25% { top: 0px; left: 350px;}
    50% { top: 200px; left: 350px;}
    75% { top: 200px; left: 0px;}
    100% { top: 0px; left: 0px;} 
}
```

动画创建好后，还需要将动画应用到指定的 HTML 元素。要将动画应用到指定的 HTML 元素需要借助 CSS 属性，CSS 中提供了如下所示的动画属性：

- animation-name：设置需要绑定到元素的动画名称；
- animation-duration：设置完成动画所需要花费的时间，单位为秒或毫秒，默认为 0；
- animation-timing-function：设置动画的速度曲线，默认为 ease；
- animation-fill-mode：设置当动画不播放时（动画播放完或延迟播放时）的状态；
- animation-delay：设置动画开始之前的延迟时间，默认为 0；
- animation-iteration-count：设置动画被播放的次数，默认为 1；
- animation-direction：设置是否在下一周期逆向播放动画，默认为 normal；
- animation-play-state：设置动画是正在运行还是暂停，默认是 running；
- animation：所有动画属性的简写属性。

# CSS column（多列布局）

当需要在页面中展示大量文本时，如果每段的文本都很长，阅读起来就会非常麻烦，有可能读错行或读串行。为了提高阅读的舒适性，CSS3 中引入了多列布局模块，用于以简单有效的方式创建多列布局。所谓多列布局指的就是您可以将文本内容分成多块，然后让这些块并列显示，类似于报纸、杂志那样的排版形式，如下图所示：



![column](D:\software\Typora\复制的图片文件\1112331T9-0.gif)
图：多列布局演示

CSS3 中提供了一系列实现多列布局的属性，如下表所示：



| 属性              | 说明                                        |
| ----------------- | ------------------------------------------- |
| column-count      | 指定元素应该分为几列                        |
| column-fill       | 指定如何填充每个列                          |
| column-gap        | 指定列与列之间的间隙                        |
| column-rule       | 所有 column-rule-* 属性的简写形式           |
| column-rule-color | 指定列与列之间边框的颜色                    |
| column-rule-style | 指定列与列之间边框的样式                    |
| column-rule-width | 指定列与列之间边框的宽度                    |
| column-span       | 指定元素应该横跨多少列                      |
| column-width      | 指定列的宽度                                |
| columns           | column-width 与 column-count 属性的简写属性 |

# CSS box-sizing：改变盒子模型

默认情况下，网页中元素的实际宽度或高度取决于元素内容区的宽度或高度、内边距以及边框属性的大小，因此我们在为元素布局时还需要考虑元素的内边距和边框属性所占的页面空间，这一点我们已经在《[CSS盒子模型](https://c.biancheng.net/css3/box-model.html)》中进行了讲解。

正是由于上述原因，当您为页面元素设置宽度和高度时，元素的实际大小往往比您设置的要大。为此 CSS3 中添加了 box-sizing 属性来改变默认的盒子模型，通过 box-sizing 属性可以将元素的内边距和外边距在元素内容区内绘制，以使元素呈现的宽度和高度与设置的宽度和高度相同。

box-sizing 属性的可选值如下：



| 值          | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| content-box | 默认值，元素的实际宽度或高度等于元素内容区的宽度或高度、内边距和边框的和 |
| border-box  | 在元素的内容区内绘制内边距或边框，内边距或边框不会影响元素的实际宽度或高度 |
| inherit     | 从父元素继承 box-sizing 属性的值。                           |

# CSS filter（滤镜）

说起滤镜可能大家首先想到的就是 PhotoShop 之类的制图软件，通过此类软件的滤镜可以对图片进行美化。而在 CSS 中，我们无需借助任何软件也可以实现很多种滤镜效果，例如模糊效果、透明效果、色彩反差调整、色彩反相等等。另外，通过 CSS 中的滤镜还能对网页中的元素或者视频进行处理。本节我们就来学习一下 CSS 中滤镜的使用。

CSS 中实现滤镜效果需要通过 filter 属性并配合一些函数来实现，如下所示：



| 滤镜                                             | 描述                                                         |
| ------------------------------------------------ | ------------------------------------------------------------ |
| none                                             | 默认值，表示没有效果                                         |
| blur(px)                                         | 为图像设置高斯模糊，默认值为 0，单位为像素，值较大越模糊     |
| brightness(%)                                    | 调整图像的亮度，默认值为 100％，代表原始图像；0％ 表示没有亮度，图像将完全变黑；当值超过 100％ 时图像将变得更亮 |
| contrast(%)                                      | 调整图像的对比度，默认值为 100％，代表原始图像；0％ 将使图像完全变黑；当值超过 100％ 时图像将获得更高的对比度 |
| drop-shadow(h-shadow v-shadow blur spread color) | 为图像添加阴影效果，参数说明如下：h-shadow：必填值，指定水平方向阴影的像素值，若值为负，则阴影会出现在图像的左侧；v-shadow：必填值，指定垂直方向阴影的像素值，若值为负，则阴影会出现在图像的上方；blur：可选值，为阴影添加模糊效果，默认值为 0，单位为像素，值越大创建的模糊就越多（阴影会变得更大更亮），不允许使用负值；spread：可选值，默认值为 0，单位为像素。若值为正，则阴影将会扩展并增大；若值为负，则阴影会缩小；color：可选值，为阴影添加颜色，如未指定，则由浏览器来绝对，通常为黑色。注意：Chrome、Safari 和 Opera 等浏览器不支持第 4 个参数，如果添加，则不会有任何效果 |
| grayscale(%)                                     | 将图像转换为灰度图像，默认值为 0%，表示原始图像；100％ 表示将图像完全变成灰度图像（即黑白图像），不允许为负值 |
| hue-rotate(deg)                                  | 给图像应用色相旋转，该值用来定义色环的度数，默认值为 0deg，代表原始图像，最大值为 360deg |
| invert(%)                                        | 反转图像，默认值为 0%，表示原始图像；100% 则表示完全反转，不允许使用负值 |
| opacity(%)                                       | 设置图像的不透明度，默认值为 100%，表示原始图像；0% 表示完全透明，不允许使用负值 |
| saturate(%)                                      | 设置图像的饱和度，默认值为 100%，表示原始图像；0% 表示图像完全不饱和，不允许使用负值 |
| sepia(%)                                         | 将图像转换为棕褐色，默认值为 0%，表示原始图像；100% 表示图像完全变成棕褐色，不允许使用负值 |
| url()                                            | url() 函数用来指定一个 XML 文件，文件中设置了一个 SVG 滤镜，并且可以包含一个锚点来指定具体的滤镜元素 |
| initial                                          | 将属性设置为其默认值                                         |
| inherit                                          | 从父元素继承此属性的值                                       |

提示：这些 CSS 函数的参数值基本上都在 0~1（0%~100%）之间，但也有几个例外，比如 blur() 函数的参数值以像素为单位，而 hue-rotate() 函数的参数值则是以“deg”为单位。

```css
<!DOCTYPE html>
<html>
<head>
    <style>
        div {
            width: 200px;
            height: 200px;
            float: left;
            position: relative;
        }
        div span {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: white;
            text-shadow: 1px 1px 2px black;
        }
        img {
            width: 100%;
        }
        div img.blur {
            filter: blur(4px);
        }
        div img.brightness {
            filter: brightness(250%);
        }
        div img.contrast {
            filter: contrast(180%);
        }
        div img.grayscale {
            filter: grayscale(100%);
        }
        div img.huerotate {
            filter: hue-rotate(180deg);
        }
        div img.invert {
            filter: invert(100%);
        }
        div img.opacity {
            filter: opacity(50%);
        }
        div img.saturate {
            filter: saturate(7);
        }
        div img.sepia {
            filter: sepia(100%);
        }
        div img.shadow {
            filter: drop-shadow(8px 8px 10px green);
        }
    </style>
</head>
<body>
    <div><img src="./tulip.jpg" alt="tulip">                   <span>原始图像</span></div>
    <div><img class="blur" src="./tulip.jpg" alt="tulip">      <span>blur(4px)</span></div>
    <div><img class="brightness" src="./tulip.jpg" alt="tulip"><span>brightness(250%)</span></div>
    <div><img class="contrast" src="./tulip.jpg" alt="tulip">  <span>contrast(180%)</span></div>
    <div><img class="grayscale" src="./tulip.jpg" alt="tulip"> <span>grayscale(100%)</span></div>
    <div><img class="huerotate" src="./tulip.jpg" alt="tulip"> <span>hue-rotate(180deg)</span></div>
    <div><img class="invert" src="./tulip.jpg" alt="tulip">    <span>invert(100%)</span></div>
    <div><img class="opacity" src="./tulip.jpg" alt="tulip">   <span>opacity(50%)</span></div>
    <div><img class="saturate" src="./tulip.jpg" alt="tulip">  <span>saturate(7)</span></div>
    <div><img class="sepia" src="./tulip.jpg" alt="tulip">     <span>sepia(100%)</span></div>
    <div><img class="shadow" src="./tulip.jpg" alt="tulip">    <span>drop-shadow(8px 8px 10px green)</span></div>
</body>
</html>
```

# CSS flex布局（弹性布局/弹性盒子）

Flex 是 Flexible Box 的缩写，意为“弹性布局”或者“弹性盒子”，是 CSS3 中的一种新的布局模式，可以简便、完整、响应式地实现各种页面布局，当页面需要适应不同的屏幕大小以及设备类型时非常适用。目前，几乎所有的浏览器都支持 Flex 布局。

## 1. 基本概念

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称“容器”。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称“项目”。容器默认存在两根轴，分别为水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置叫做 main start，结束位置叫做 main end；交叉轴的开始位置叫做 cross start，结束位置叫做 cross end。项目默认沿主轴排列。单个项目占据的主轴空间叫做 main size，占据的交叉轴空间叫做 cross size。如下图所示：



![Flex 容器](D:\software\Typora\复制的图片文件\1504491454-0.gif)
图：Flex 容器

提示：您可以通过将元素的 display 属性设置为 flex（生成块级 flex 容器）或 inline-flex（生成类似 inline-block 的行内块级 flex 容器）。当一个元素设置了 Flex 布局以后，其子元素的 float、clear 和 vertical-align 等属性将失效。

CSS 中提供了以下属性来实现 Flex 布局：



| 属性            | 描述                                                         |
| --------------- | ------------------------------------------------------------ |
| display         | 指定 HTML 元素的盒子类型                                     |
| flex-direction  | 指定弹性盒子中子元素的排列方式                               |
| flex-wrap       | 设置当弹性盒子的子元素超出父容器时是否换行                   |
| flex-flow       | flex-direction 和 flex-wrap 两个属性的简写                   |
| justify-content | 设置弹性盒子中元素在主轴（横轴）方向上的对齐方式             |
| align-items     | 设置弹性盒子中元素在侧轴（纵轴）方向上的对齐方式             |
| align-content   | 修改 flex-wrap 属性的行为，类似 align-items，但不是设置子元素对齐，而是设置行对齐 |
| order           | 设置弹性盒子中子元素的排列顺序                               |
| align-self      | 在弹性盒子的子元素上使用，用来覆盖容器的 align-items 属性    |
| flex            | 设置弹性盒子中子元素如何分配空间                             |
| flex-grow       | 设置弹性盒子的扩展比率                                       |
| flex-shrink     | 设置弹性盒子的收缩比率                                       |
| flex-basis      | 设置弹性盒子伸缩基准值                                       |

按照作用范围的不同，这些属性可以分为两类，分别为容器属性（flex-direction、flex-wrap、flex-flow、justify-content、align-items、align-content）和项目属性（order、align-self、flex、flex-grow、flex-shrink、flex-basis）。下面就来介绍一下这些属性的使用。

## 2. 容器属性

### 1) flex-direction

flex-direction 属性用来决定主轴的方向（即项目的排列方向），属性的可选值如下：



| 值             | 描述                           |
| -------------- | ------------------------------ |
| row            | 默认值，主轴沿水平方向从左到右 |
| row-reverse    | 主轴沿水平方向从右到左         |
| column         | 主轴沿垂直方向从上到下         |
| column-reverse | 主轴沿垂直方向从下到上         |
| initial        | 将此属性设置为属性的默认值     |
| inherit        | 从父元素继承此属性的值         |

### 2) flex-wrap

flex-wrap 属性用来设置当弹性盒子的子元素（项目）超出父容器时是否换行，属性的可选值如下：



| 值           | 描述                                     |
| ------------ | ---------------------------------------- |
| nowrap       | 默认值，表示项目不会换行                 |
| wrap         | 表示项目会在需要时换行                   |
| wrap-reverse | 表示项目会在需要时换行，但会以相反的顺序 |
| initial      | 将此属性设置为属性的默认值               |
| inherit      | 从父元素继承属性的值                     |

### 3) flex-flow

flex-flow 属性是 flex-direction 和 flex-wrap 两个属性的简写，语法格式如下：

```css
flex-flow: flex-direction flex-wrap;
```

### 4) justify-content

justify-content 属性用于设置弹性盒子中元素在主轴（横轴）方向上的对齐方式，属性的可选值如下：



| 值            | 描述                             |
| ------------- | -------------------------------- |
| flex-start    | 默认值，左对齐                   |
| flex-end      | 右对齐                           |
| center        | 居中                             |
| space-between | 两端对齐，项目之间的间隔是相等的 |
| space-around  | 每个项目两侧的间隔相等           |
| initial       | 将此属性设置为属性的默认值       |
| inherit       | 从父元素继承属性的值             |

### 5) align-items

align-items 属性用来设置弹性盒子中元素在侧轴（纵轴）方向上的对齐方式，属性的可选值如下：



| 值         | 描述                           |
| ---------- | ------------------------------ |
| stretch    | 默认值，项目将被拉伸以适合容器 |
| center     | 项目位于容器的中央             |
| flex-start | 项目位于容器的顶部             |
| flex-end   | 项目位于容器的底部             |
| baseline   | 项目与容器的基线对齐           |
| initial    | 将此属性设置为属性的默认值     |
| inherit    | 从父元素继承属性的值           |

几个属性值的效果如下图所示：



![align-items 属性演示](D:\software\Typora\复制的图片文件\1504492A2-5.gif)
图：align-items 属性演示

### 6) align-content

align-content 属性与 justify-content 属性类似，可以在弹性盒子的侧轴还有多余空间时调整容器内项目的对齐方式，属性的可选值如下：



| 值            | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| stretch       | 默认值，将项目拉伸以占据剩余空间                             |
| center        | 项目在容器内居中排布                                         |
| flex-start    | 项目在容器的顶部排列                                         |
| flex-end      | 项目在容器的底部排列                                         |
| space-between | 多行项目均匀分布在容器中，其中第一行分布在容器的顶部，最后一行分布在容器的底部 |
| space-around  | 多行项目均匀分布在容器中，并且每行的间距（包括离容器边缘的间距）都相等 |
| initial       | 将此属性设置为属性的默认值                                   |
| inherit       | 从父元素继承该属性的值                                       |

几个属性值的效果如下图所示：



![align-content 属性演示](D:\software\Typora\复制的图片文件\15044a4X-6.gif)
图：align-content 属性演示

## 3. 项目属性

### 1) order

order 属性用来设置项目在容器中出现的顺序，您可以通过具体的数值来定义项目在容器中的位置，属性的语法格式如下：

```css
order: number;
```

其中 number 就是项目在容器中的位置，默认值为 0。

### 2) align-self

align-self 属性允许您为某个项目设置不同于其它项目的对齐方式，该属性可以覆盖 align-items 属性的值。align-self 属性的可选值如下：



| 值         | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| auto       | 默认值，表示元素将继承其父容器的 align-items 属性值，如果没有父容器，则为“stretch” |
| stretch    | 项目将被拉伸以适合容器                                       |
| center     | 项目位于容器的中央                                           |
| flex-start | 项目位于容器的顶部                                           |
| flex-end   | 项目位于容器的底部                                           |
| baseline   | 项目与容器的基线对齐                                         |
| initial    | 将此属性设置为属性的默认值                                   |
| inherit    | 从父元素继承属性的值                                         |

#### 3) flex

flex 属性是 flex-grow、flex-shrink 和 flex-basis 三个属性的简写，语法格式如下：

```css
flex: flex-grow flex-shrink flex-basis;
```

参数说明如下：

- flex-grow：（必填参数）一个数字，用来设置项目相对于其他项目的增长量，默认值为 0；
- flex-shrink：（选填参数）一个数字，用来设置项目相对于其他项目的收缩量，默认值为 1；
- flex-basis：（选填参数）项目的长度，合法值为 auto（默认值，表示自动）、inherit（表示从父元素继承该属性的值） 或者以具体的值加 "%"、"px"、"em" 等单位的形式。

另外，flex 属性还有两个快捷值，分别为 auto（1 1 auto）和 none（0 0 auto）。

除了可以使用 flex 属性外，您也可以使用 flex-grow、flex-shrink、flex-basis 几个属性来分别设置项目的增长量、收缩量以及项目长度，例如：

```css
.flex div:nth-child(4) {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: auto;
    /* 等同于 flex:1 1 auto; */
}
```

# CSS resize（调整元素大小）

为了增强用户体验，CSS3 中新增了一个非常实用的 resize 属性，该属性允许用户通过拖动的方式来自由缩放元素的尺寸，在此之前要实现类似的效果还需要借助大量的 JavaScript 代码。resize 属性的语法格式如下：

```css
resize: none|both|horizontal|vertical;
```

语法说明如下：

- none：用户无法调整元素的尺寸；
- both：用户可调整元素的高度和宽度；
- horizontal：用户可调整元素的宽度；
- vertical：用户可调整元素的高度。

在使用 resize 属性时还需要注意以下几点：

- 单独设置 resize 属性是无效的，resize 属性需要与 overflow 属性结合使用才有效，并且 overflow 属性的值需要设置为 auto、hidden 或 scroll；
- 并不是所有的元素都可以设置 resize 属性，比如 img 和 table 属性就没办法使用 resize 属性。

# CSS响应式布局（自适应布局）

CSS 响应式布局也称自适应布局，是 Ethan Marcotte 在 2010 年 5 月份提出的一个概念，简单来讲就是一个网站能够兼容多个不同的终端（设备），而不是为每个终端做一个特定的版本。这个概念是为解决移动端浏览网页而诞生的。响应式布局能够为使用不同终端的用户提供很好的用户体验，而且随着大屏智能手机的普及，用“大势所趋”来形容也不为过。

要实现响应式布局，常用的方式有以下几种：

- 使用 CSS 中的媒体查询（最简单）；
- 使用 JavaScript（使用成本比较高）；
- 使用第三方开源框架（例如 bootstrap，可以很好的支持各种浏览器）。

接下来我们以媒体查询为例来具体演示一下响应式布局的实现。

## 设置 meta 标签

首先，我们需要设置 meta 标签来告诉浏览器，让视口（网页的可视区域）的宽度等于设备的宽度，并禁止用户对页面的缩放，如下所示：

<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">

在设置视口时需要注意，视口就是网页可见区域的尺寸，设置视口时只设置宽度就行，不用在乎高度，具体高度由网页内容自动撑开。上面 meta 标签中内容的含义如下：

- viewport：即视口，表示网页的可视区域；
- width：控制 viewport 的大小，可以指定一个具体的值，例如 600，也可以是由关键字组成的特殊值，例如 device-width 就表示设备的宽度；
- initial-scale：表示初始缩放比例，也就是页面第一次加载时的缩放比例；
- maximum-scale：表示允许用户缩放的最大比例，范围从 0 到 10.0；
- minimum-scale：表示允许用户缩放到最小比例，范围从 0 到 10.0；
- user-scalable：表示用户是否可以手动缩放，“yes”表示允许缩放，“no”表示禁止缩放。

## 媒体查询

[CSS 媒体查询](https://c.biancheng.net/css3/media.html)可以根据指定的条件，针对不同的媒体类型（screen print）定义不同的 CSS 样式，让使用不同设备的用户都能得到最佳的体验。

关于媒体查询有以下三种实现方式：

### 1、直接在 CSS 文件中使用

```css
@media (max-width: 320px) {
    /*0~320*/
    body {
        background: pink;
    }
}
@media (min-width: 321px) and (max-width: 375px) {
    /*321~768*/
    body {
        background: red;
    }
}
@media (min-width: 376px) and (max-width: 425px) {
    /*376~425*/
    body {
        background: yellow;
    }
}
@media (min-width: 426px) and (max-width: 768px) {
    /*426~768*/
    body {
        background: blue;
    }
}
@media (min-width: 769px) {
    /*769~+∞*/
    body {
        background: green;
    }
}
```

### 2、使用 @import 导入

```css
@import 'index01.css' screen and (max-width:1024px) and (min-width:720px)@import 'index02.css' screen and (max-width:720px)
```

### 3、在 link 标签中使用

```css
<link rel="stylesheet" type="text/css" href="index01.css" media="screen and (max-width:1024px) and (min-width:720px)"/><link rel="stylesheet" type="text/css" href="index02.css" media="screen and (max-width:720px)"/>
```























