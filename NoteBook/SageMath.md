# SageMath

# 介绍
---
本教程分为四个部分。这部分，关于本教程，讨论 SageMath 的一些基本属性，向您介绍 教程的结构，并解释如果您愿意，如何为项目做出贡献。

第二部分，SageMath作为计算器，涵盖了如何做算术，评估函数，创建简单图形，解决方程和做基本微积分等主题。我们将本节称为SageMath作为计算器，因为涵盖的大多数主题都是通常使用标准图形计算器完成的主题。本节的目标受众是任何有动力的微积分或微积分预科学生。

SageMath编程向读者介绍了一些更高级的主题，例如SageMath如何处理数字;如何定义和使用变量和函数;如何操作列表、字符串和集合;和SageMath宇宙和胁迫。

最后一部分，数学结构，向读者介绍在大学水平课程中找到的主题：线性代数，数论，群，环，域等。

由于本教程是对 SageMath 的介绍，我们将使用示例来演示想法，并鼓励读者跟随我们的进度，将命令输入到他们自己的 SageMath 副本中。我们包括练习练习和问题，以便更广泛地探索给定主题。还鼓励读者做其中的许多。

虽然本教程主要以线性方式进行，但我们仍然在每个部分的开头包含最重要的先决条件主题的列表。此列表遵循文本“您应该熟悉”，通过单击其中一个链接，您将被带到教程的相关部分。我们还提供了指向更多信息和其他在线参考的链接。这些将遵循“另请参阅：”文本。

某些部分可能包含编号的引文，例如“[1]”。这些引文的列表将位于至少有一个引文的部分的底部。这些引文将引导读者阅读包含有关所呈现主题的更多信息的文本。

引用：

[1]	William A. Stein et al. Sage Mathematics Software （Version 8.2）， Sage 开发团队，2018 年，http://www.sagemath.org。

# 开始
---
SageMath（以前称为Sage或SAGE）是基于Python编程语言的免费开源数学软件系统。最初是为研究 数学，它已经发展成为数学的强大工具 教育。它结合了许多其他数学软件包 使用单个界面，使用 Python。通过学习SageMath，你也学到了很多关于Python的知识。

作为一个开源项目，SageMath邀请所有用户做出贡献。本教程是学习如何使用 SageMath 的众多信息来源之一。有关更多信息，请参阅SageMath项目的网站。

本教程假定读者有权访问正在运行的 SageMath 副本。在大多数操作系统上，安装 SageMath 通常包括从项目的主网站下载正确的包，解开包装，然后从内部执行 sage。有关安装 sage 过程的更多信息，请参阅 SageMath 的安装指南。

一个不错的选择是使用Cocalc在云中运行SageMath。您需要做的就是注册一个免费帐户或通过Google/Github/Facebook/Twitter帐户登录。注册后，您可以使用SageMath启动项目，也可以与其他用户共享。有关Cocalc及其功能的更多信息，请访问Cocalc教程。

如果您选择物理安装并启动了 SageMath，您应该知道有两种方法可以输入命令：从命令行或使用基于 Web 的笔记本。笔记本界面在设计上类似于Matlab，Mathematica或Maple的界面，是一个受欢迎的选择。

提示符后面的所有内容都是我们鼓励读者自行输入的命令。例如，如果我们想分解整数，1438880我们将使用 SageMath 的命令给出以下示例。sage:factor()

sage: factor(1438880)
2^5 * 5 * 17 * 23^2
后面的行包含用户应遵循的输出 正确输入命令后预期。sage:

选项卡完成
接下来，我们将讨论如何使用各种 SageMath 接口的几个重要功能;制表符补全和内置帮助系统。

SageMath内置的最方便的功能之一是命令的选项卡完成。若要使用 Tab 完成，只需键入要使用的命令的前几个字母，然后按 Tab 键。例如，假设您要计算66乙，但不记得执行此操作的确切命令名称。一个很好的猜测是，该命令的名称中将有阶乘。要查看该猜测是否正确，只需键入前三个字母并按 tab 键即可。fac

sage: fac[TAB]
factor     factorial
sage: factor
输出告诉您只有两个 SageMath 命令以 和 开头。请注意，SageMath 已经将命令从 更改为 ，因为这是两个命令的公共根。由于阶乘看起来像正确的命令，我们将通过键入下一个字母来选择它，然后再次按 Tab 键。facfactor()factorial()facfactori

sage: factorial
这次不返回任何列表，因为唯一以 开头的命令是 。因此，要计算66乙，您只需通过添加参数来完成命令。factorifactorial()(56)

sage: factorial(56)
710998587804863451854045647463724949736497978881168458687447040000000000000
制表符补全的另一个很好的用途是发现对象具有哪些方法。假设您有整数a = 56，并且想知道 SageMath 提供了哪些命令来处理整数，例如 56.在这种情况下，一个这是我们的对象，我们可以通过键入然后按 tab 键来找到与整数相关的所有方法。a.

