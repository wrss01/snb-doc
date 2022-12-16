# 快捷键
---
SmartNoteBook支持许多键盘快捷键，为配合用户使用习惯，大多参考了标准Jupyter的快捷键。

## 编辑模式和命令模式

`命令模式`下，用户可以使用键盘快捷键来执行各种操作，而不是在单元格中编写代码。例如，在命令模式下，用户可以按 `Shift + Enter` 键来运行单元格中的代码。

![picture 2](../images/%E5%91%BD%E4%BB%A4%E6%A8%A1%E5%BC%8F%E6%A0%B7%E4%BE%8B.png)  

`编辑模式`指的是在NoteBook中编写代码的模式。在编辑模式下，用户可以在单元格中编写和编辑代码。要进入编辑模式，可以单击单元格并按 `Enter` 键，或者双击单元格。要退出编辑模式，可以按 `Esc` 键。

![picture 1](../images/%E7%BC%96%E8%BE%91%E6%A8%A1%E5%BC%8F%E6%A0%B7%E4%BE%8B.png)  

## 全局快捷键

* 文档级
  * `Ctrl + S`：版本保存
  
* 代码块（Cell）状态
  * `Enter`：命令状态 --转化为--&gt;编辑状态
  * `ESC`：编辑状态--转化为--&gt;命令状态
  
  
* 代码块（Cell）运行
  * `Ctrl+Enter`：运行当前单元格(cell) 
  * `Shift+Enter`：运行当前单元格(cell)，并选定下面一个单元格 
  * `Alt+Enter`：运行当前单元格(cell)，并下面插入一个code 单元格(code cell) 
  
> [!NOTE]
> 全局快捷键即无论处于命令模式还是编辑模式下都可正常使用。

## 命令模式下支持的快捷键

* 代码块（Cell）操作`注："命令状态" 才有效`
  * `D`+`D`：删除当前CELL
  * `A`：在当前单元格前插入单元格
  * `B`：在当前单元格后插入单元格
  * `C`：复制选中单元格
  * `X`: 剪切选中单元格
  * `V`: 粘贴单元格


## 编辑模式下支持的快捷键

* 代码块（Cell）编辑器的快捷键
  * `Ctrl+Alt+↓`:列选择
  * `Shift+Alt+↓/↑`：向上/向下复制行
  * `Ctrl+X`：剪切行
  * `Ctrl+C`：复制行
  * `ALT+↑/↓`：上下移动
  * `Ctrl+]/[`：缩进
  * `Home/End`：转到行的开头/转到行的末尾
  * `Ctrl+/`：切换行注释
  * `shift+Alt+A`：''' '''
  * `Ctrl + G`：跳转到行
  * `Ctrl + F`：查找
  * `Ctrl + H`：替换
  * `Ctrl + U`：撤消上一个光标操作
  * `Ctrl + F2`：选择当前字的所有出现
  * `Shift + Alt + →`：展开选择
  * `Shift + Alt + ←`：缩小选择
  * `Ctrl+Z`：撤销
  * `Ctrl+Y`: 重做
  * `Ctrl+X`: 剪切
  * `Ctrl+C`: 复制
  * `Ctrl+V`: 粘贴
  * `Ctrl+A`: 全选


* MarkDown代码块支持的快捷键
  
  * `Ctrl+Z`：撤销
  * `Ctrl+Y`: 重做
  * `Ctrl+X`: 剪切
  * `Ctrl+C`: 复制
  * `Ctrl+V`: 粘贴
  * `Ctrl+A`: 全选
  * `Home`：跳转到句首
  * `Ctrl+Home`：跳转到文首
  * `End`：跳转到句尾
  * `Ctrl+End`：跳转到文末
  * `Ctrl+1/2/3/4/5/6`：标题      
  * `TAB`：缩进
  * `SHIFT + TAB`：取消缩进
  * `CTRL+D`：删除选中行
  * `CTRL+BreakSpace`：清空所有内容
  * `CTRL+B`：**加粗**
  * `CTRL+I`：*斜体*
  * `CTRL+H`：# 标题
  * `CTRL+U`：++下划线++
  * `CTRL+M`：==标记==
  * `CTRL+Q`：> 引用
  * `CTRL+O`：1. 有序列表
  * `CTRL+L`：[链接标题](链接地址)
  * `CTRL+ALT+S`：	^上角标^
  * `CTRL+ALT+U`：- 无序列表
  * `CTRL+ALT+C`：``` 代码块
  * `CTRL+ALT+L`：`![图片标题](图片链接)`
  * `CTRL+ALT+T`：表格
  * `CTRL+SHIFT+S`：下角标
  * `CTRL+SHIFT+D`：~~中划线~~
  * `CTRL+SHIFT+C`：居中
  * `CTRL+SHIFT+L`：居左
  * `CTRL+SHIFT+R`：居右


