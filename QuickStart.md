# 快速上手使用
---

使用本指南快速了解SmartNotebook的基础知识。

## 概述

SmartNotebook 是一个协作式数据科学/分析平台，可简化数据洞察和交付，帮助数据科学和业务团队共同提高工作效率。您可以使用 SmartNotebook 进行数据采集和探索、机器学习、可视化和（定期）生成报告。

SmartNotebook汇集了：

- Python、SQL、R、SageMath 和 Julia 的强大编码和运行环境支持

- SQL 数据库和数据仓库的集成支持和管理

- 现代商业智能和交互式的数据开发和应用

- 团队成员在工作空间中的实时协作


## 第一步

通过创建和编辑您的第一个Notebook开始学习数据知识。

**在workspace下创建新的Notebook**
  
1. 在workspace下，单击左下方的“新建Notebook”，您将重定向到“新建NoteBook”页面。

![图 1](/images/newnotebook.png)  

2. 输入notebook的标题，并选择相应的环境，然后点击提交。

![图 2](/images/%E8%AE%BE%E7%BD%AE%E6%A0%87%E9%A2%98.png)  

3. 创建Notebook完成，进入到Notebook的编辑页面。

目前，您的Notebook仅包含一个代码单元格。默认情况下，它会显示一段python语言的欢迎代码。

![图 3](/images/welcomecode.png)  


**编辑笔记本**

1. 在第一个代码单元格中，输入以下代码。

```
# 获取当前时间
import datetime

now = datetime.datetime.now()
print('现在几点钟了？')
print('当前时间：',now)
```

2. <p>点击左上角的运行按钮 <img src="images/run.png"  style="display: inline-block;" /> 或使用键盘快捷键 Shift+Enter 来运行代码块。</p>

3. 通过将鼠标悬停在单元格下边框的中间，选择`More cell types`并单击Markdown来添加 Markdown单元格。

![图 5](/images/morecelltype.png)  

4. 在Markdown单元格中输入文本。

5. 如果要运行整个Notebook代码，请选择主菜单栏的运行从主菜单运行所有内容。


## 使用您的数据

按照以下步骤附加.csv文件并对其数据执行基本分析。

1. 下载鸢尾花数据集Iris.csv，此数据集据集包含150个数据样本，分为3类，每类50个数据，每个数据包含Id列、花的4个属性以及花的分类。

2. 点击workspace主页右上角的的上传文件按钮，将下载的数据集上传至云端。

3. <p>进入Notebook，单击左侧边栏上的数据资源图标 <img src="images/attachment.png"  style="display: inline-block;" /> ，在workspace文件下可以看到上传的Iris.csv，点击右上角“文件一键同步到Node”，此时页面上方提示文件同步成功。</p>

4. 使用 pandas（一种流行的 Python 库）查看数据。

在任意python单元格中粘贴以下代码：

```
import pandas as pd

iris_data = pd.read_csv('/home/Iris.csv')
iris_data
```

运行代码单元后，输出区域将显示如下表：

![图 8](/images/iristable.png)  

**可视化数据集**

新建一个python单元格，贴入以下代码：

```
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline

plt.figure()
sns.pairplot(iris_data.drop("Id", axis=1), hue = "Species", height=3, markers=["o", "s", "D"])
plt.show()
```
运行代码块后，会显示如下所示的图表：

![图 9](/images/snspic.png)  

## 分享您的分析报告

1. 单击Notebook右上角的分享图标。

2. 复制分享链接发送分析报告。

3. <p>（可选）如果需要单独分享某个单元格输出，只需点击该单元格右侧的分享 <img src="images/sharebutton.png"  style="display: inline-block;" /> 按钮。</p>

