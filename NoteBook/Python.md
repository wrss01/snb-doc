# Python单元格
---
用户可以在Python单元格中编写和执行任何有效的Python代码。

## 创建Python单元格

创建Python单元格有以下几种方式：

* 方式一：单击单元格右上角的 `+` 号
* 方式二：鼠标移动到单元格的下边界，单击悬浮框的菜单`添加单元格`

<!-- ![图 9](../images/pycell.png)   -->
![图 1](../images/f954e878763ace910f28057d809abad3be86a645a3f65db048c84389dcacca31.png)  


* 方式三：在单元格右上角的更多`...`操作里选择`在上方插入单元格`或`在下方插入单元格`，也可以创建Python单元格

 <!-- ![图 10](../images/newpycell.png)   -->
![图 2](../images/9fa5c2e89a992f479a90b3b2497cca5e9562f4d837e0ccd3fcd0fe660af2d118.png)  


* 方式四：当单元格处于命令状态下，可使用以下快捷键创建：
  *  `A`：在当前单元格前插入单元格
  *  `B`：在当前单元格后插入单元格 

## 运行Python单元格

* 编写Python代码
* 点击Cell左上角的运行按钮 <img src="../images/%E6%89%A7%E8%A1%8C%E6%8C%89%E9%92%AE.png"  style="display: inline-block;padding:0px;border:0px"  />开始执行代码，运行完毕后按钮右侧将显示运行时长
* 结果输出
* 折叠/展开输入框
* 行号（运行前为空，运行后显示行号）
* 折叠/展开结果输出

![图 4](../images/%E8%BF%90%E8%A1%8Cpython%E4%BB%A3%E7%A0%81.png)  

当代码运行报错时，报错信息会以红色底显示输出：

![图 6](../images/%E6%8A%A5%E9%94%99%E5%8C%BA%E5%9F%9F.png)  

## 关于显式/隐式打印

任何显式打印（如：print)的值都将显示在输出中，如：

![图 1](../images/%E6%98%BE%E7%A4%BA%E6%89%93%E5%8D%B0.png)  

隐式打印值的行只有在出现在单元格的最后一行时才会显示在输出中，如：

![图 2](../images/%E9%9A%90%E5%BC%8F%E6%89%93%E5%8D%B0.png)  

如果单元格中没有显式打印语句，并且最后一行也未显式或隐式打印任何值，此时该单元格不会将任何内容显示为输出。这类情况完全没有问题，这种通常是为了保持内容的可读性，为另外的单元格提供包、函数或数据的支持。比如：

![图 4](../images/%E6%B2%A1%E6%9C%89%E6%89%93%E5%8D%B0%E7%9A%84%E6%A0%B7%E4%BE%8B.png)  

## 单元格类型转换

您可以点击单元格右上角<img src="../images/%E8%BD%AC%E6%8D%A2%E7%B1%BB%E5%9E%8B%E5%9B%BE%E6%A0%87.png"  style="display: inline-block;padding:0px;border:0px"  />将单元格从Python 转换为SQL或Markdown单元格，反之亦然。

![图 5](../images/%E8%BD%AC%E6%8D%A2%E4%BB%A3%E7%A0%81%E5%9D%97%E7%B1%BB%E5%9E%8B.png)  
