# 代码块（Cell）

在Notebook中，代码块是编写、运行、分享 `代码/图表/MarkDown` 的最小单元，代码块处于运行状态，会有![](/assets/zzzz.png)标志。

![](/assets/xzms.png)



目前代码块支持的类型有：

* `Python代码`
* `SQL代码`
* `MarkDown`

![](/assets/cellfirst.png)

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

## 代码块的状态

Cell的状态为两种：**编辑状态**、**命令状态** ，两者可以相互切换。

* 编辑状态：input 输入框处于编辑状态，焦点处于代码输入框中
* 命令状态：当前Cell 处于选定状态，焦点不位于input输入框中。
* 状态切换：
  * Enter 回车：命令状态 --转化为--&gt;编辑状态
  * ESC   取消：编辑状态--转化为--&gt;命令状态

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

## 上下键切换代码块

在当前选定的单元格是命令状态时，可以上下键切换单元格（移动选定的单元格），上键往上移动选定，直到最上面一个单元为止。下键往下移动选定单元格，直到最下面的单元格为止。

# Python代码

Python是代码块默认的类型，增加Python代码块的两种方式：

* 直接单击代码块右上角的 `+` 号
* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`insert code cell`

![](/assets/inspython.png)

## SQLTemplate

通过SmartNoteBook提供的SQLTemplate语法，可以实现对SQL语句替换变量，流程控制及动态拼接。

* 变量替换：`{{VAR}}`
* 判断：  
        `{% if b >0 %}`  
        `,{{a}}`  
       `{% endif %}`

* 循环：  
       `{% for i in list_1 %}`  
       `, {{i}}`  
       `{% endfor %}`

* 字典：  
       `data ={"a":100,"b":200}`  
       `{{data.a}}`  
      `{{data.b}}`

## 示例说明

```py
Province='山东省'

df2=_smartnotebook_execute_dataframesql("""
select Province,sum(GDP2020) as gdp_sum, sum(Population2020) as popu_sum,sum(GDP2020) / sum(Population2020) as gdp_avg,
count(distinct District) as dist_count,stddev(per_gdp) as gdp_std from gdp 

where Province > "{{Province}}" 

group by Province
""",context=globals())
df2
```

```py
a=111
b=0
df_2 = _smartnotebook_execute_sql("""    select 1
{% if b >0 %}
,{{a}}
{% endif %}
""", "861437dfd11e-11ed1944-cba5b0be-93b0", context=globals())
print(df_2)
```

```py
a=111
b=0
list_1=[1,2,3,4]
df_2 = _smartnotebook_execute_sql("""    select 1
{% if b >0 %}
,{{a}}
{% endif %}

{% for i in list_1 %}
, {{i}}
{% endfor %}

""", "861437dfd11e-11ed1944-cba5b0be-93b0", context=globals())
print(df_2)
```

```
data={"a":100,"b":200}
df_2 = _smartnotebook_execute_sql("""    select 1

,{{data.a}}
,{{data.b}}

""", "861437dfd11e-11ed1944-cba5b0be-93b0", context=globals())
print(df_2)
```

## DFSQL

通过SmartNoteBook的DFSQL功能，可以实现

* SQL查询的结果可直接命名和保存为python的DataFrame数据结构
* 进行SQL查询时可直接将DataFrame数据结构作为表名使用。

## 示例说明

```py
lat =pd.read_excel('http://172.30.21.57/lat.xlsx')
lat.columns=['Province','d','d','lot','lat']
lat


import pandas as pd
gdp=pd.read_excel('http://172.30.21.57/gdpData.xlsx')
gdp['per_gdp']=gdp['GDP2020']/gdp['Population2020']
gdp




import numpy as np
df2['gdp_all_avg']=sum(df2['gdp_sum'])/sum(df2['popu_sum'])
df2['t_score']=(df2['gdp_avg']-df2['gdp_all_avg'])/(df2['gdp_std']/np.sqrt(df2['dist_count']))
df2['A']='all'
for c in ['gdp_sum','popu_sum','gdp_avg','gdp_std','gdp_all_avg','t_score']:
    df2[c]=round(df2[c],2)
df2


select Province,sum(GDP2020) as gdp_sum, sum(Population2020) as popu_sum,sum(GDP2020) / sum(Population2020) as gdp_avg,
count(distinct District) as dist_count,stddev(per_gdp) as gdp_std from gdp  group by Province


select Province,gdp_sum,popu_sum,gdp_avg,gdp_std,t_score as XL_Index,rank() over(partition by A order by gdp_sum desc) as gdp_rank ,
rank() over(partition by A order by popu_sum desc) as popu_rank ,rank() over(partition by A order by gdp_avg desc) as gdp_avg_rank ,
rank() over(partition by A order by t_score desc) as XL_Index_rank
from df2


select df3.*,lat.lat,lat.lot from df3,lat where df3.Province=lat.Province

```

# SQL代码

SmartNoteBook支持运行SQL代码块。

## 创建SQL代码块

创建SQL代码块的两种方法：

* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`SQL`。

![](/assets/sqldm.png)

* 直接单击代码块右上角的 `+` 号或者单元格下方的`Add Code Cell`，然后点击右上角的![](/assets/cvvr.png)，选择`Convert to SQL`。

![](/assets/cvtsqs.png)

## SQL代码的操作

* 选择数据源
* 结果集的名称 `结果将保存为DataFrame`
* 点击执行代码

![](/assets/sqczz.png)

# Markdown

Markdown代码块，文本编辑单元，支持 Markdown 语法，可利用它编写数据分析报告、解释算法和模型的搭建过程。

## 创建MarkDown

创建MarkDown的两种方法：

* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`MarkDown`。

![](/assets/markdown.png)

* 直接单击代码块右上角的 `+` 号或者单元格下方的`Add Code Cell`，然后点击右上角的![](/assets/cvvr.png)，选择`Convert to Markdown`。

![](/assets/cvmarkd.png)

## MarkDown的操作

Markdown 语法可参考此[Markdown基本语法](http://markdown.p2hp.com/basic-syntax/)。

MarkDown编写完成后无需执行，将鼠标移动至代码块以外即可保存和显示。

![](/assets/mrakeddown2.png)



