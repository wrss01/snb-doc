# Python代码

Python是代码块默认的类型，增加Python代码块的两种方式：

* 直接单击代码块右上角的 + 号
* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击【insert code cell】

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



