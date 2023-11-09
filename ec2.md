## aws ec2是干嘛的

AWS EC2（Amazon Elastic Compute Cloud）是亚马逊提供的一项云计算服务，它允许用户在亚马逊的数据中心虚拟运行应用程序。

EC2 提供可伸缩的计算能力，使得开发者可以通过网络快速启动虚拟服务器、管理存储、安全和网络配置，以及在需要时扩展或缩减资源，从而优化成本。

EC2 提供了多种服务器实例类型，以适应不同的工作负载和应用程序。比如，有些实例优化了计算性能，有些则优化了内存使用，还有些优化了存储性能等等。

用户可以根据需求选择适当的实例类型，并且可以使用镜像（AMI - Amazon Machine Images）来加载带有所需软件配置的虚拟服务器。

总而言之，AWS EC2 提供的是一种灵活、可控、按需计费的计算资源，适用于从小规模开发测试到大规模生产部署的各种应用场景。

## ec2 instance是干嘛的

EC2 instance 就像是一台你可以随意配置的虚拟电脑。它存在于亚马逊的云端服务器里，你可以通过互联网远程使用它。

你可以告诉亚马逊你需要多大的电脑资源，比如处理器有多强、内存有多大等等，然后亚马逊就会在云端为你提供一台符合这些要求的虚拟电脑。

你可以在这台虚拟电脑上做很多事情，比如运行网站、处理数据、运行应用程序等。

你用不到它的时候可以关掉它，这样就不会产生费用；需要的时候再开机使用，就像平时我们用自己的笔记本电脑一样，只不过这台电脑非常强大，而且是在互联网上。

## SSH（Secure Shell），IPv4/IPv6，HTTP，UDP/TCP

SSH

用途：SSH用于提供安全的网络服务，主要是远程登录到服务器。

特点：它通过加密来确保连接的安全，避免数据被窃取或篡改。

层级：SSH工作在应用层，为其他协议如SCP（安全复制协议）或SFTP（SSH文件传输协议）提供安全的运输机制。

IPv4/IPv6

用途：这些是互联网协议版本，用于在网络中标识设备，并将数据从一个设备传输到另一个设备。

特点：IPv4是一个32位地址协议，而IPv6是128位，后者提供了更多的地址空间和一些额外的功能，如自动配置和改进的隐私。

层级：它们工作在网络层，负责在网络上路由数据包。

HTTP

用途：HTTP是用于传输网页数据的协议，是Web通信的基础。

特点：HTTP协议明文传输数据，所以本身不提供数据加密，HTTPS是它的安全版本，它使用SSL/TLS来加密HTTP的通信。

层级：HTTP工作在应用层，是一个建立在底层TCP/IP协议之上的协议。

TCP

用途：TCP是一种面向连接的协议，用于在网络中可靠地传输数据。

特点：它确保数据完整性和顺序，通过三次握手建立连接，并使用确认和重传机制确保数据正确送达。

应用：HTTP和SSH通常建立在TCP之上，因为它们需要可靠的数据传输。

UDP

用途：UDP是一种无连接的协议，用于快速传输数据，但不保证可靠性。

特点：它不保证数据包的顺序或可靠到达，没有握手过程，因此延迟较小。

应用：适用于对速度要求高于可靠性的应用，如在线视频或游戏。

关系与区别

关系：TCP和UDP是传输层的协议，它们工作在IPv4/IPv6之上，负责将数据传输到正确的应用进程上。SSH和HTTP是应用层的协议，它们依赖TCP来确保数据的可靠传输（尽管SSH和HTTP都可以配置为使用UDP）。

区别：

TCP vs UDP：TCP保证数据的顺序和完整性，适用于需要可靠性的应用。UDP传输快但不保证可靠性，适用于对实时性要求高的应用。

TCP/UDP vs SSH：SSH是一个应用层协议，提供安全的数据传输，通常使用TCP来保证连接的可靠性。

TCP/UDP vs HTTP：HTTP是建立在TCP上的，用于网页数据的传输，而不是建立在UDP上，因为网页加载通常要求数据完整无误。

TCP/UDP vs IPv4/IPv6：IPv4和IPv6是网络层协议，负责数据包的寻址和路由。TCP和UDP工作在这些协议的上一层，负责确保数据包能够到达正确的应用程序。

在实际的网络通信中，IPv4/IPv6是地址和邮路，TCP或UDP是邮递员的传递方法（TCP像是需要签收确认的挂号信，UDP像是扔进你家信箱的广告邮件），而SSH和HTTP是邮件的内容和邮件上的机密印章（SSH提供安全性，HTTP决定内容的格式）。

## SSH，IPv4/IPv6，HTTP，UDP/TCP分别在什么层

SSH (Secure Shell)：SSH是一种协议，它提供加密的终端会话，用于安全地远程访问另一台计算机。SSH通常运行在应用层，但它是建立在较低层的传输协议之上，通常是TCP。

IPv4/IPv6 (Internet Protocol version 4/6)：这些是网络层协议，用于路由和数据包传输，确保数据可以在网络中的不同节点之间传递。

