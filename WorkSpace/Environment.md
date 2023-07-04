# Workspace环境
---
配置环境和镜像类型。

![图 1](../images/new_enve.png)  


## 新建/编辑环境（专业版或企业版）

选择左侧导航栏的`环境`，单击`新建环境配置`，选择型号配置和镜像类型并填写环境名称提交。

![图 1](../images/5e22381e4243227086dd4e07fcedc9a26d97347ff47fed07184b3d772c579911.png)  


如需修改环境配置，可单击`操作`列的`...`，然后点击`编辑环境`，修改完成后提交。

> [!NOTE|style:flat]
> 专业版或企业版的管理员拥有此功能权限，基础版无此功能。

## 查看和关闭Kernel实例

<p>单击环境列表前的 <img src="../images/%E6%9F%A5%E7%9C%8Bicon.png"  style="display: inline-block;padding:0px;border:0px"  /> 可查看该环境下所有打开的Kernel实例。</p>

<!-- ![图 2](../images/shutkernel.png)   -->
<!-- ![图 5](../images/709813ee04c07146e06dff10a5c925846da06c15bb0f7ab4c50b4f5921a58a4e.png)   -->

![图 3](../images/709813ee04c07146e06dff10a5c925846da06c15bb0f7ab4c50b4f5921a58a4e.png)  


如需关闭实例，可以选择相对应的NoteBook，点击右侧的`关闭`并确定。

<!-- ![图 4](../images/5fae9bed501e447c71285c8dac41a7ae9b4fc82c8fcddd51970d1a945c53968d.png)   -->
![图 4](../images/5fae9bed501e447c71285c8dac41a7ae9b4fc82c8fcddd51970d1a945c53968d.png)  


> [!NOTE|style:flat]
> 如果 kernel 实例在当前环境中超过 12 小时没有被使用，系统将会自动释放该 kernel 实例以节省资源。

## 环境状态

环境拥有两种状态：

- `正常`：环境按照预期的方式工作，没有出现任何错误或故障
- `异常`：环境发生了一些不寻常或不符合预期的情况，可能无法正常工作，功能可能受限或完全无法使用。

<!-- ![图 7](../images/812ff8bb3c282a2e927da2acc91cf872238f982aceae7186550de227dff40f77.png)   -->


## 查看环境的运行和使用状态

详见侧边栏的<a href="./Sidebar.md/#sv" title="切换环境">环境-查看配置/负载情况</a> 

## 切换环境

详见侧边栏的<a href="./Sidebar.md/#sv" title="切换环境">环境-切换环境</a> 

## 删除环境

在`WorkSpace环境`标签页，找到需要删除的环境，单击`操作`列的`...`，然后点击`删除`。

<!-- ![图 8](../images/f48523a219be4c55207a08d3129f8a76f550d4805a38ec832de4b177ba3b9098.png)   -->
![图 5](../images/f48523a219be4c55207a08d3129f8a76f550d4805a38ec832de4b177ba3b9098.png)  

> [!Warning]
> 注：如环境已被使用，需将此环境下所有的NoteBook删除后才可删掉环境。
