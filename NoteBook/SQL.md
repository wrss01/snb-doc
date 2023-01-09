# SQL代码块
---
SmartNoteBook通过SQL代码块提供一流的SQL支持，每个SQL代码块都是一个完全成熟的查询IDE，具有自动补全、数据预览等功能。项目可以有无限数量的SQL代码块与MarkDown文本、代码、图表和各类可视化组件交错，从而创建非常灵活的查询环境。

## SQL代码块的特性/要点

在SmartNoteBook中使用SQL代码块会使数据查询变的非常便捷高效，区别于您之前所使用的SQL查询工具，使用SmartNoteBook编写SQL，有以下几个特性/要点需要您了解：

- SmartNoteBook中有两种类型的SQL查询：既可以通过连接远程数据库或数据仓库来运行SQL查询（DBSQL），也可以直接使用SQL查询DataFrame或.csv数据格式文件（DFSQL）。SmartNoteBook将两种方式融合，帮助您执行一些非常强大的工作流程。
  
- SQL查询数据库返回的结果可以作为DataFrame返回：默认情况下，SQL查询将整个结果集作为可在内存中操作的DataFrame类型返回。

- SQL查询可以“串联”在一起：后面执行的SQL查询可以引用NoteBook中之前已执行的SQL查询结果，就像我们写复杂SQL中包含许多CTE（公共表表达式） 一样。您可以使用这种方式将复杂SQL按照逻辑进行拆分，使整个查询过程更具可读性。