sage: a = 56
sage: a.[TAB]
a.N                            a.kronecker
... A long list of Commands ...
a.divisors                     a.parent
a.dump                         a.popcount
a.dumps                        a.powermod
a.exact_log                    a.powermodm_ui
--More--
不要被这个列表的长度吓倒。SageMath是一个非常强大的系统，它可以用整数做很多事情。在命令行上，屏幕底部的 告诉您可能的命令列表比单个屏幕适合的列表要长。要一次滚动浏览此列表一页，请点击任意键，SageMath 将显示下一页。--More--

在第二页上，您会看到这是一个选项。要使用此方法（该方法将因子56分解为唯一素因数），请输入 。factor()a.factor()

sage: a.factor()
2^3 * 7
制表符补全不仅可以减少所需的键入量，还可以用于在 SageMath 中发现新命令。

帮助使用 ？
确定感兴趣的命令后，下一步就是准确了解该命令的作用以及如何使用它。SageMath有一个内置的帮助系统来帮助您实现这一目标。

假设您希望计算 两个整数，不确定哪个命令执行此操作。一个好地方 开始搜索是在命令提示符下键入，然后 按制表键。l

sage: l[TAB]
laguerre                    list_plot3d
lambda                      lk
laplace                     ll
latex                       ln
lattice_polytope            lngamma
lazy_attribute              load
lazy_import                 load_attach_path
lc                          load_session
lcalc                       loads
lcm                         local/LIB
ldir                        local/bin
...
lisp_console                ls
list                        lucas_number1
list_composition            lucas_number2
list_plot                   lx
再一次，您有很长的命令列表可供选择。向下扫描列表，您会看到列出的命令，该命令似乎是您尝试计算的命令。要确保这一点，请输入 。lcm()lcm?

sage: lcm?
此命令的输出是一个页面，其中解释了命令的用法和用途。

Base Class:     <type 'function'>
String Form:    <function lcm at 0x32db6e0>
Namespace:      Interactive
File:           /home/ayeq/sage/local/lib/python2.6/site-packages/sage/rings/arith.py
Definition:     lcm(a, b=None)
Docstring:
       The least common multiple of a and b, or if a is a list and b is
       omitted the least common multiple of all elements of a.

       Note that LCM is an alias for lcm.

       INPUT:

       * ``a,b`` - two elements of a ring with lcm or

       * ``a`` - a list or tuple of elements of a ring with lcm

       EXAMPLES:

          sage: lcm(97,100)
          9700
          sage: LCM(97,100)
同样，会有很多信息，通常比一个屏幕所能容纳的信息更多。在命令行上，导航很容易;空格键将带您进入下一页，并且 或向上箭头键将在文档中向后移动。要退出帮助系统，请按键。bq

刚开始时;说明、和部分是值得阅读的好部分。该说明提供了描述命令用途的简短摘要，提供了有关应作为命令参数提供的内容的信息，并提供了命令用法的具体示例。INPUTEXAMPLESINPUTEXAMPLES

本例中的描述为：

The least common multiple of a and b, or if a is a list and b is
omitted the least common multiple of all elements of a.
Note that LCM is an alias for lcm.
从此描述中，您可以非常确定这是您要查找的命令。接下来检查：INPUT

INPUT:
* ``a,b`` - two elements of a ring with lcm or
* ``a`` - a list or tuple of elements of a ring with lcm
在这里你可以看到可以接受两个参数，对于我们的目的，可以接受两个整数，或者一个对象列表。最后，通过仔细阅读，您可以很好地了解此命令在实践中的实际使用方式。lcmEXAMPLES

EXAMPLES:

   sage: lcm(97,100)
   9700
   sage: LCM(97,100)
   9700
   sage: LCM(0,2)
   0
   sage: LCM(-3,-5)
   15
   sage: LCM([1,2,3,4,5])
   60
   sage: v = LCM(range(1,10000))   # *very* fast!
   sage: len(str(v))
   4349
在 SageMath 中内置全面的帮助系统是其最佳功能之一，您越早熟悉使用它，您就能更快地使用此 CAS 的全部功能。

源代码，？？
本教程可能有一些读者喜欢编程，想看看如何在 SageMath 中构建命令。为此，您只需键入您感兴趣的源代码的命令，然后按 <tab> 键。例如，回到我们的命令factor()

sage: factor??
Source Code (starting at line 2139):

def factor(n, proof=None, int_=False, algorithm='pari', verbose=0, **kwds):
"""comments inserted here"""
        try:
                m = n.factor
        except AttributeError:
                """Maybe n is not a Sage element, try to convert it
                e = py_scalar_to_element(n)
if e is n:
    # Either n was a Sage Element without a factor() method
    # or we cannot it convert it to Sage
    raise TypeError("unable to factor {!r}".format(n))
n = e
m = n.factor

        """code continues"""
此命令的输出很长，不适合单个页面或快照（自己尝试）。但是，我们报告了一些代码行，以向您展示语法如何是 Pythonic。运行该命令后，您将在代码中看到大量注释（由三引号“”标记），如果您不熟悉它，这些注释将引导您如何阅读它，它的作用以及解释Python语法。