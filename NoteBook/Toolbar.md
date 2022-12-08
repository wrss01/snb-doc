# 工具栏
---
工具栏提供对文件、Kernel和终端等的一系列扩展操作

![图 1](../images/toobar%E7%9A%84%E6%93%8D%E4%BD%9C.png)  


具体包含：

* 文件
  * 最近打开的
  * 分享
  * 重命名
  * 导出.ipynb
  * 导出.snb
* 工具
  * 保存版本
  * 历史版本
  * 添加数据资源
  * 目录
  * Packages
  * 变量预览
  * 环境
  * 代码片段
  * 终端
  * 生成Graph
* Kernel
  * 中断Kernel
  * 重启Kernel
* 运行
  * 全部运行
  * 运行当前及上方所有单元格
  * 运行当前及下方所有单元格
  * 运行当前sheet的所有单元格
* 帮助
  * 快捷键
  * 帮助手册


# 文件
---
* 最近打开的：可查看最近打开的NoteBook文档
* 分享：分享当前NoteBook文档，功能参考<a href="./Share.md" title="分享">分享</a>
* 重命名：给当前NoteBook重新起一个名称
* 导出.ipynb：将当前NoteBook导出为.ipynb文件并下载至本地
* 导出.snb：将当前NoteBook导出为.snb文件并下载至本地


## 工具
---
* 保存版本
* 历史版本
* 添加数据资源
* 目录
* Packages
* 变量预览
* 环境
* 代码片段
* 终端
* 生成Graph

# Kernel（内核）
---
每个NoteBook都具备底层内核，这些内核本质上是运行代码的程序。

Kernel 连接服务端的计算资源，当内核处于连接状态时，才能正常运行NoteBook中的代码。

## 中断Kernel

kernel 的中断（Kernel interrupt）是指kernel 正在运行代码中断运行（Kernel interrupt），针对notebook 内单元格（cell) 中断包括正在运行cell 和待运行的cell。
 
点击左上角的停止按钮中断Kernel

![](/assets/zdkr.png)

或是点击工具栏的`中断kernel`

![](/assets/zdkr2.png)

## 重启Kernel（内核）

当环境发生变化（如环境安装了新的包），需要重启Kernel时使用。

![](/assets/cqkr.png)


# 运行

运行Notebook内的各类型代码及组件

![](/assets/yxdm.png)

## 全部运行

批量运行Notebook下所有sheet内的全部代码块（Cell）

## 运行当前及上方所有单元格

批量运行Notebook下选中的代码块前的所有Cell（当前sheet范围内）

## 运行当前及下方所有单元格

批量运行Notebook下选中的代码块后的所有Cell（当前sheet范围内）

## 运行当前sheet的所有单元格

批量运行Notebook下的所有Cell（当前sheet范围内）


# 终端

用户可通过终端连接至容器，查看和操作服务器上的资源。

![](/assets/zdtr.png)

# Graph

SmartNotebook可根据代码块间的变量引用关系自动生成Graph，直观清洗展示各个代码块（Cell）间的相互关系和整体脉络。

该设计主要存在以下几点好处：

- 可解释性：很容易看到各代码块（Cell）如何相互关联，以及查看整个NoteBook代码逻辑的“流动”，跟踪你复杂逻辑的可视化“思维导图”。

- 性能：在模型开发过程中，这种新的DAG模型几乎不会产生额外的性能开销，对性能不会有任何影响。

## 代码块（cell）是如何连接在一起的

Graph是根据代码块中的参数引用自动构建的。

如下图我们可以看到各个DataFrame的生成过程以及引用过程。这些联系是SmartNoteBook自动推断的，无需用户去定义。

![](/assets/gra.png)

> [!Tip]
> Graph中的代码片段用户可以随意拖动。





