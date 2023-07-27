# 仪表板
---

仪表板（Dashboard）允许用户快速轻松地将逻辑视图中的元素组合成任何人都可以使用的交互式、美观的 Web 应用程序。提供一个直观的图形化界面，可以展示和解析大量的数据。它可以将复杂的数据集转化为更易理解的图表和图形，使得业务决策者能够迅速理解数据，并据此做出决策。

通过仪表板我们可以将原始数据转化为可行的见解和战略成果来提升你的决策过程


一个仪表板可以包含多种类型的视图，例如条形图、饼图、折线图、地图、表格等等。这些视图都是由数据驱动的，可以实时或定期更新。仪表板可以展示各种关键性能指标（KPI），比如销售额、客户满意度、员工绩效等。

用户可以通过交互式操作，比如过滤、钻取、切片和切块等来查看不同的数据视角和层级。这使得用户能够深入理解数据，发现数据的趋势和模式。


![图 0](../images/426a75ba60aa205938e2fd63314f7e55ea3c0bfae86f6cbffb8f5fbac3b6192f.png)  

仪表板主要特征如下：

- 支持拖拽notebook 生成各种类型文本、图片、图表等添加到仪表板上。
- 通过拖拽改变图表大小和位置实现自由布局。
- 仪表板有强大的自定义功能（包括自定义容器大小，设置仪表板的背景图片包括颜色和水印等）。
- 支持预览、分享和嵌入到数据门户中
- 支持通过调度定期更新仪表板。
- 支持交互组件动态刷新、数据下钻（功能测试中）


## 创建/修改仪表板

要创建/修改仪表板，请打开相对应的NoteBook。在右上角点击<img style="display: inline-block;padding:0px;border:0px" src="../images/35c3df6dc0f939b38721ff40d40174ee7c117f77edede0fa1743430d4167e75f.png"  />，弹出仪表板的设计界面。


> [!NOTE]
> 请注意，每个NoteBook只能创建和发布一个仪表板。如果您需要发布多个仪表板，请将您的NoteBook复制多个副本来实现。

## 操作按钮


| 图标 | 操作 | 解释 | 备注 |
| :-----| :-----| :---- | :---- | 
| <img src="../images/6e96c88651800e935ed4c70ea00245fc4d354e6585d689e59a261522e7f8aff0.png"  style="display: inline-block;padding:0px;border:0px"  /> | 画布设置 | 对画布属性进行配置，如像素大小，背景设置等 | -  | 
| <img src="../images/b0773cbfa0f2c640acf3a741b68a875a2b2fd02aa138b779d04be3412505af7b.png"  style="display: inline-block;padding:0px;border:0px"  /> | 小地图 | 打开/关闭画布小地图 | - | 
|  <img src="../images/25d7fe58a21e28a4c80444ab472bf5bae250bdfea210af49128666e71cfa7786.png"  style="display: inline-block;padding:0px;border:0px"  /> | 上一步 | 回退到上一步的画布状态 | - |
|  <img src="../images/2d9a895d29cea49d008043e368704b99a1a3f1c6a45da4721f1adbad445587dc.png"  style="display: inline-block;padding:0px;border:0px"  /> | 下一步 | 前进到下一步的画布状态（用户之前有做上一步的操作） | -  |
|  <img src="../images/f48e2b9b4ba5f61a5ea878ee08219b508111a8f58daaaa2a378bd60f75bf91a6.png"  style="display: inline-block;padding:0px;border:0px"  /> | 清空画布 | 清空画布中的所有组件 | - |
|  <img src="../images/4401a590c0c3131c6960b2ebe248b7a19a4a87ab392eb8979175c5017a6ebc92.png"  style="display: inline-block;padding:0px;border:0px"  /> | 适应屏幕 | 画布自适应调整到合适的大小和位置 | -  |
|  <img src="../images/a991261f29c064df0b57533e30a19b033c2b51c20f521746727b99db17458d42.png"  style="display: inline-block;padding:0px;border:0px"  /> | 隐藏左侧菜单 | 隐藏/显示左侧的操作按钮 | - |
|  <img src="../images/1c19222318dc4e581e7367583a9794d79413d412e81c05e10a571991f1bd225a.png"  style="display: inline-block;padding:0px;border:0px"  /> | 隐藏右侧菜单 | 隐藏/显示左侧的操作按钮 | - |
|  <img src="../images/4186043d86d5fa8c5dfe0ffb398d335ad948679ba38491ccf3752ef2720ea702.png"  style="display: inline-block;padding:0px;border:0px"  /> | 保存 | 保存当前画布的状态 | -  |
|  <img src="../images/2c7204369c33a2052cc32653e373563e1ca4bd1fab1ff863c7244a73fd026b42.png"  style="display: inline-block;padding:0px;border:0px"  /> | 发布/更新发布 | 仪表板设计完成/修改后生成发布链接 | -  |
|  <img src="../images/5d90b2f9bb7e02451e4de36754818428ba41b3a17cc59002834fead908b4afaf.png"  style="display: inline-block;padding:0px;border:0px"  /> | 预览 | 生成预览链接，预览仪表板内容 | -  |
|  <img src="../images/59cb15031a4445215f9d5163cdcc278cdc97044408e867fd2eedc9af934fe779.png"  style="display: inline-block;padding:0px;border:0px"  /> | 关闭 | 关闭仪表板界面（重新打开显示最后保存的画布内容） | - |

## 设计仪表板

您可以使用右侧的拖动手柄从左侧的“轮廓”面板中拖放元素。或者，您可以使用每个元素上的“添加到应用程序”按钮。

## 重新发布

重新出版
每当您对其进行更改时，您的笔记本都不会自动重新发布。要重新发布包含最新更改的笔记本，请转到发布编辑器并单击“发布更改”。

已发布项目的 URL 在重新发布后保持不变，因此您不必担心与受众共享新 URL。

## 操作案例

![图 1](../images/32f51c6fb8b971e483154c0e7718b4f4e3bf06e56c57528b45201184fe57cafb.png)  
