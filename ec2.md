## Amazon Elastic Compute Cloud(EC2)

- **简介**

​      [Amazon Elastic Compute Cloud](https://docs.aws.amazon.com/ec2/index.html)  (简称 Amazon EC2)  在 Amazon Web Services (AWS) 云中提供可扩展的计算容量。使用 Amazon EC2 可避免前期的硬件投入，因此您能够快速开发和部署应用程序。通过使用 Amazon EC2，您可以根据自身需要启动任意数量的虚拟服务器、配置安全和网络以及管理存储。Amazon EC2 允许您根据需要进行缩放以应对需求变化或流行高峰，降低流量预测需求。



- **功能**

​      虚拟计算环境，也称为[实例](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/ec2-instances-and-amis.html)

​      实例的预配置模板，也称为 [Amazon 系统映像 (AMI)](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AMIs.html)，其中包含您的服务器需要的程序包（包括操作系统和其他软件）。

​      实例 CPU、内存、存储和网络容量的多种配置，也称为实例类型，

​      使用密钥对的实例的安全登录信息（AWS 存储公有密钥，您在安全位置存储私有密钥）

​      使用 Amazon Elastic Block Store (Amazon EBS) 的数据的持久性存储卷，也称为 Amazon EBS 卷。

​      用于存储资源的多个物理位置，例如实例和 Amazon EBS 卷，也称为区域 和可用区

​      防火墙，让您可以指定协议、端口，以及能够使用安全组到达您的实例的源 IP 范围

​      用于动态云计算的静态 IPv4 地址，称为弹性 IP 地址

​      元数据，也称为标签，您可以创建元数据并分配给您的 Amazon EC2 资源

​      您可以创建的虚拟网络，这些网络与其余 AWS 云在逻辑上隔离，并且您可以选择连接到您自己的网络，也称为 Virtual Private Cloud (VPC)



- **实例类型**

​    Amazon EC2 提供多种经过优化，适用于不同使用案例的实例类型以供选择。实例类型由 CPU、内存、存储和网络容量组成不同的组合，可让您灵活地为您的应用程序选择适当的资源组合。每种实例类型都包括一种或多种实例大小，从而使您能够扩展资源以满足目标工作负载的要求。

   Amazon EC2 提供非常丰富的[实例类型](https://aws.amazon.com/cn/ec2/instance-types/), 常见的有以下几种:

​    通用: T2, T3, M4, M5, M5a

​    计算优化型: C4, C5

​    内存优化型:  R4, R5, X1, z1d

​    加速计算(GPU): P2, P3, G3

​    存储优化:  H1, I3, D2



- **弹性伸缩**

​     [Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/zh_cn/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)  助您确保拥有适量的 Amazon EC2 实例，用于处理您的应用程序负载。通过Auto Scaling 功能你可以按需求快速将EC2 扩展(scale out)或者收缩(scale in )适当的数量，满足你多样的工作负载需求。

​    将 Amazon EC2 Auto Scaling 添加到应用程序架构是一种最大限度利用 AWS 云的方法。当您使用 Amazon EC2 Auto Scaling 时，您的应用程序将获得以下优势：

​     A. 提高容错能力。Amazon EC2 Auto Scaling 可以检测到实例何时运行状况不佳并终止实例，然后启动新实例以替换它。您还可以配置 Amazon EC2 Auto Scaling 以使用多个可用区。如果一个可用区变得不可用，则 Amazon EC2 Auto Scaling 可以在另一个可用区中启动实例以进行弥补。

​     B. 提高了可用性。Amazon EC2 Auto Scaling 有助于确保应用程序始终具有合适的容量以满足当前的流量需求。

​     C. 加强成本管理。Amazon EC2 Auto Scaling 可以根据需要动态地增加或降低容量。由于您仅为使用的 EC2 实例付费，您可以在需要的时候启动实例，并在不需要的时候终止实例以节约成本。



​    图一 Auto Scaling group 示意:

![ 			åºæ¬ Auto Scaling ç»çç¤ºæå¾ã 		](https://docs.aws.amazon.com/zh_cn/autoscaling/ec2/userguide/images/as-basic-diagram.png)



- **存储**

​    Amazon EC2 为您的实例提供了灵活、经济且易于使用的数据存储选项。各选项都具有独特的性能和耐久性。这些存储选项既可以单独使用，也可以组合使用，以便满足您的需求。

​         [Amazon Elastic Block Store](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AmazonEBS.html)

​        [Amazon EC2 实例存储](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/InstanceStorage.html)

​        [Amazon Elastic File System (Amazon EFS)](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AmazonEFS.html)

​        [Amazon Simple Storage Service (Amazon S3)](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AmazonS3.html)



​    图二 存储于EC2实例关系示意:

![       éç¨äº Amazon EC2 çå­å¨éé¡¹     ](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/images/architecture_storage.png)



- **网络**

   Amazon EC2 使用[VPC](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/using-vpc.html),通过 Amazon Virtual Private Cloud (Amazon VPC)，您可以在 AWS 云内您自己的逻辑隔离区域中定义虚拟网络，我们称之为 *Virtual Private Cloud (VPC)*。您可将 Amazon EC2 资源（如实例）启动到 VPC 的子网中。您的 VPC 与您在自己的数据中心中运行的传统网络可能极为相似，同时享有使用来自 AWS 的可扩展基础设施的优势。您可以配置您的 VPC；您可以选择它的 IP 地址范围、创建子网并配置路由表、网关和安全设置。现在您可以将您的 VPC 中的实例连接到 Internet 或您自己的数据中心。



- **其他资源**

  [启动Linux 虚拟机](https://aws.amazon.com/cn/getting-started/tutorials/launch-a-virtual-machine/)
  
  [启动Window虚拟机](https://aws.amazon.com/cn/getting-started/tutorials/launch-windows-vm/)

  [资源](https://amazonaws-china.com/cn/ec2/resources/)

  [FAQ](https://amazonaws-china.com/cn/ec2/faqs/)

