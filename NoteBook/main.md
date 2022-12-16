# NoteBook
---
NoteBook是一个可以在浏览器中使用的交互式笔记本文档，它的核心任务是通过将文字、代码、图表、公式、结论都整合在一个文档中，能够将整个分析过程完整清晰地表述，并能够以网页的形式进行分享。Notebook可以实现将代码、文字完美结合起来，因此非常适合从事机器学习、数据分析等数据科学工作的人员使用。

![](/assets/nbooks.png)

## 新建Notebook

点击左下【新建Notebook】可以创建新的Notebook

![](/assets/xjnote.png)填写Notebook信息，并选择环境、Kernel类型和模式，最后点击提交

* kernel类型
  * python
  * R
  * sagemath
* 模式选择
  * Jupyter模式：经典的Jupyter模式，没有评估命令执行。计算停止后，笔记本状态不保存。
  * 交互模式：可重复模式强制固定自顶向下的评估顺序和自动重新计算低于修改的细胞。笔记本状态在每次计算单元格后保存，可以在单个编辑会话的任何时候恢复。
  
![图 1](../images/kernel%E7%B1%BB%E5%9E%8B%E7%9A%84%E9%80%89%E6%8B%A9.png)  

## 导入Notebook

点击左下【新建Notebook】右侧的下拉箭头，点击上传文件。  

![](/assets/scnbwj.png)  

拖拽.snb文件到长方形热区或点击下方从电脑选择.snb文件进行上传。

导入后的snb文件将在Notebook列表展示。  

![](/assets/drsnb.png)

## 修改Notebook标题

两种方式修改Notebook标题

* 在Notebook列表页面，选择要修改标题的Notebook，单击编辑按钮，修改完成后点击对钩进行提交。  
  ![](/assets/xgnb2.png)

* 在Notebook的代码页面，双击顶部中间的标题进行修改，修改完成后鼠标移动到任意其他位置即可提交。  
  ![](/assets/xgnbbt.png)

## 添加sheet
Notebook支持多个sheet，方便用户组织内容。
![](/assets/ssheet.png)

## 返回Workspace

单击浏览器的`后退`按钮或单击左上方SmartNoteBook的Logo区域可返回至Workspace管理页面。

## 成员同时打开一份NoteBook

当处于同一个Workspace下的组内成员打开同一份NoteBook文档时，后打开的成员会在页面上方收到提示：

```
xxxx 正在编辑，您所编辑的内容无法保持。请您另存为进行保存。
```

此时，请您根据提示另存或复制一份副本出来再进行修改和编辑。

![图 1](../images/%E5%90%8C%E6%97%B6%E7%BC%96%E8%BE%91.png)  
