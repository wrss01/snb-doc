# 代码块（Cell）概述
---
在NoteBook中，代码块是编写、运行、分享 `代码/图表/MarkDown` 的最小单元。

## 代码块的状态

- 代码块未执行

![图 2](../images/%E6%9C%AA%E6%89%A7%E8%A1%8C%E7%8A%B6%E6%80%81.png)  

- 代码块处于运行状态，会有<img src="../assets/zzzz.png"  style="display: inline-block;" />标志

![](/assets/xzms.png)

- 代码块执行结束。在执行按钮旁会显示执行时长，代码块左上方增加行号显示

![图 4](../images/%E6%89%A7%E8%A1%8C%E7%BB%93%E6%9D%9F%E7%8A%B6%E6%80%81%E6%98%BE%E7%A4%BA.png)  


## 代码块的类型

<b>Code类型：</b>

* `Python代码`：详见 <a href="./Python.md" title="Python代码块">Python代码块</a>
* `SQL代码`：详见 <a href="./SQL.md" title="SQL代码块">SQL代码块</a>
* `MarkDown`：详见 <a href="./Markdown.md" title="Markdown代码块">Markdown代码块</a>

<b>Data Display：</b> 
* `Chart`：详见 <a href="./Visualization.md" title="可视化">可视化组件</a>
* `Snb table`:详见 <a href="./Visualization.md" title="可视化">可视化组件</a>
* `EDA分析`:详见 <a href="./EDA.md" title="EDA组件">EDA组件</a>
* `EDA概览`:详见 <a href="./EDA.md" title="EDA组件">EDA组件</a>

<b>Data Transform：</b> 
* `数据透视表`:详见 <a href="./DataTransform.md" title="数据透视表">数据透视表</a>

![图 5](../images/%E4%BB%A3%E7%A0%81%E5%9D%97%E7%9A%84%E7%B1%BB%E5%9E%8B%E5%B1%95%E7%A4%BA.png)  


## 代码块的操作

* 执行代码
* 折叠/展开
  * input 折叠：折叠状态下只显示一行，或一行的高度内；状态切换
  * output 折叠：折叠状态下只显示一行，或一行的高度内；状态切换
* 新增cell
* 转换cell类型
* 删除cell
* 向上插入cell
* 向下插入cell
* 分享单元格输出
* 全屏/退出全屏
* 执行以上所有代码
* 代码自动补全
  * 引号补齐，包括单引号、双引号，英文半角下单双引号，`'`  --&gt; `''`    `"`--&gt; `""`
  * 三引号补齐，包括三单引号、三双引号，英文半角下三单双引号 `"""` -&gt;`""""""`   `'''`  --&gt; `''''''`
  * 文本选定，添加单双引号,选定文本输入单引号或双引号 ，文本添加双引号
  * 单行或多行注释快捷键
* SQL代码块类型下
  * 选择数据库
  * 变量名
* 代码块状态
* 代码框左侧颜色
* 鼠标处于代码框内右键操作
  * 剪切
  * 拷贝

## 代码块模式状态

Cell的状态为两种：**编辑状态**、**命令状态** ，两者可以相互切换。

* 编辑状态：input 输入框处于编辑状态，焦点处于代码输入框中
* 命令状态：当前Cell 处于选定状态，焦点不位于input输入框中。
* 状态切换：
  * Enter 回车：命令状态 --转化为--&gt;编辑状态
  * ESC   取消：编辑状态--转化为--&gt;命令状态

> [!Tip]
> 可根据Cell代码块左侧颜色来判断Cell处于`编辑状态`还是`命令状态`。蓝色为`命令状态`，显示绿色为`编辑状态`。

## 代码块操作快捷键

* 删除当前CELL   连续按两次`d`键
* 插入Code单元格（在当前单元格前插入）`a`键
* 插入Code单元格（在当前单元格后插入）`b`键
* 单元格复制`c`键
* 单元格剪切`x`键
* 单元格黏贴`v`键   粘贴于当前选定的单元格下面

`注：快捷键只有"命令状态" 才有效`

## 代码块运行快捷键

* 运行当前单元格\(cell\) `Ctrl+Enter`
* 运行当前单元格\(cell\),并选定下面一个单元格  `Shift+Enter`
* 运行当前单元格\(cell\),并下面插入一个code 单元格\(code cell\)  `Alt+Enter`

`注：命令状态与编辑状态 都支持运行快捷键`

> [!Tip]
> 代码块操作的快捷键详见 <a href="./Shortcuts.md" title="快捷键">快捷键</a>

## 上下键切换代码块

在当前选定的单元格是命令状态时，可以上下键切换单元格（移动选定的单元格），上键往上移动选定，直到最上面一个单元为止。下键往下移动选定单元格，直到最下面的单元格为止。

