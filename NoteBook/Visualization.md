# 可视化组件

目前SmartNoteBook提供的可视化组件有：

* `Chart`
* `Snb Table`

# Chart

SmartNoteBook具备低代码实现可视化，目前支持的Chart类型包括

* 标准charts: bar、line、point\(Scatter\)、area、pei
* 组合图：Grid 组合、overlap `建设中`
* 地图、箱线图（盒须图）、WordCloud、漏斗图`建设中`

## 创建Chart

鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`MarkDown`。

![](/assets/xjcharts.png)

## 配置Chart

1. `Chart`配置区域
2. `Chart`显示区域
3. `Chart`类型显示
4. 执行`Chart`
5. `Chart` 主题和图例等配置

![](/assets/charsgs.png)

## Chart API（Low code）

除使用Chart组件外，SmartNoteBook也提供了Chart的开放接口Chart API。用户也可通过Python调用Chart API自定义显示图表。

### 河流图themeRiver

```
from snb_plugin.snbcharts.SnbCharts import themeRiver
themeRiver(df,'day','project','count_day',height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- 'day','project','count_day'：控制统计维度

![图 1](../images/themeriver.png)  

### 散点图scatterChart

```
from snb_plugin.snbcharts.SnbCharts import scatterChart

scatterChart(df,'hour','week_cn','count_hour',series=None, title='SmartNotebook', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- 'hour','week_cn','count_hour',series=None：控制统计维度
- title：图表名称

![图 2](../images/scatterchart.png)  

### 散点图极坐标scatterPolarChart

```
from snb_plugin.snbcharts.SnbCharts import scatterPolarChart

scatterPolarChart(df,'hour','week_cn','count_hour',series=None, title='SmartNotebook', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- 'hour','week_cn','count_hour',series=None：控制统计维度
- title：图表名称

![图 3](../images/polarchart.png)  


### 热力图 heatmapChart

```
from snb_plugin.snbcharts.SnbCharts import heatmapChart

heatmapChart(df,'hour','week_cn','count_hour', title='SmartNotebook', height='550px', width='960px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- 'hour','week_cn','count_hour',：控制统计维度
- title：图表名称

![图 4](../images/heatmap.png)  

### 雷达图radarChart

```
from snb_plugin.snbcharts.SnbCharts import radarChart
radarChart(df, "hour", "week_cn", "count_week_cn", title='SmartNotebook', height='550px', width='1600px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- "hour", "week_cn", "count_week_cn",：控制统计维度
- title：图表名称

![图 5](../images/radar.png)  

### 盒须图boxPlot

```
from snb_plugin.snbcharts.SnbCharts import boxPlot
boxPlot(df, 'Province', 'per_gdp', title='SmartNotebook', height='550px', width='980px')
```
接口说明：
- df：数据集，格式：`pandas.DataFrame`
- height：高度，格式：`px` 或`百分比`
- width：宽度，格式：`px`或`百分比`
- 'Province', 'per_gdp',：控制统计维度
- title：图表名称

![图 7](../images/boxplotchart.png)  


# Snb Table

Snb用于对展示数据集，并具备一定的交互能力，如对特征值进行条件筛选和排序。

## 创建Snb Table

鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`Snb Table`。

![](/assets/snttable.png)

## 配置和展示

* 下拉框选择数据集。
* 选择字段可进行排序和条件筛选。

![](/assets/snbtablesss.png)

## 自定义Snb Table

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