HTTP (Hypertext Transfer Protocol)：HTTP是应用层协议，用于Web浏览器和服务器之间的通信，传输如网页文本、图片和视频等超媒体信息。

UDP (User Datagram Protocol) 和 TCP (Transmission Control Protocol)：这两种都是传输层协议。TCP提供的是一种面向连接的、可靠的数据传输服务，确保数据按顺序且正确无误地到达。

UDP则提供的是一种无连接的传输服务，它不保证数据包的顺序或可靠性，但是在某些情况下，它比TCP更快。

总结一下，它们在OSI模型中所处的层级如下：

应用层：SSH, HTTP

传输层：UDP, TCP

网络层：IPv4, IPv6

## 用ssh链接aws ec2 instance

```
(base) zhenyingyu@ZhenyingdeMBP aws % ls
ec2-tutorial.pem
(base) zhenyingyu@ZhenyingdeMBP aws % ssh -i ec2-tutorial.pem ec2-user@3.16.181.72
The authenticity of host '3.16.181.72 (3.16.181.72)' can't be established.
ED25519 key fingerprint is SHA256:zr73AQPkCta8c9l0AP0o5tQ6+lx5SjRUgdlWhbQEub4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '3.16.181.72' (ED25519) to the list of known hosts.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'ec2-tutorial.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "ec2-tutorial.pem": bad permissions
ec2-user@3.16.181.72: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
(base) zhenyingyu@ZhenyingdeMBP aws % chmod 0400 ec2-tutorial.pem
(base) zhenyingyu@ZhenyingdeMBP aws % ssh -i ec2-tutorial.pem ec2-user@3.16.181.72
   ,     #_
   ~\_  ####_        Amazon Linux 2
  ~~  \_#####\
  ~~     \###|       AL2 End of Life is 2025-06-30.
  ~~       \#/ ___
   ~~       V~' '->
    ~~~         /    A newer version of Amazon Linux is available!
      ~~._.   _/
         _/ _/       Amazon Linux 2023, GA and supported until 2028-03-15.
       _/m/'           https://aws.amazon.com/linux/amazon-linux-2023/

[ec2-user@ip-172-31-21-163 ~]$ whoami
ec2-user
[ec2-user@ip-172-31-21-163 ~]$ ping google.com
```

这段文本是一个终端会话的记录，显示了一系列使用SSH（Secure Shell）连接到Amazon EC2（Elastic Compute Cloud）实例的步骤。我将一步一步解释你的命令及其输出：

ls

这个命令列出了当前目录（可能是一个名为aws的目录）的内容，显示了一个名为ec2-tutorial.pem的文件，这是一个私钥文件，用于SSH连接。
ssh -i ec2-tutorial.pem ec2-user@3.16.181.72

这个命令尝试使用ec2-tutorial.pem私钥文件，通过SSH作为ec2-user用户连接到IP地址3.16.181.72的EC2实例。
第一次连接到一个SSH服务器时，系统会提示你确认服务器的真实性。当你输入yes后，服务器的公钥被保存到本地的known_hosts文件中。

接下来出现了一个错误，指出ec2-tutorial.pem文件的权限太开放（0644），这使得SSH客户端出于安全考虑拒绝使用这个私钥。

chmod 0400 ec2-tutorial.pem

为了解决权限问题，这个命令更改了ec2-tutorial.pem文件的权限，将其设置为仅所有者有读取权限，这是私钥文件所需的安全设置。
再次运行SSH连接命令后，成功连接到了EC2实例。连接成功后，出现的提示符显示了Amazon Linux 2的欢迎信息，提示Amazon Linux 2的生命周期将在2025年6月30日结束，并推荐使用新版本的Amazon Linux，支持至2028年3月15日。

whoami

这个命令用于确认当前登录的用户是ec2-user。
ping google.com

这个命令用来测试ec2-user从EC2实例到google.com的网络连接。它会发送网络包到google.com，并等待回应，以验证网络连接的状态。
综上所述，这些步骤是标准的SSH连接流程，用于从本地机器安全地连接到远程AWS EC2实例，并执行一些基本的网络测试。

## EC2 部分 — 概述

EC2 实例：AMI（操作系统）+ 实例大小（CPU + RAM）+ 存储 + 安全组 + EC2 用户数据

安全组：连接到EC2实例的防火墙

EC2 用户数据：在实例首次启动时执行的脚本

SSH：启动终端进入我们的EC2实例（端口22）

EC2 实例角色：链接到IAM角色

购买选项：按需（On-Demand），现货（Spot），预留（Reserved，包括标准和可转换），专用宿主机（Dedicated Host），专用实例（Dedicated Instance）

## 哪种EC2购买选项能提供最大的折扣，但不适合关键任务或数据库？

保留实例（Reserved Instances）

可转换实例（Convertible Instances）

专用宿主机（Dedicated Hosts）

现货实例（Spot Instances）

已选中的答案是现货实例（Spot Instances）

