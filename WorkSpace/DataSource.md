# WorkSpace数据源
---
简单高效接入和管理数据源。

![图 1](../images/ds.png)  


## 支持数据源类型

![支持的数据源类型 style="width: 70%;height: 70%;"](../images/datatype.png "数据源类型")  

* `MySQL`：关系型数据库管理系统，由瑞典MySQL AB 公司开发，属于 Oracle 旗下产品。MySQL 是最流行的关系型数据库管理系统之一。
* `Spark`：通用的大数据分析引擎,具有高性能、易用和普遍性等特点。
* `Hive`：基于Hadoop的一个数据仓库工具，用来进行数据提取、转化、加载，这是一种可以存储、查询和分析存储在Hadoop中的大规模数据的机制。
* `PostgreSQL`：一种特性非常齐全的自由软件的对象-关系型数据库管理系统（ORDBMS）
* `Oracle`：甲骨文公司的一款关系数据库管理系统。它是在数据库领域一直处于领先地位的产品。
* `SQL Server`：SQL Server是由Microsoft开发和推广的关系数据库管理系统（RDBMS）。
* `Presto`：Facebook开发的数据查询引擎，可对250PB以上的数据进行快速地交互式分析。
* `ClickHouse`：俄罗斯的 Yandex 于 2016 年开源的用于在线分析处理查询（OLAP :Online Analytical Processing）MPP架构的列式存储数据库
* `Greenplum`：业界最快最高性价比的关系型分布式数据库，它在开源的PG(PostgreSql)的基础上采用MPP架构（Massive Parallel Processing,海量并行处理），具有强大的大规模数据分析任务处理能力。

> [!Tip]
> SmartNoteBook即将支持更多的数据源——如果您有需要优先支持的数据源，请联系我们。

## 建立连接

选择`WorkSpace数据源`标签页，点击右上角`新建连接服务`。

然后选择所需的数据源类型图标，填写数据源地址和认证信息后单击`测试`，返回成功信息后点击`提交`。

![图 3](../images/dsinput.png)  

## 编辑连接

在数据源列表中选择所需修改的数据源，修改配置信息后单击`测试`，返回成功信息后点击`提交`。

## 不同数据源的配置信息

用户可以在选择不同类型的数据源后，通过正确配置对应类型的数据库信息、数据库凭证后，完成创建数据库连接。

不同的数据源对应填写的配置项也会存在差异。

- 对于MySQL，PostgreSQL，SQL Server，ClickHouse和Greenplum，您需要：

  - 数据库主机网址地址（host）
  - 数据库端口（Port）
  - 数据库名称（Database）
  - 用户名和密码

- 对于Spark，Hive，Presto，ClickHouse和Greenplum，您需要：

  - 数据库主机网址地址（host）
  - 数据库端口（Port）
  - 数据库名称（Database）
  - 鉴权方式：`用户名和密码`或`无需鉴权`
  - 用户名和密码

- 对于Oracle，您需要：

  - 数据库主机网址地址（host）
  - 数据库端口（Port）
  - 实例名（SID）
  - 驱动类型（driver）：`Thin`/`OCI`/`OCIB`
  - 用户名和密码


备注：当数据库连接配置完成后，我们会为你生成一个数据标识，相当于该数据库的`云端“唯一id”`， 如 `0242ac110004-11edacf8-81c84f68-a244`。该数据标识你可在Notebook的侧边栏--数据资源复制获取，并可在代码中引用。参见<a href="../NoteBook/Sidebar.md" title="数据资源">侧边栏->数据资源</a>






