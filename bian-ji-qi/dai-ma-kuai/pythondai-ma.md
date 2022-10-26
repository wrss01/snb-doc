# Python代码

Python是代码块默认的类型，增加Python代码块的两种方式：

* 直接单击代码块右上角的 + 号
* 鼠标移动到代码块的下方，当显示悬浮操作框时，单击【insert code cell】

![](/assets/inspython.png)

## SQLTemplate

通过SmartNoteBook的SQLTemplate语法，可以实现对SQL语句替换变量，流程控制及动态拼接。

* 变量替换：`{{VAR}}`
* 判断：
        `{% if b >0 %} ` 
        `,{{a}}   `
       ` {% endif %}`

* 循环：
       `{% for i in list_1 %}` 
       `, {{i}}`
       `{% endfor %}`
* 字典：
       data ={"a":100,"b":200}
       {{data.a}}
       {{data.b}}