解释：
现货实例通常提供比其他类型购买选项更大的折扣，因为它们允许用户利用AWS上未使用的EC2计算容量，通常以远低于按需价格的成本。

然而，因为现货实例的价格会根据供求关系变化，并且AWS可以在不提前通知的情况下回收这些实例，所以它们不适合运行关键任务或数据库等需要高度可靠性的应用。

## 你可以预订EC2保留实例多长时间？

1年或3年

2年或4年

6个月或1年

1年到3年之间的任何时间

已选中的答案是1年或3年

## 哪种EC2购买选项适合你计划在一台服务器上连续运行1年的应用程序？

预留实例

竞价实例

按需实例

可转换实例

已选择的答案是“预留实例”。

解释：
在亚马逊云计算服务（AWS）中，当你计划在服务器上长期（例如1年）运行一个应用程序时，

预留实例（Reserved Instances）通常是最经济的选择，因为它们提供了较长时间内的定价优惠。

预留实例需要用户做出一定期限（1年或3年）的承诺，并相对于其他选项提供较低的使用成本。

其他选项包括：

竞价实例（Spot Instances）：提供未使用的EC2实例的容量，以市场定价出售，适合可以接受应用程序中断的场景。

按需实例（On-demand Instances）：适用于需要即时访问和无需长期承诺的计算能力的用户。

可转换实例（Convertible Instances）：是一种特殊类型的预留实例，它们允许在合同期内改变实例的属性或换成不同的实例类型。

所以，对于计划连续运行一年的服务器应用程序，选择“预留实例”是正确的。

## EFS, EC2 INSTANCE STORE, EC2 IMAGE BUILDER, AMI 

EFS (Elastic File System):
想象一下你的电脑可以让家里的所有人同时使用，而且每个人都可以从他们自己的设备访问和编辑文件。EFS就像是亚马逊云中的一个超级强大的网络驱动器，它允许多个EC2实例（亚马逊的虚拟服务器）同时连接和访问存储在里面的数据。它能够自动伸缩以适应存储的数据量，所以你用多少空间，就付多少钱。

EC2 Instance Store:
这个像是你的游戏机里的存储卡，可以让你的游戏和应用跑得飞快，但是如果你的游戏机坏了或者你决定把它换掉，那上面的数据就都没了。EC2 Instance Store提供的是临时存储，它在你的虚拟服务器（EC2实例）运行时非常快速，但是一旦你关掉这台服务器，存储上的数据就会消失。

EC2 Image Builder:
想象你有一份你喜欢的饼干食谱，你每次按这个食谱都能烤出相同的美味饼干。EC2 Image Builder就是用来制作那个“食谱”的，只不过这里的食谱是为创建亚马逊云服务器的镜像（也就是一个包含了操作系统、软件、配置的预设模板）。你可以用它来创建一个模板，每次都能用这个模板快速制作出一模一样设置的服务器。

AMI (Amazon Machine Image):
这就像是一个智能手机的备份。如果你的手机丢了或者要换新的，你可以用备份来在新手机上复原你所有的应用、照片和设置。AMI就是AWS上的服务器备份，包含了服务器的操作系统、应用程序和所有配置。你可以用AMI来创建新的服务器，新服务器会和原来那台有着一模一样的内容和设置。

## 总结

1. EBS 卷:

网络驱动器可以一次连接到一个EC2实例

映射到可用区

可以使用EBS快照进行备份/跨AZ传输EBS卷

2. AMI:

创建包含我们定制内容的现成EC2实例

3. EC2 图像构建器:

自动构建、测试和分发AMIs

4. EC2 实例存储:

高性能硬件磁盘连接到我们的EC2实例

如果我们的实例停止/终止，数据将丢失

5. EFS:

网络文件系统，可以连接到一个区域内的数百个实例

6. EFS-IA:

为不经常访问的文件优化成本的存储类

7. FSx for Windows:

Windows服务器的网络文件系统

8. FSx for Lustre:

高性能计算Linux文件系统

这是一个关于亚马逊网络服务（AWS）提供的不同存储选项的总结，特别是围绕EC2（弹性计算云）服务的存储选项。

## AMI不被用于什么？

添加你自己的软件许可

添加你自己的配置

添加你自己的操作系统

添加你自己的IP地址

解释：

AMI，或者说亚马逊机器映像，是AWS中一个预先配置好的虚拟机镜像，可以用来快速启动新的EC2实例。

它包括操作系统（比如Linux, Windows等）以及运行实例所需的其他软件配置和应用程序。

AMI可以用来添加自己的软件许可，确保新的EC2实例拥有正确的软件和许可。

AMI可以用来添加自己的配置，确保实例在启动时就具有所需的配置。

AMI也可以用来添加自己的操作系统，允许用户选择特定的操作系统版本和配置。

然而，IP地址不是AMI的一部分，因为IP地址是在实例启动时由Amazon EC2网络和安全子系统分配的。

你不能在AMI中预设一个IP地址；IP地址是动态分配给实例的，或者可以在启动后通过Elastic IP地址静态分配。
