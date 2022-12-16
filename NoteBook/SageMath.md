# SageMath支持

SageMath 是一个免费的、开源的数学软件系统，采用GPL协议。它整合了许多开源Python包，采用Python语言编写，但也支持其他语言。它的目标是创造一个可变的开源软件以替代Matlab、Magma、Maple 和 Mathematica。

为使大家方便的了解、学习并使用SageMath，我们的SmartNotebook通过引入SageMath引擎并细致地对兼容性做了优化和完善，充分利用Notebook的特性，不仅减少大量复杂的安装和配置，而且做到可以让用户即开即用。

当我们创建NoteBook时，对于要在NoteBook中使用的语言及环境，目前有三个类型选项：
- Python
- R
- SageMath

关于Python类型的NoteBook详见<a href="./Cell.md" title="代码块（Cell）">代码块（Cell）-> Python代码</a>

关于R类型的NoteBoo详见<a href="./R.md" title="R">R语言支持</a>

这里我们介绍一下SmartNoteBook对SageMath的支持。

## 创建SageMath环境支持

我们用SmartNotebook 快速创建一个Sagemath内核的Notebook。像下面这样，输入Notebook的标题，选择Sagemath的内核，点击提交即可。

![picture 1](../images/sagemath_kernel.png)  


接下来我们进入Notebook后直接创建Code Cell 单元格，便可以编写并执行Sage代码了。



比如：当我们对整数`20221208` 进行素数因子分解 ，新建一个Code Cell 单元格 ，输入以下代码并点击执行：

```factor(20221208)```

执行结果：

![picture 2](../images/factor%E5%87%BD%E6%95%B0.png)  


## SageMath的帮助系统

- Help帮助：使用 “？”

当我们需要准确了解某个函数或命令的作用以及如何使用它，我们可以使用 “？”来调用内置的帮助系统。例如：

```lcm?```

- 查看源代码：使用“??”

有些喜欢研究源码的同学想看看 SageMath 中某个命令的源码，您只需键入您感兴趣的命令，然后键入“??”。

例如，查看factor()的源代码：

```factor??```

![图 3](../images/%E6%9F%A5%E7%9C%8B%E6%BA%90%E4%BB%A3%E7%A0%81.png)  




## SageMath as a Calculator

这里我们介绍介绍一下如何像图形计算器一样使用 SageMath 的一些算术和函数命令。

基本算术

基础的算术运算符为加 + 、减 -、乘 * 、除 / 、指数 ^
数字前面的符号-表示它是负数。

```
print('1+1=',1+1)
print('103-101=',103-101)
print('7*9=',7*9)
print('7337/11=',7337/11)
print('11/4=',11/4)
print('2^5=',2^5)
print('-11+9=',-11+9)
-6
```

SageMath 遵守标准的操作顺序， 即PEMDAS (parenthesis, exponents, multiplication, division, addition, subtraction): 括号、指数、乘法、除法、加法、 减法。

```
print(2*4^2+1)
print((2*4)^2+1)
print(2*4^(2+1))
print(-3^2)
print((-3)^2)
```


当两个整数相除时，有一个微妙之处：SageMath将返回分数或其十进制近似值。与大多数图形计算器不同，SageMath将尝试尽可能精确，除非另有说明，否则将返回分数。

```
print(11/4)
print(11/4.0)
print(11/4.)
print(11.0/4)
print(11/4*1.)
```

整数除法和因式分解

有时当我们使用除法时，除法运算符不会给我们所有想要的信息。比如，我们不仅想知道约化分数是多少，甚至想知道它的十进制近似值，或者想知道唯一商和余数是多少。我们可以使用运算符// 来计算商，使用运算符 % 用于余数。使用 divmod(）函数来同时计算获得商和余数。

```
print( 14 // 4)
print( 14 % 4)
print( divmod(14,4))
```

我们知道当两个整数是否能整除，可以采用A/B余数是0，说明可以整除，但SageMath 整数有一个内置的方法可以专门用来检查一个整数是否整除另一个整数。

```
print(3.divides(15))
print(5.divides(17))
```

与divides方法相关的还有一个方法divisors()，此方法可以返回指定整数的所有正除数的列表。

