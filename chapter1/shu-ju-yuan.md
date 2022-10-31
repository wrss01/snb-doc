# 数据源

SmartNoteBook为用户提供数据接入与管理功能，让用户可以简单高效的接入和管理数据集。


![](/assets/datax.png)

创建数据库连接时，我们会为你生成一个数据标识，相当于该数据库的云端“唯一id”。  
该数据标识你可在Notebook的侧边栏--数据资源复制获取，并可在代码中引用。

示例：

```py
from snb_plugin.sql.execute_sql import __smartnotebook_getengine_by_conn_id as snb_conn  
engine=snb_conn("0842ac110004-11ed4175-527b33a4-a5ab", context=globals())

# 使用 cursor() 方法创建一个游标对象 cursor
with engine.connect() as conn:
    #参考 gpu_df.to_sql('gpu_data',conn,if_exists='append')
```

