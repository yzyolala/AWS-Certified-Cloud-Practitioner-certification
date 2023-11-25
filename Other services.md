## Dockers

Docker是一个软件开发平台，用于部署应用程序。
应用程序被打包在容器中，可以在任何操作系统上运行。
应用程序运行时表现一致，无论它们在哪里运行，无兼容性问题。
预测性行为，减少工作量，易于维护和部署。
可以使用任何语言、任何操作系统、任何技术。
可以非常快速地扩展容器（秒级）。

Docker镜像存储的位置：

Docker镜像存储在Docker仓库中。
公共的Docker Hub提供了多种技术或操作系统的基础镜像。
私有的Amazon ECR（Elastic Container Registry）是存放Docker镜像的地方。

对比Docker和虚拟机：

Docker是一种虚拟化技术，但并不完全相同。
资源与宿主机共享，因此一个服务器上可以运行多个容器。
图表展示了虚拟机中每个应用都有自己的客户操作系统，而Docker容器共享宿主操作系统（例如EC2实例）和Docker守护进程。

docker是容器还是虚拟机:

Docker 是一个容器化平台，它使用容器来运行和管理应用程序。

容器是轻量级的，因为它们共享宿主机的操作系统核心，而不需要像虚拟机（VM）那样为每个应用程序运行一个完整的操作系统实例。

这使得容器比传统的虚拟机更高效，启动更快，占用的系统资源更少。

简而言之，Docker 不是虚拟机，而是利用容器技术来实现应用程序的虚拟化。

## ECS

ECS 是 Elastic Container Service 的缩写，是 AWS 提供的容器管理服务。
ECS 允许用户在 AWS 云上启动 Docker 容器。
用户需要自行提供和维护基础设施，即 EC2 实例。
AWS 负责启动和停止容器，简化了容器的生命周期管理。
ECS 与应用程序负载均衡器集成，有助于实现应用程序的高可用性和负载均衡。
容器化应用程序使用容器技术，将应用程序及其依赖项打包成独立的、可移植的容器，使应用程序能够在不同环境中运行，无需担心环境差异。
AWS ECS 提供了一个平台，用于部署、运行和管理容器化应用程序，让用户专注于应用程序本身，而无需亲自管理底层的基础设施。

## Amazon Fargate：

Fargate允许在AWS上启动Docker容器。
使用Fargate时，不需要为基础设施预留EC2实例，这使得过程更简单。
Fargate是一个无服务器服务。
AWS根据你需要的CPU和RAM来运行容器。
第三张图片描述了Amazon Elastic Container Registry (ECR)：

## ECR是Elastic Container Registry的缩写。
它是AWS上的私有Docker注册表。
这是存储Docker镜像的地方，以便它们可以由ECS或Fargate运行。

## 无服务器（Serverless）架构：

无服务器是一种新范式，开发者无需管理服务器。
开发者只需部署代码。
无服务器最初等同于函数即服务（Function as a Service，FaaS）。
AWS Lambda是无服务器服务的先驱，但现在也包括管理数据库、消息传递、存储等。
无服务器并不意味着没有服务器，而是指你不需要管理或配置服务器。

## 无服务器应用：

Amazon S3：一种云存储服务。
DynamoDB：一种NoSQL数据库服务。
Fargate：一种无服务器的容器运行服务。
Lambda：AWS的无服务器计算服务，可以运行代码而无需管理服务器。

## lamda
为什么要使用AWS Lambda：


AWS Lambda 就像是一个魔法厨房，你只需要提供食谱（代码），它就会自动为你准备食物（运行代码）。

你不需要自己买厨具（服务器），也不需要清洗和维护它们，只需要等待成品出炉。

每次做饭（执行代码）你只支付食材费（实际计算时间），而不是整个厨房的费用。

而且，不论是为两个人还是两千人做饭，魔法厨房都能自动调整大小，确保每个人都能按时吃上热腾腾的菜肴。这样，你就能专注于创作新食谱，而不是忙于做饭的准备工作。

AWS Lambda是虚拟函数的概念，无需管理服务器。
函数执行时间有限，通常执行时间很短。
函数根据需求运行。
自动扩展。

AWS Lambda的好处：

定价简单，按请求和计算时间付费。
与AWS的整套服务集成。
事件驱动，需要时由AWS触发函数。
可以使用多种编程语言。
通过AWS CloudWatch容易监控。
每个函数容易获取更多资源（最高10GB的RAM）。
增加RAM也会提高CPU和网络性能。

AWS Lambda支持的编程语言：

Node.js (JavaScript)
Python
Java (Java 8 compatible)
C# (.NET Core)
Golang
C# / Powershell
Ruby
自定义运行时API（社区支持，例如Rust）
Lambda容器镜像：容器镜像必须实现Lambda运行时API，对于运行任意Docker镜像，推荐使用ECS或Fargate。

## Amazon API Gateway：

API Gateway是一种完全托管的服务，开发者可以轻松创建、发布、维护和保护API。
它是无服务器的，并且可以扩展。
支持RESTful API和WebSocket API。
提供安全性、用户身份验证、API限流、API密钥、监控等支持。
示例说明了如何构建一个无服务器API，客户端通过REST API向API Gateway发送代理请求，API Gateway将请求转发到AWS Lambda函数，Lambda函数执行CRUD操作并与DynamoDB交互。


## AWS Batch：

AWS Batch是一个完全托管的批处理服务，可以在任何规模上高效运行批处理作业。
批处理作业有开始和结束，与连续作业相对。
AWS Batch会动态地启动EC2实例或Spot实例。
AWS Batch提供所需计算/内存的正确量。
用户提交或计划批处理作业，AWS Batch完成剩下的工作。
批处理作业定义为Docker镜像，并在ECS上运行。
这有助于成本优化，减少对基础设施的关注。

## Batch vs Lambda：

Lambda函数有时间限制，运行时环境和临时磁盘空间有限，是无服务器服务。
Batch没有时间限制，任何运行时环境只要打包为Docker镜像即可，依赖于EBS/实例存储提供磁盘空间，并且依赖于EC2（可以由AWS管理）。

