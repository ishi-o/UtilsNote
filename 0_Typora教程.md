<a id="HOME"></a>

---

[toc]

---

# 如何写一份`Markdown`?

## `Typora`简介

市面上有许多用于攥写`md`的软件，其中，`Typora`有“**所见即所得**”的特点，即你所看见的就是文件导出后的样子。基于这点，本文将介绍`Typora`中常见的转义指令，教会读者如何编写代码，数学公式等

## 常用记号

以下是一些常用的记号，关于其他功能可以视图模式下右键鼠标查看，例如引用、缩进等，按下左下角`</>`可以进入源代码模式

1. `'\'`：它是**转义记号**，类似`C`语言里的'\n'等，它可以将内嵌的命令转义
   	例如\`a\`和`a`，前者利用'\\'将'\`'转义，取消了它原本具有的“行代码”特性
   	您还可以用'\\'将它自身转义

2. `'#'`：它是**标题记号**，它可以将一行文字快捷地变为一级标题
   	格式为：# title，井号越多，标题等级越低
   	具有该功能的快捷键是`ctrl+number`(`number`表示标题等级)

3. `'*'`：它是**斜体记号**，两个`*`组成一队，可以将中间的文本变为*斜体*
   	例如\*abcd\*的效果为：*abcd*
   	具有该功能的快捷键是`ctrl+I`
   	3，4点'\*'可以替换为'\_'

4. `'**'`：它是**加粗记号**，两组`**`组成一对，可以将中间的文本**加粗**，且可以和斜体记号一起使用
   	例如\*\*\*abcd\*\*\*的效果为：***abcd***
   	具有该功能的快捷键是`ctrl+B`

5. '\`'(英文反引号)：它是**行内代码记号**，两个\`组成一对，可以将中间的文本变为`代码字体`，注意代码块内的记号会失效，例如使用'\\'将其转义时有时会产生混乱，**`行内代码可以加粗`**
   	例如\`#include\`的效果是：`#include`
   	具有该功能的快捷键是`shift+ctrl+`\`

6. `'```'`：它是**代码块记号**，三个反引号两组组成一对，可以在其中输入代码语言与相应代码等，例如：

   ```c
   int main() {
       return 0;
   }
   ```

7. `'$$'`：它是**居中数学公式**符，两组`$$`组成一对，可以在其中用`Latex`语法写入数学公式。使用时只需键入'$$'后按下回车即可。例如：
$$
a^{\varphi(x)}\%\ n=1\ (a与n互素)
$$
​	具体该如何写数学公式将在[这里](#Latex)讲述

8. `'$'`：它是**行内数学公式**符，两个`$`组成一对，可以在其中用`Latex`语法写入数学公式。使用时只需键入'\$'后按下[ESC]键即可。注意，该功能默认关闭，需要勾选'文件'->'偏好设置'->'`Markdown`'->'内联公式'后并重启才可使用
   	例如：$\begin{align}\int_0^{\Large\frac{\pi}{2}}f(\sin x)dx=\int_0^{\Large\frac{\pi}{2}}f(\cos x)dx\end{align}$
9. `'[]()'`：它是**链接记号**，在'[]'内输入文本，在'()'内输入链接，这个链接可以是**网址**、**本地文件**或**文章内锚点**，文件支持使用相对路径或绝对路径，但导出时都会转换为绝对路径
   	例如：[Baidu](https://www.baidu.com)，[aFile](./file)，[aFlag](#null)
   	注意，在`Typora`下需要`'crtl+左键'`才可跳转，导出后才可直接点击
10. `'![]()'`：它是**图像记号**，与链接记号类似，但只能输入图片文件的路径，且会解析图片
		例如：<img src="D:\Picture\Screenshots\屏幕截图 2023-12-22 192623.png" style="zoom:33%;" />
		图片可以缩放，即在前方的`html`标签内加上`style="zoom:num%"`，`num`为缩放比例
11. `'[toc]'`：它是**目录记号**，可以用它生成自带锚点的目录，例如开头所示的索引
12. `'---'`：它是**分割线记号**，可以用它生成一条直线，例如：
---

## `Latex`数学公式语法<a id="Latex"></a>

有关其他字符可以自行查阅[符号表](https://blog.csdn.net/wait_for_eva/article/details/84307306)

### 缩进符

`Latex`里空格不会被解析为实实在在的空格，需要使用转义符，即`'\ '(空格),'\\'(换行)`

### 颜色

`\color{color}{text}`：将`'text'`颜色变为`'color'`，例如：`\color{red}{abcd}`的效果是$\color{red}{abcd}$

### 关于函数

`Latex`默认字母为**斜体**，用函数符号得到的函数为正体，且可以规范写法，例如：$\begin{align}lim_{x\rightarrow0}，\lim_{x\rightarrow0}\end{align}$

如果需要使用正体，可以用**`\rm{text}`**，例如$abcd，\rm{abcd}$

### 常用特殊符号

如果需要**成块被纳入**范围需要使用`{}`，否则默认读取单个字符，例如：$x_abc和x_{abc}$
`{}`也同时担任块内解析的效果，即放缩符等出块后即失效

$x_a$	`x_a`
$e^x$	`e^x`
$\in$	`\in`
$\infty$	`\infty`
$\rightarrow$	`\rightarrow`(左箭头即`\leftarrow`，需加长则在前面加上`long`，下面同理)
$\leftrightarrow$	`\leftrightarrow`
$\leftrightarrows$	`\leftrightarrows`
$\rightleftharpoons$	`\leftrightharpoons`
$\Rightarrow$	`\Rightarrow`(若加长需加`Long`)
$\cup$	`\cup`
$\sim$	`\sim`
$\frac{UP}{DOWN}$	`\frac{UP}{DOWN}`

### 常用放缩符

$\small((\big(\Big(\bigg(\Bigg($	从左往右依次是`\small 正常 \big \Big \bigg \Bigg`，'正常项'之后的放缩符只能对`(),[],{},|,<,>,/,\`起作用，其中`\,{}`需要**转义**

$\small a\normalsize a\large a\Large a\LARGE a\huge a\Huge a$	从左往右依次是`\small \normalsize \large \Large LARGE \huge \Huge`，它们对所有字符都有效

### 常用环境符

环境符两两配对，其中的代码可以被分为多行并且可以对齐

`\begin{align}\end{align}`：**对齐**环境，它可以将$\lim_{x\rightarrow0}，\int_a^b，\sum_{i=1}^{10}$等变为$\begin{align}\lim_{x\rightarrow0}，\int_a^b，\sum_{i=1}^{10}\end{align}$
还可以将'&'置于每行开头，实现**左对齐**

`\begin{cases}\end{cases}`：**大括号**环境，它可以将多项列举在一个大括号范围内，例如：$sgn(x)=\begin{cases}1,&x>0\\0,&x=0\\-1,&x<0\end{cases}$，可以将'&'置于逗号后，实现**对齐条件**

### 常用特殊字母

$\alpha$	`\alpha`
$\beta$	`\beta`
$\gamma$	`\gamma`
$\Gamma$	`\Gamma`
$\delta$	`\delta`
$\Delta$	`\Delta`
$\epsilon$	`\epsilon`
$\varepsilon$	`\varepsilon`
$\xi$	`\xi`
$\varphi$	`\varphi`
$\phi$	`\phi`
$\Phi$	`\Phi`
$\eta$	`\eta`
$\theta$	`\theta`
$\pi$	`\pi`
$\lambda$	`\lambda`
$\mu$	`\mu`

### 常用运算符

$\le$	`\le(与Linux类似的less equal)`
$\ge$	`\ge(greater equal)`
$\xlongequal[a]{b}$	`\xlongequal[a]{b}`(自动伸长的等号)
$\ne$	`\ne(not equal)`
$\equiv$	`\equiv`
$\begin{align}\int\end{align}$	`\int`
$\begin{align}\iint\end{align}$	`\iint`
$\begin{align}\int_a^b\end{align}$	`\int_a^b`

$\begin{align}\sum_{i=1}^{10}\end{align}$	`\sum_{i=1}^{10}`

$\begin{align}\lim_{x\rightarrow+\infty}\end{align}$	`\lim_{x\rightarrow+\infty}`

$\sqrt a$	`\sqrt a`

$\sqrt[n]{abc}$	`\sqrt[n]{abc}`

$\begin{align}\Bigg|_a^b\end{align}$	`\Bigg|_a^b`

## 内嵌`HTML`

### 表格

`Typora`支持内嵌`HTML`，常见用法为写表格，例如：

<table border="2">
    <tr>
        <td>title</td>
        <td>body</td>
    </tr>
    <tr>
        <td>exp1</td>
        <td>111</td>
    </tr>
    <tr>
        <td>exp2</td>
        <td rowspan="4" style="display:table-cell; vertical-align:middle">11</td>
    </tr>
    <tr>
        <td>exp3</td>
    </tr>
</table>
<img src="D:\Picture\Screenshots\屏幕截图 2023-12-22 210507.png" style="zoom: 33%;" />

如图，使用`html`语法，写出一个四行两列的、边界值为2的、内容`'11'`被设置为占据四行且居中的表格

### 链接

`<a id="111"></a>`：这条元素定义了一个`id`为`'111'`的锚点，在文章内部可以通过`[点击](#111)`链接跳转到这个锚点，例如本文在目录处设定了一个`'HOME'`锚点，您可以[点击我](#HOME)来跳转

`<a href="https://www.baidu.com">Baidu</a>`：这条元素定义了一个链接为百度域名，显示内容为`'Baidu'`的链接，<a href="https://www.baidu.com">Baidu</a>

### 强制分页

`<div style="page-break-after: always;"></div>`

在导出时，这条元素将强制新建一页

### 透明字体及右对齐

`<p style="color: rgba(400, 0, 400, 0.2)" align="right">ishiooo</p>`

`style`属性中，前三个数字为`rgb`值，第四个数字为透明度

这条元素定义了一个透明度为0.2，内容为`'ishiooo'`，右对齐的段落：

<p style="color: rgba(400, 0, 400, 0.2)" align="right">ishiooo</p>

