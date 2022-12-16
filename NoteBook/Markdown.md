# MarkDown代码块
---
MarkDown代码块为我们提供了一个熟悉的、所见即所得的MarkDown编辑器环境。

Markdown代码块允许您编写纯文本并使用Markdown语法规则设置格式。此外还支持标准的LaTex数学公式和符号，因此您也可以非常方便的在文本中插入数学符号。

Markdown代码块通常用作代码的解释性或描述性文本，此外SmartNoteBook还会根据MarkDown的标题结构和层级帮助我们自动生成大纲目录，方便我们快速掌握文档结构。

![图 1](../images/%20MarkDown%E4%BB%A3%E7%A0%81%E5%9D%97%E7%8E%AF%E5%A2%83.png)  

## 创建MarkDown

创建MarkDown的两种方法：

* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`MarkDown`。

![图 8](../images/new%20md.png)  


* 直接单击代码块右上角的 `+` 号或者单元格下方的`Add Code Cell`，然后点击右上角的<img src="../assets/cvvr.png"  style="display: inline-block;" />，选择`Convert to Markdown`。

![](/assets/cvmarkd.png)

## MarkDown的操作

* 编写MarkDown

如果熟悉MarkDown的语法规则，您可以直接在编辑框中书写MarkDown代码；如果不太熟悉，也可以借助上方的快捷工具栏来辅助您调整格式、上传图片以及嵌入链接等。下方会提到几个例子帮您熟悉MarkDown的语法。

* 执行代码块

MarkDown编写完成后无需执行，将鼠标移动至代码块以外即可保存和显示。

![](/assets/mrakeddown2.png)

* 添加标题

要添加标题，请使用`#`符号后加一个空格然后跟标题文本。您最多可以添加6个`#`，标题的层级将随着每添加一个`#`而减小一个层级：

![图 4](../images/%E6%A0%87%E9%A2%98.png)  

* 添加列表

要在MarkDown中创建无序列表，请使用`*`或`-`符号。要创建有序列表，请使用前面跟有数字的`)`或`.`符号。（注意：符号后需跟一个空格后再输入列表内容）

![图 5](../images/%E5%88%97%E8%A1%A8.png)  

* 添加链接

要添加指向网站的链接，您可以将文本括在方括号`[]`中，后跟用括号`()`括起来的URL。

![图 6](../images/%E9%93%BE%E6%8E%A5%E5%9C%B0%E5%9D%80.png)  

* 插入代码

您可以通过将文本换行在反引号中来突出显示文本中的变量，也可以在文本前后使用3个反引号来创建代码块。

![图 7](../images/daimakuai.png)  

* 插入引用

要创建块引用，请使用`>`符号加一个空格然后跟文本内容：

![图 8](../images/%E5%9D%97%E5%BC%95%E7%94%A8%E7%9A%84%E4%BE%8B%E5%AD%90.png)  

* 插入图片

直接复制粘贴图片即可将图片插入MarkDown代码块。

![图 9](../images/tupianMarkdown.png)  

当然，也可以采用MarkDown代码块提供的快捷工具栏：

![图 10](../images/%E5%BF%AB%E6%8D%B7%E6%93%8D%E4%BD%9C%E6%A0%8FMarkDown.png)  


* 插入LaTeX数学公式
  * 行内公式 `$x`=`1$` 与文字混排
  * 行间公式 `$$ x`=`1 $$` 独立成行
  * 语法和样例可参考[LaTex中文手册](https://1024th.github.io/MathJax_Tutorial_CN/#/)。

![图 7](../images/latex.png)  

* 更多Markdown 语法

更多Markdown 语法可参考此[Markdown基本语法](http://markdown.p2hp.com/basic-syntax/)。

## 代码块类型转换

您可以点击代码块右上角<img src="../images/markdownicon.png"  style="display: inline-block;" />将单元格从Markdown转换为Python或SQL代码块，反之亦然。

![图 2](../images/zhuanhuan.png)  
 
## MarkDown快捷键操作

MarkDown操作的快捷键详见<a href="./Shortcuts.md" title="快捷键">快捷键</a>
