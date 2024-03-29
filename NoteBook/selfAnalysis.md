# SNB_自助数据分析
SNB_自助数据分析工具采用类似Tableau和PowerBI的展现方式，提供了一个拖拽式、交互式的可视化探索分析界面，能够充分利用客户端的算力，对大数据量进行高效支持。它简化了数据探索的操作，使分析师能够轻松应对多种分析场景，展现出强大的适应性。

![](/assets/selfAnalysis/summary.gif)
### 创建自助数据分析组件
鼠标移动至单元格的下边界，当显示悬浮操作框时，单击`更多类型`，然后选择`自助分析`。  
**操作步骤：**  
1.准备数据：创建一个DataFrame变量，存放你的数据；  
2.选择你要分析的数据源（若无，则先去创建一个DataFrame变量）；  
3.你可以通过下拉“主题类型”或“风格”选项来调整分析界面的视觉效果；  
4.点击单元格左上方的“执行”图标按钮，即可得到一个数据/可视化探索界面，如下图所示：
![](/assets/selfAnalysis/image0.png)

### 专题分析管理
#### 1. 保存专题分析
<div style="display:flex;align-items:center;">点击单元格右边的图标<img width="58" src="/assets/selfAnalysis/image-24.png"  style="margin-right:0;"/>，在弹出的对话框中输入“专题名称”,点击“提交”，即可保存该专题。</div>
![alt text](/assets/selfAnalysis/image-25.png)
在专题分析管理页面可以查看到已保存的专题，你可以点击进入查看或分析。
![alt text](/assets/selfAnalysis/image-26.png)

#### 2. 配置权限
在这里配置该专题分析的查看权限，设置谁可以看，只有勾选过的用户才可以查看。
![alt text](/assets/selfAnalysis/image-27.png)

### 开始分析
分析界面设有“数据”和“可视化”两个选项卡，默认是展示“可视化”部分，数据探索分析主要是在“可视化”界面进行。
#### 1. 数据部分
内容区域展示的是数据字段的概要情况，你可以粗略地查看数据的分布情况、缺失值或者异常值等
#### 2. 可视化部分
工具栏位于顶部
![alt text](/assets/selfAnalysis/image.png)
每个图标按钮的功能如下所述：

| 图标 | 功能名称 | 说明 |
| --- | --- | --- |
| <img height="50" src="/assets/selfAnalysis/image-1.png" /> | 撤销/重做 | 进行撤销/重做操作。 |
| <img height="50" src="/assets/selfAnalysis/image-2.png" /> | 聚合度量 | 使用“求和”、“平均值”和“计数”等方法对数据进行聚合。 |
| <img height="50" src="/assets/selfAnalysis/image-3.png" /> | 标记类型 | 在不同的图表类型之间切换，支持条形图、折线图、面积图、痕迹图、散点图、表格等，默认是‘自动’类型。 |
| <img height="50" src="/assets/selfAnalysis/image-4.png" /> | 堆叠模式  | 创建堆叠图表或规范化图表，默认是“堆叠”图表。 |
| <img height="50" src="/assets/selfAnalysis/image-5.png" /> | 转置  | 将图表中的行和列进行交换，即原先的列变为行，将原先的行变为列。 |
| <img height="50" src="/assets/selfAnalysis/image-6.png" /> | 升序/降序排序 | 按照数据的大小顺序对图表中的内容进行升序/降序排列。 |
| <img height="50" src="/assets/selfAnalysis/image-7.png" /> | 坐标系缩放 | 对坐标轴进行伸缩，以改变坐标轴的显示范围和分辨率。 |
| <img height="50" src="/assets/selfAnalysis/image-8.png" /> | 尺寸模式 | 对图表的大小进行设置的方式。它包括固定尺寸、自适应尺寸和适应容器大小三种模式。 |
| <img height="50" src="/assets/selfAnalysis/image-9.png" /> | 坐标系模式 | 默认通用坐标系，还可以设置地理模式。 |
| <img height="50" src="/assets/selfAnalysis/image-10.png" /> | 图表调试 | 默认关闭，若打开，则图表右上方会出现一个图标按钮，可以进行调试操作，如图所示：<img height="200" src="/assets/selfAnalysis/image-18.png" /> |
| <img height="50" src="/assets/selfAnalysis/image-11.png" /> | 导出 | 将图表以图片的形式导出，支持png、svg和base64三种格式。 |
| <img height="50" src="/assets/selfAnalysis/image-12.png" /> | 导出csv | 将结果数据以csv的形式导出。 |
| <img height="50" src="/assets/selfAnalysis/image-13.png" /> | 配置 | 图表配置相关的一些设置，比如图表颜色、坐标轴最大值/最小值、数据格式等,如图所示：<img width="500" src="/assets/selfAnalysis/image-19.png" /> |
| <img height="50" src="/assets/selfAnalysis/image-14.png" /> | 代码 | 可以查看该组件的代码形式，也可以将该代码插入到一个新的单元格，还支持将生成的图表上传到图表库（后面会再提及该功能）。 |
| <img height="50" src="/assets/selfAnalysis/image-16.png" /> | 设置上限 | 设置能展示的最大数据量，比如最终绘制图表的数据有100条数据，而设置了上限为50，那么图表中只会展示前50条数据。 |
| <img height="50" src="/assets/selfAnalysis/image-17.png" /> | 打开数据绘板 | 打开一个类似绘板的界面和工具，用于数据清洗、数据建模和数据探索，你可以通过画笔和橡皮来随意探索。<br />注：创建绘制字段前需要在x和y轴上分别放置一个字段来创建绘制字段，同时必须先关闭聚合。 |



在分析界面的左侧，字段列表中列出来所有的可选字段类型，这些字段都来源于数据源中的列。你可以通过简单的拖拉拽将字段拖放至你想放置的通道中（如列、行、筛选器、颜色、透明度、大小、形状和信息通道），然后就可以通过可视化的方式来分析这些数据。
![alt text](/assets/selfAnalysis/image-15.png)
对于度量，你可自由的选择合适的聚合类型（平均、求和、标准差等）
![alt text](/assets/selfAnalysis/image-20.png)
你可以通过调整不同的标记类型来展现不同的图表形式，如散点图等。
![alt text](/assets/selfAnalysis/image-21.png)
你也可以比对多个不同的度量，只需将他们都拖到行或列中来创建拼接视图，行和列都支持多个字段。
![alt text](/assets/selfAnalysis/image-22.png)
当完成自助探索，你可以选择将结果导出到文件，当下次分析时，便可快速导入之前分析的结果。
**说明：** 
开放状态包括自己访问、WorkSpace内访问和开放访问三种。  
<u>自己访问</u>：表示该图表是私密的，只能由你访问；  
<u>WorkSpace内访问</u>：是指同一个WorkSpace的成员都能访问；  
<u>开放访问</u>：是指任何人都能访问。

### 图表库管理
#### 1. 图表上传
<div style="display:flex;align-items:center;">点击工具栏中的图标按钮<img height="50" src="/assets/selfAnalysis/image-14.png"  style="margin-right:0;"/>；</div>
在弹出的对话框中，点击“上传”按钮，输入“图表名称”和选择“开放状态”，完成后点击“提交”，即可将图表上传至图表库中。
![alt text](/assets/selfAnalysis/image-23.png)

#### 2. 图表查看/修改
上传的图表可以从图表管理页面中查看，可以进入接着探索数据。
![alt text](/assets/selfAnalysis/image-28.png)
可以在这里修改图表的名称和开放状态。
![alt text](/assets/selfAnalysis/image-29.png)

<br/>
**快开始你的探索之旅吧！**  