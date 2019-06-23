## Amazon Relational Database Service (Amazon RDS)

- **简介**

  [Amazon Relational Database Service (Amazon RDS)](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html) 是一种 Web 服务，可让用户更轻松地在云中设置、操作和扩展关系数据库。它可以经济有效的为用户提供一个容量可调的行业标准的关系数据库，并承担常见的数据库管理任务。

  Amazon RDS 会接管关系数据库的很多困难或繁琐的管理任务：

   - 购买服务器时，您会一并获得 CPU、内存、存储和 IOPS。利用 Amazon RDS，您可以将这些部分进行拆分，以便单独对其进行扩展。如果您需要更多 CPU、更少 IOPS 或更多存储，可以轻松地对它们进行分配。

   - Amazon RDS 可以管理备份、软件修补、自动故障检测和恢复。

   - 为了产生托管服务体验，Amazon RDS 不允许通过 shell 访问数据库实例，而仅限访问某些需要高级特权的系统过程和表。

   - 您可以在需要时执行自动备份，也可以手动创建您自己的备份快照。您可以使用这些备份还原数据库。Amazon RDS 还原过程将可靠且高效地工作。

   - 您可以通过主实例和在发生问题时可向其执行故障转移操作的同步辅助实例实现高可用性。您还可以使用 MySQL、MariaDB 或 PostgreSQL 只读副本扩展读取。

   - 您可以使用您已熟悉的数据库产品：MySQL、MariaDB、PostgreSQL、Oracle 和 Microsoft SQL Server。

   - 除了保证数据库包的安全外，还可以使用 AWS Identity and Access Management (IAM) 定义用户和权限来帮助控制可以访问 RDS 数据库的人员。您还可以将数据库置于虚拟私有云中，这样有助于保护数据库。

     

- **Amazon Aurora**

  [Amazon Aurora (Aurora)](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html) 是一个与 MySQL 和 PostgreSQL 兼容的完全托管的关系数据库引擎。您已了解了 MySQL 和 PostgreSQL 不仅具有高端商用数据库的速度和可靠性，同时还具有开源数据库的简单性和成本效益。您目前用于现有 MySQL 和 PostgreSQL 数据库的代码、工具和应用程序可用于 Aurora。在某些工作负载条件下，Aurora 最多可以将 MySQL 吞吐量增加 5 倍，将 PostgreSQL 的吞吐量增加 3 倍，而无需对大多数现有应用程序进行更改。

  Aurora 包括一个高性能的存储子系统。已自定义其 MySQL 和 PostgreSQL 兼容数据库引擎以利用该快速分布式存储。基础存储根据需要自动增长，最高为 64 TB。Aurora 还会自动化和标准化数据库集群和复制，这通常是数据库配置和管理方面的最大问题。

  

- **数据库实例**

  Amazon RDS 的基本构建基块是*数据库实例*。数据库实例是在云中运行的独立数据库环境。 一个数据库实例可以包含多个由用户创建的数据库，并且可以使用与独立数据库实例相同的工具和应用程序进行访问。您可以使用 AWS Command Line Interface、Amazon RDS、API 或 AWS 管理控制台 创建和修改数据库实例。

  每个数据库实例均运行一个*数据库引擎*。Amazon RDS 当前支持 MySQL、MariaDB、PostgreSQL、Oracle 和 Microsoft SQL Server 数据库引擎。每个数据库引擎有其自己支持的功能，并且每个版本的数据库引擎可能包括一些特定的功能。此外，每个数据库引擎在数据库参数组中均有一组参数，用于控制其管理的数据库的行为。

  数据库实例的计算和内存容量由*数据库实例类*决定。您可以选择最能满足您需求的数据库实例。如果一段时间后您的需求出现了变化，可以更改数据库实例。有关信息，请参阅[选择数据库实例类](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/Concepts.DBInstanceClass.html)。

  

- **Amazon RDS交互方式**

  - AWS 管理控制台

    AWS 管理控制台是一个基于 Web 的简单用户界面。您可以从控制台中管理数据库实例，而无需进行任何编程。要访问 Amazon RDS 控制台，请登录 AWS 管理控制台 并打开位于以下位置的 Amazon RDS 控制台：https://console.aws.amazon.com/rds/。

  - 命令行界面

    您可以使用 AWS Command Line Interface (AWS CLI) 以交互方式访问 Amazon RDS API。要安装 AWS CLI，请参阅安装 AWS 命令行界面。要开始使用适用于 RDS 的 AWS CLI，请参阅适用于 Amazon RDS 的 AWS Command Line Interface 参考。

  - 使用 Amazon RDS 进行编程

    如果您是一名开发人员，则可以采用编程方式访问 Amazon RDS。有关更多信息，请参阅Amazon RDS 应用程序编程接口 (API) 参考。对于应用程序开发，我们建议使用 AWS 软件开发工具包 (SDK) 之一。AWS 开发工具包可处理低级详细信息 (如身份验证、重试逻辑和错误处理)，让您可以将注意力放在应用程序逻辑上。AWS 开发工具包适用于各种语言。有关更多信息，请参阅用于 Amazon Web Services 的工具。

    

- **Amazon RDS数据库引擎**

  您可以在以下部分中查看特定数据库引擎的特定信息：

  - [Amazon RDS 上的 MariaDB](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_MariaDB.html)
  - [Amazon RDS 上的 Microsoft SQL Server](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_SQLServer.html)
  - [Amazon RDS 上的 MySQL](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)
  - [Amazon RDS 上的 Oracle](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_Oracle.html)
  - [Amazon RDS 上的 PostgreSQL](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_PostgreSQL.html)

- 资源

  - [创建 MySQL 数据库实例并连接到 MySQL 数据库实例上的数据库](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.MySQL.html)
  - [创建 PostgreSQL 数据库实例并连接到 PostgreSQL 数据库实例上的数据库](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.PostgreSQL.html)
  - [教程：创建 Web 服务器和 Amazon RDS 数据库](https://docs.aws.amazon.com/zh_cn/AmazonRDS/latest/UserGuide/TUT_WebAppWithRDS.html)
  - [FAQ](https://amazonaws-china.com/cn/rds/faqs/)