- SQL查询可以嵌入变量参数及流程控制参数：您可使用[Jinja2](http://docs.jinkan.org/docs/jinja2/templates.html)语法将NoteBook中其他代码部分定义或运行的值插入到当前的SQL查询中。这种机制可以帮助您自定义用户输入、将之前已运行的SQL或Python代码块输出作为查询条件进行参数化查询,并在SQL代码中加入流程控制（if...else.../for循环等等），从而构建由SQL提供的支持面向用户的复杂数据应用程序。


## 何时使用DBSQL或DFSQL？

如果查询数据库或数据仓库，则必须使用DBSQL。如果查询DataFrame的数据或.csv文件，则需使用DFSQL。

您可以通过组合DBSQL和DFSQL，以更流畅的方式构建复杂的数据处理流程，比如：

- 当你需要用Python对数据做一个中间处理：假设你刚运行完一个DBSQL查询，然后需要使用Python对某一列进行地理编码处理。这时你可以利用DFSQL对DataFrame进行SQL操作，此时数据其实已不在数据库表中。
  
- 如果需要从.csv文件查询数据。DFSQL可以直接对上传的文件运行查询，您只需`SELECT * FROM "文件名.csv"`

例如：

```
select * from '/home/Iris.csv'
```
或
```
select Id, SepalLengthCm, SepalWidthCm, PetalLengthCm, PetalWidthCm,Species from '/home/Iris.csv'
```

- 如果需要跨不同数据源连接数据。您可以运行两个DBSQL查询，一个针对MySQL连接，另一个针对Oracle连接，然后使用DFSQL查询将两个DataFrame进行连接。

> [!NOTE]
> DFSQL需要在内存中加载数据集，因此如果数据量非常大的情况下不建议使用。

## 创建SQL代码块

创建SQL代码块的两种方法：

* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`More cell types`，然后选择`SQL`。

![图 7](../images/new%20sql%20%E5%9B%BE.png)  


* 直接单击代码块右上角的 `+` 号或者单元格下方的`Add Code Cell`，然后点击右上角的<img src="../assets/cvvr.png"  style="display: inline-block;" />，选择`Convert to SQL`。

![](/assets/cvtsqs.png)

## 使用DBSQL（查询远程数据库/数据仓库)

* 创建SQL代码块
* 数据源下拉框选择已有数据源（连接数据源操作详见<a href="../WorkSpace/DataSource.md" title="数据源">数据源</a>）
* 填写结果集的名称，如`df2` （输出类型为DataFrame）
* 点击执行代码

经以上步骤我们就运行完一个DBSQL查询，并且将结果保存在了名称为df2的DataFrame中。

![图 7](../images/dbsql%E7%9A%84%E6%A0%B7%E4%BE%8B.png)  


## 使用DFSQL（用SQL操作DataFrame）

* 创建SQL代码块
* 数据源下拉框选择`dfSQL`
* 输入SQL代码，表名填写DataFrame的名称，比如查询我们上面保存过的`df2`
* 填写结果集的名称，如`df3`（输出类型为DataFrame）
* 点击执行代码

经以上步骤我们就运行完一个dfSQL查询，使用SQL和Pandas DataFrame融合的方式完成了数据处理，并且将结果保存在名称为df3的DataFrame中。

![图 8](../images/dfsql%E7%9A%84%E6%A0%B7%E4%BE%8B.png)  

> [!Tip]
> 关于DFSQL可以支持的一些特性和操作可参考[SQLite3 Documentation](https://www.sqlite.org/docs.html)。

## 示例

以下通过一个简单示例展示如何使用dfSQL将SQL和Python融合方便快捷的进行数据处理：

- 通过Python代码块导入经纬度信息：

```{% raw %}
lat =pd.read_excel('http://172.30.21.57/lat.xlsx')
lat.columns=['Province','d','d','lot','lat']
lat
{% endraw %}
```

- 通过Python代码块导入全国的gdp数据：

```{% raw %}
import pandas as pd
gdp=pd.read_excel('http://172.30.21.57/gdpData.xlsx')
gdp['per_gdp']=gdp['GDP2020']/gdp['Population2020']
gdp
{% endraw %}
```


- 通过Python代码块对列进行计算和精度处理，将结果保存在`df2 `中（数据类型为DataFrame）
  
```{% raw %}
import numpy as np
df2['gdp_all_avg']=sum(df2['gdp_sum'])/sum(df2['popu_sum'])
df2['t_score']=(df2['gdp_avg']-df2['gdp_all_avg'])/(df2['gdp_std']/np.sqrt(df2['dist_count']))
df2['A']='all'
for c in ['gdp_sum','popu_sum','gdp_avg','gdp_std','gdp_all_avg','t_score']:
    df2[c]=round(df2[c],2)
df2
{% endraw %}
```

- 使用`DF_SQL`，可将上面的DataFrame类型的数据集直接当做表进行SQL查询处理：

```{% raw %}
select Province,sum(GDP2020) as gdp_sum, sum(Population2020) as popu_sum,sum(GDP2020) / sum(Population2020) as gdp_avg,
count(distinct District) as dist_count,stddev(per_gdp) as gdp_std from gdp  group by Province
{% endraw %}
```

- 使用`DF_SQL`，采用SQL计算排名：
  
```{% raw %}
select Province,gdp_sum,popu_sum,gdp_avg,gdp_std,t_score as XL_Index,rank() over(partition by A order by gdp_sum desc) as gdp_rank ,
rank() over(partition by A order by popu_sum desc) as popu_rank ,rank() over(partition by A order by gdp_avg desc) as gdp_avg_rank ,
rank() over(partition by A order by t_score desc) as XL_Index_rank
from df2
{% endraw %}
```

- 使用`DF_SQL`，对表进行关联：

```{% raw %}
select df3.*,lat.lat,lat.lot from df3,lat where df3.Province=lat.Province
{% endraw %}
```

## SQL参数化（使用SQLTemplate）

可以让您在SQL中使用输入参数或Python变量来进行参数化查询！

我们使用SmartNoteBook提供的SQLTemplate语法，可以实现对SQL语句替换变量，流程控制及动态拼接。以下几个小样例会告诉您如何应用SQLTemplate进行变量替换和流程控制。另外，关于SQLTemplate的详细语法可参考[Jinja2 模板](http://docs.jinkan.org/docs/jinja2/templates.html)。

* 变量替换：
  * 一般变量

  ``` {% raw %}
  {{VAR}}
  {% endraw %}
  ```

  * 字典变量：
 
  ```{% raw %}
  data ={"a":100,"b":200}  
  {{data.a}} 
  {{data.b}}
  {% endraw %}
  ```

* 判断：  
  ```{% raw %}
  {% if b >0 %}
    ,{{a}}  
  {% endif %}
  {% endraw %}
  ```

* 循环：
  ```{% raw %}
  {% for i in list_1 %}  
  , {{i}}
  {% endfor %}
  {% endraw %}
  ```

### 示例

比如，您可以在Python代码块中先定义两个变量：

```{% raw %}
start_time = '2022-07-01T00:00:00Z'
end_time = '2022-11-01T00:00:00Z'
{% endraw %}
```
然后在SQL代码块中我们便可以引用以上变量过滤数据

```{% raw %}
select count(*)  from df where dt > '{{start_time}}' and dt < '{{end_time}}'
{% endraw %}
```

![图 2](../images/sqltema.png)  


还可以用if..else判断做流程控制


```{% raw %}
{% if yes_count>0 %}
	delete from tb_snb_code_data where dt > '{{yesterday_str}}' and dt < '{{today_str}}';
{% else %}
    select '昨天的记录不存在';
{% endif %}
{% endraw %}
```


![图 3](../images/SQLtemp%E4%BE%8B%E5%AD%90B.png)  


再来个简单的使用for循环的例子：

先用Python代码定义一个list：


```
columns = ['Province', 'District', 'GDP2020']
```


然后新建SQL代码块，数据源设置为dfSQL，键入以下SQL代码：


```{% raw %}
select 2022
  {% for col in columns %}
  , {{col}}
  {% endfor %} 
  from gdp_data
{% endraw %}
```

![图 4](../images/templatefor%E5%BE%AA%E7%8E%AF.png)  

使用字典的小例子：

Python代码块

```
data={"a":100,"b":200}
```


dfSQL代码

```{% raw %}
 select 
 {{data.a}}
,{{data.b}}
{% endraw %}
```


![图 6](../images/%E4%BD%BF%E7%94%A8%E5%AD%97%E5%85%B8%E4%BE%8B%E5%AD%90.png)  


## SQL注释

注释用于解释SQL语​​句的各个部分，或用于防止执行SQL语句。

在SmartNoteBook中，SQL注释用`##` 双井号开始，末尾用分号`;`结束：

![图 9](../images/SQL%E6%B3%A8%E9%87%8A.png)  
