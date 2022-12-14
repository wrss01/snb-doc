# 密保箱

通过将敏感值（如API令牌或重要密码）添加到密保箱来确保关键信息的机密性。后面我们可以在Python单元格中通过调用名称来访问该机密信息，而不是通过明文或者硬编码的方式进行调用。

如您需要在NoteBook中使用环境变量，也可以通过密保箱的功能进行配置，减少代码中硬编码的情况。

![图 3](../images/%E6%96%B0%E5%BB%BA%E5%AF%86%E4%BF%9D.png)  

## 新建密保/环境变量

点击右上角的`新建密保`,输入`名称（英文）`和`值`后提交。

![图 2](../images/mibashezhi.png)  

## 密保/环境变量列表

在密保列表我们可以重新`编辑密保`和`删除密保`。

![图 4](../images/%E5%AF%86%E4%BF%9D%E7%AE%B1%E5%88%97%E8%A1%A8.png)  

## 密保的使用

<p>通过单击密保名称前面的<img src="../images/%E5%A4%8D%E5%88%B6icon.png"  style="display: inline-block;" />可以复制密保的使用代码，并在NoteBook中插入代码进行调用。</p>

![图 5](../images/%E5%A4%8D%E5%88%B6%E5%AF%86%E4%BF%9D.png)  

在python代码中引用：

![picture 1](../images/%E5%BC%95%E7%94%A8%E5%AF%86%E4%BF%9D.png)  

## 环境变量的例子

新建一个db_url环境变量

![picture 2](../images/%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F.png)  

代码中引用db_url环境变量

```
DB_URL = snbGetValue("db_url")
DB_NAME = snbGetValue("db_name")
```