```
print(12.divisors())
101.divisors()
```

我们知道当整数的除数只是1和它本身时，这个数字是素数。为了检查一个数字在SageMath中是否是素数，我们可使用方法is_prime()

```
print(153.is_prime())
(2^19-1).is_prime()
```

factor()可计算整数的素因数分解

```
print(62.factor())
63.factor()
```

有兴趣简单地知道哪些素数除以整数，我们可以使用prime_divisors() 或 prime_factors()方法。

```
print(24.prime_divisors())
print(24.prime_factors())
print(63.prime_factors())
print(63.prime_divisors())
```

求最大公约数和最小公倍数。

最大公约数（GCD）是所有这些公约数中最大的一个。

最小公倍数（LCM）是两个整数相除的最小整数。

```
print( gcd(14,63))
print( gcd(15,19))
print(lcm(4,5))
lcm(14,21)
```

标准函数和常量

SageMath几乎包含了人们在学习数学时遇到的所有标准函数。接下来我们将介绍一些最常用的函数：maximum、minimum、 floor、ceiling、trigonometric、exponential、logarithm 函数。我们还将看到许多标准的数学常数，如欧拉常数(e）、π 和黄金比例（ ϕ ）。

```
# max 最大值
print(max(1,5,8))
# min 最小值
print(min(1/2,1/3))
# abs 绝对值
print(abs(-10))
# floor 向下取整 
print(floor(2.1))
# ceil 向上取整
print(ceil(2.1))
```

当使用floor、ceil 时要特别小心，注意计算精度问题

```
 print(floor(1/(2.1-2)))
 print(1/(2.1-2))
```


sqrt()该命令/函数计算实数的平方根。正如我们之前在分数中看到的那样，如果我们想要十进制近似值，我们可以通过给出一个十进制数作为输入来获得它。

```
print(sqrt(3))
print( sqrt(3.0))
```

为了计算其他根，我们使用有理指数。SageMath可以计算任何有理数指数幂(SageMath can compute any rational power)。如果指数或基数是小数，则输出将是小数。

```
print( 3^(1/2) )
print( (3.0)^(1/2) )
print( 8^(1/2) )
print( 8^(1/3) )
```

SageMath 还支持所有标准三角函数，例如：正弦sin()和余弦 cos()

```
print( sin(1) )
print( sin(1.0) )
print( cos(3/2) )
print( cos(3/2.0) )
```

在SageMath内，我们完全处理的是π，而不是一些数字近似。但是，我们可以使用以下方法调用数值近似：pi.n()

```
print(pi.n())
print(sin(pi))
print(sin(pi.n()))
```


我们看到，当使用符号时，SageMath 返回确切的结果。但是，当我们使用近似值时，我们会得到一个近似值。是 的10^{-16}简写，数字应为零，但近似值引入了错误。以下是使用符号、精确 π 与数值近似的几个示例:

```
print( sin(pi/6))
print( sin(pi.n()/6))
print( sin(pi/4))
print(sin(pi.n()/4))
```

继续我们的主题，有一些鲜为人知的特殊角度，可以巧妙地简化正弦或余弦的值。

```
print( sin(pi/10)) 
print( cos(pi/5) )
print( sin(5*pi/12) )
```

其他三角函数、反三角函数和双曲函数也可用

```
print( arctan(1.0) )
print( sinh(9.0))
```

SageMath内与 π 类似，它有一个内置的数字符号常数e，即自然对数的底数。

```
print(e)
print(e.n())
```

我们使用命令:ln(x)、log(x)、log(x,b)，幂基e可以使用函数和通过将符号常数提高到指定幂来完成。

```
print(  ln(e) )
print(  log(e) )
print(  log(e^2) )
print(  log(10) )
print(  log(10.0) )
print(  log(100,10) )
print(  exp(2) )
print(  exp(2.0) )
print(  exp(log(pi)) )
print(  e^(log(2)) )
```

## 更多

想了解更多SageMath的知识和例子，可以参考[SDSU Sage Tutorial](https://mosullivan.sdsu.edu/Teaching/sdsu-sage-tutorial) 