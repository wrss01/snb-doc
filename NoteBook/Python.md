# Python代码块

Python是新增Cell代码块默认的代码类型。用户可以在Python代码块中编辑和执行任何有效的Python。

## 创建Python代码块

增加Python代码块的两种方式：

* 直接单击代码块右上角的 `+` 号
* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击`insert code cell`

![](/assets/inspython.png)

## 运行Python代码块

* 编写Python代码
* 点击Cell左上角的运行按钮 <img src="../images/%E6%89%A7%E8%A1%8C%E6%8C%89%E9%92%AE.png"  style="display: inline-block;" />开始执行代码，运行完毕后按钮右侧将显示运行时长
* 打印代码输出区域
* 折叠代码输入区域
* 行号
* 折叠打印输出区域

![图 4](../images/%E8%BF%90%E8%A1%8Cpython%E4%BB%A3%E7%A0%81.png)  

当代码存在错误，报错信息会打印在代码输出区域

![图 6](../images/%E6%8A%A5%E9%94%99%E5%8C%BA%E5%9F%9F.png)  

## 关于显示/隐式打印

Python代码块中任何显示打印的值都将显示在输出中，如：

![图 1](../images/%E6%98%BE%E7%A4%BA%E6%89%93%E5%8D%B0.png)  

隐式打印值的行只有在出现在Python代码块的最后一行时才会显示在输出中，如：

![图 2](../images/%E9%9A%90%E5%BC%8F%E6%89%93%E5%8D%B0.png)  

如果Python代码块中没有显式打印语句，并且最后一行也未显示或隐式打印任何值，此时该代码快不会将任何内容显示为输出。这类情况完全没问题，这种通常是为了保持内容的可读性，为另外的代码块提供包、函数或数据的支持。比如：

![图 4](../images/%E6%B2%A1%E6%9C%89%E6%89%93%E5%8D%B0%E7%9A%84%E6%A0%B7%E4%BE%8B.png)  

## 代码块类型转换

您可以点击代码块右上角<img src="../images/%E8%BD%AC%E6%8D%A2%E7%B1%BB%E5%9E%8B%E5%9B%BE%E6%A0%87.png"  style="display: inline-block;" />将单元格从Python 转换为 SQL或Markdown 代码块，反之亦然。

![图 5](../images/%E8%BD%AC%E6%8D%A2%E4%BB%A3%E7%A0%81%E5%9D%97%E7%B1%BB%E5%9E%8B.png)  
