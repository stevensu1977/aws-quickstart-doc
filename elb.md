## Elastic Load Balancing (ELB)

- **简介**

  [Elastic Load Balancing](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) 跨多个可用区中的多个目标（如 Amazon EC2 实例、容器和 IP 地址）分发传入应用程序或网络流量。Elastic Load Balancing 会在应用程序的传入流量随时间的推移发生更改时扩展负载均衡器，并可自动扩展以处理大部分工作负载。它监控健康目标上的已注册目标和流量路的健康状况。Elastic Load Balancing 支持三种负载均衡器：应用程序负载均衡器([Application Load Balancer](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/application/introduction.html))、网络负载均衡器([Network Load Balancer](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/network/introduction.html) )和 Classic 负载均衡器([Classic Load Balancer](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/classic/introduction.html))。

- **组件**

  负载均衡器,  充当客户端的单一接触点。负载均衡器在多个可用区中的多个目标 (例如 EC2 实例) 间分配应用程序的传入流量。这将提高应用程序的可用性。可以向您的负载均衡器添加一个或多个侦听器。

  侦听器,使用您配置的协议和端口检查来自客户端的连接请求，并根据您定义的规则将请求转发到一个或多个目标组。每个规则指定一个目标组、条件和优先级。满足条件时，流量会转发到目标组。您必须为每个侦听器定义一个默认规则，然后，您可以添加规则来根据请求内容指定不同目标组 (也称为*基于内容的路由*)。

  目标组, 使用您指定的协议和端口号将请求路由到一个或多个注册目标，例如 EC2 实例。您可以向多个目标组注册一个目标。您可以对每个目标组配置运行状况检查。在注册到目标组 (它是使用负载均衡器的侦听器规则指定的) 的所有目标上，执行运行状况检查。

  ![                 åºæ¬ åºç¨ç¨åºè´è½½åè¡¡å¨ çç»æé¨å             ](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/application/images/component_architecture.png)

  

- **应用程序负载均衡器(Application Load Balancer)**

​       应用程序负载均衡器(Application Load Balancer),在应用程序层正常工作，该层是开放系统互连 (OSI) 模型的第 7 层。负载均衡器收到请求后，将按照优先级顺序评估侦听器规则以确定应用哪个规则，然后从目标组中选择规则操作目标。可以配置侦听器规则，以根据应用程序流量的内容，将请求路由至不同的目标组。每个目标组的路由都是单独进行的，即使某个目标已在多个目标组中注册。 支持以下功能:

​     支持基于路径的路由。对于根据请求中的 URL 转发请求的侦听器，您可以为它配置规则。这让您可以将应用程序构造为较小的服务，并根据 URL 内容将请求路由到正确的服务。

​     支持基于主机的路由。对于基于 HTTP 标头中主机字段转发请求的侦听器，您可以为它配置规则。这使您能够使用单个负载均衡器将请求路由到多个域。

​     支持基于请求中的字段进行路由，例如标准和自定义 HTTP 标头和方法、查询参数和源 IP 地址。

​     支持将请求路由到单个 EC2 实例上的多个应用程序。可以使用多个端口向同一个目标组注册每个实例或 IP 地址。

​     支持将请求从一个 URL 重定向到另一个 URL。

​     支持返回自定义 HTTP 响应。

​     支持通过 IP 地址注册目标，包括位于负载均衡器的 VPC 之外的目标。

​     支持将 Lambda 函数注册为目标。

​     支持单独监控每个服务的运行状况，因为运行状况检查是在目标组级别定义的，并且许多 CloudWatch 指标是在目标组级别报告的。将目标组挂载到 Auto Scaling 组的功能使您能够根据需求动态扩展每个服务。

​     访问日志包含附加信息，并以压缩格式存储。



- **网络负载均衡器(Network Load Balancer)**

  网络负载均衡器在开放系统互连 (OSI) 模型的第四层运行。它每秒可以处理数百万个请求。在负载均衡器收到连接请求后，它会从默认规则的目标组中选择一个目标。它尝试在侦听器配置中指定的端口上打开一个到该选定目标的 TCP 连接。支持以下功能：

  ​    可以处理急剧波动的工作负载，并可以扩展到每秒处理数百万个请求。

  ​    支持将静态 IP 地址用于负载均衡器。还可以针对为负载均衡器启用的每个子网分配一个弹性 IP 地址。

  ​    支持通过 IP 地址注册目标，包括位于负载均衡器的 VPC 之外的目标。

  ​    支持将请求路由到单个 EC2 实例上的多个应用程序。可以使用多个端口向同一个目标组注册每个实例或 IP 地址。

  ​    支持容器化的应用程序。计划任务时，Amazon Elastic Container Service (Amazon ECS) 可以选择一个未使用的端口，并可以使用此端口向目标组注册该任务。这样可以高效地使用您的群集。

  ​    支持单独监控每个服务的运行状况，因为运行状况检查是在目标组级别定义的，而且许多 Amazon CloudWatch 指标也是在目标组级别报告的。将目标组挂载到 Auto Scaling 组的功能使您能够根据需求动态扩展每个服务。



- 资源

  [应用程序负载均衡器教程](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/application/application-load-balancer-getting-started.html)

  [使用AWS CLI 创建网络负载均衡器](https://docs.aws.amazon.com/zh_cn/elasticloadbalancing/latest/network/network-load-balancer-cli.html)

  [AWS命令行工具(AWS CLI)](https://aws.amazon.com//cli/)

  [AWS软件开发包](http://aws.amazon.com/tools/#SDKs)