# 可视化组件
---

## Chart组件

Chart组件帮助用户以可视化交互方式浏览和处理数据，无需编写代码即可创建丰富的图表用于展示和分享。

支持的Chart组件包括以下几类：

* 标准Chart类型: 如柱状图（bar）、折线图（line）、散点图（point）、面积图（area）
* 组合图表：如Grid组合、overlap等（组合图表的功能还在研发当中）
* 其他图表：如地图、箱线图（盒须图）、词云图（WordCloud）、漏斗图等（其他图表的功能还在研发当中）

### 创建Chart

鼠标移动至代码块的下边界，当显示悬浮操作框时，单击`More cell types`，然后选择`Chart`。

![图 8](../images/createchart.png)  

### 配置Chart

1. 选择要可视化的数据变量（DataFrame）
2. 选择图表的类型及相关配置：
     - Bar：条形图/柱状图/直方图
     - Line：折线图
     - Point：散点图
     - Area：面积图
3. 设置x中和y轴的字段、聚合函数、字段类型等
4. 设置系列和排序方式
5. 点击左上角的执行按钮

<!-- ![图 4](../images/charts%E7%9A%84%E9%85%8D%E7%BD%AE.png)   -->
<!-- ![图 9](../images/chartdesc.png)   -->

![图 10](../images/orderexcetable.png)  


### 聚合数据

对行数据使用`sum`，`count`,`max`等聚合函数进行聚合：

![图 11](../images/agg.png)  

### 更改数据类型

图表中的字段支持以下数据类型：
- quantitative：数量类型
- categorical：分类类型
- ordinal：序数类型
- time：时间类型

不同的数据类型下可以设定相应的格式显示，更改数据类型将影响数据的处理和呈现方式。

![图 12](../images/datatype.gif)  


### 排序

Chart提供了多种用于对数据排序的选项：

![图 13](../images/dataorder.png)  


### 绘制多列

当需要在一张图表上绘制多列，如果数据满足不同类型的标签共享相同的度量单位，此时可以通过添加系列来实现。例如：

![图 15](../images/seris.gif)  

### 显示/隐藏图例

![图 16](../images/toolstips.png)  

### 设置图表宽度/高度


![图 17](../images/shape.png)  

### 主题设置

设置图表的主题样式：
- LIGHT：高亮主题
- DARK：暗黑主题
- WHITE：亮白主题

![图 18](../images/theme.png)  

### 隐藏/显示配置

![图 5](../images/%E9%9A%90%E8%97%8F%E9%85%8D%E7%BD%AE.gif)  

### 代码拷贝

将代码拷贝到Python单元格进一步自定义图表

![图 19](../images/codecharts.png)  

![图 7](../images/kaobeidaimapythonzhixing.png)  

### Chart开放API

Chart API 为您提供了一个以编程方式自定义显示图表的方式。

**样例** 

- 河流图themeRiver

```
from snb_plugin.snbcharts.SnbCharts import themeRiver

themeRiver(df, date, series, value, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- date：日期参数，时间序列需选择处理好的日期列
- series：按照选定的维度进行展现
- value：统计数据，选择需展现的数值
- title：图表的标题
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

![图 1](../images/themeriver.png)  

样例：

```
from snb_plugin.snbcharts.SnbCharts import themeRiver

themeRiver(temp,'day','project','count_day',height='550px', width='960px')
```

- 散点图scatterChart

```
from snb_plugin.snbcharts.SnbCharts import scatterChart

scatterChart(df, x_col, y_col, size_col, series=None, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- x_col：x轴显示列
- y_col：y轴显示列
- size_col：统计数据，选择需展现的数值
- series：按照选定的维度进行展现
- title：图表名称
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

样例：
```
from snb_plugin.snbcharts.SnbCharts import scatterChart

scatterChart(df,'hour','week_cn','count_hour',series=None, title='SmartNotebook', height='550px', width='960px')
```

![图 2](../images/scatterchart.png)  

- 散点图极坐标scatterPolarChart

```
from snb_plugin.snbcharts.SnbCharts import scatterPolarChart

scatterPolarChart(df, x_col, y_col, size_col, series=None, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- x_col：x轴显示列
- y_col：y轴显示列
- size_col：统计数据，选择需展现的数值
- series：按照选定的维度进行展现
- title：图表名称
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

![图 3](../images/polarchart.png)  

样例：

```
from snb_plugin.snbcharts.SnbCharts import scatterPolarChart

scatterPolarChart(df,'hour','week_cn','count_hour',series=None, title='SmartNotebook', height='550px', width='960px')
```
- 热力图 heatmapChart

```
from snb_plugin.snbcharts.SnbCharts import heatmapChart

heatmapChart(df, x_col, y_col, size_col, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- x_col：x轴显示列
- y_col：y轴显示列
- size_col：统计数据，选择需展现的数值
- title：图表名称
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

![图 4](../images/heatmap.png)  

样例：
```
from snb_plugin.snbcharts.SnbCharts import heatmapChart

heatmapChart(df,'hour','week_cn','count_hour', title='SmartNotebook', height='550px', width='960px')
```

- 雷达图radarChart

```
from snb_plugin.snbcharts.SnbCharts import radarChart

radarChart(df, column, series, value, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- column：显示列
- series：按照选定的维度进行展现
- value：统计数据，选择需展现的数值
- title：图表名称
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

![图 5](../images/radar.png)  

样例：
```
from snb_plugin.snbcharts.SnbCharts import radarChart

radarChart(df, "hour", "week_cn", "count_week_cn", title='SmartNotebook', height='550px', width='1600px')
```

- 盒须图boxPlot

```
from snb_plugin.snbcharts.SnbCharts import boxPlot

boxPlot(df, series, value, title='', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- series：按照选定的维度进行展现
- value：统计数据，选择需展现的数值
- title：图表名称
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`

![图 7](../images/boxplotchart.png)  

样例：
```
from snb_plugin.snbcharts.SnbCharts import boxPlot

boxPlot(df, 'Province', 'per_gdp', title='SmartNotebook', height='550px', width='980px')
```

## Snb Table组件

Snb Table组件除用作展示数据集，同时也具备一定的可视化交互能力，如对特征值进行条件筛选和排序。

### 创建

鼠标移动至代码块的下边界，当显示悬浮操作框时，单击`More cell types`，然后选择`Snb Table`。

![图 20](../images/snbtables.png)  

### Snb Table使用

* 选择数据集
* 选择字段可进行排序
* 点击字段右侧筛选按钮可进行逻辑条件筛选

![图 21](../images/snbtak.gif)  


### 通过接口自定义Snb Table

除使用Snb Table组件外，SmartNoteBook也提供了Snb Table的开放接口。用户也可通过Python调用__SNB_DisplayTable接口自定义显示Table

```
__SNB_DisplayTable(df,rownum=200,height="520px", width="100%",PageSize=10,nd=2)
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- rownum：显示行数，格式：`int`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- PageSize：单页显示数量，格式：`int`
- nd：用于控制数据集中数值类型小数点后保留几位小数，格式：`int`。默认保留两位小数

