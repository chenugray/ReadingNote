# VRRP
>VRRP(Virtual Router Redundancy Protocol)虚拟路由冗余协议用来消除静态缺省路由环境下的单点故障，VRRP是一个选举协议，用从局域网中VRRP路由器中选举出虚拟路由器。绑定虚拟路由器IP的VRRP路由器被称为Master，Master用来转发IP报文。当Master因为某些原因而不能转发报文后，VRRP提供动态失效转移选举出新的Master。使用VRRP提供了高度可靠性在不使用配置任何动态路由协议时。

## 术语

|术语|解释|
|:-----:|:-----:|
|VRRP Router|运行VRRP协议的路由器|
|Virtual Router|通过VRRP虚拟出来的抽象路由器，表现得就像真实路由器一样，通常会有多个Backup路由器|
|IP Address Owner|VRRP路由器中具有虚拟路由器IP地址的归属者，通常为Master|
|Primary IP Address|从一组真实接口地址中选择出来的IP地址，选举算法通常选择第一个地址|
|Virtual Router Master|绑定虚拟路由器IP地址的VRRP路由器，并且负责应答绑定IP地址的ARP请求|
|virtual Router Backup|当Virtual Router Master不可用后的备份VRRP路由器集合|
|www|www|
|www|www|
|www|www|
|www|www|
|www|www|
|www|www|
|www|www|
|www|www|

## 必须满足特性
1. IP地址备份
>IP地址备份是VRRP协议的主要功能，当选举VRRP Router Master时，以下附加功能需尽量满足:
>1. 路由黑洞时间尽可能小
>2. 在多址访问局域网中能够正常运行切支持IP流量
>3. 能够选举出多台Virtual Router进行负载均衡
>4. 在单个局域网中支持多重逻辑子网划分
2. 服务中断时间最小
>当开始Master选举之后，任何在从Backup中选举Master不必要的中断服务时间应该尽可能的短，VRRP协议确保Backup到Master的过程中尽可能平滑过渡
3. 可扩展安全策略
>虚拟路由器能够运行部署大多数安全策略，并且能够简易配置，提供可靠的安全认证机制。


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|



|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|


|www|www|www|www|
|:-----:|:-----:|:----:|:----:|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|
|www|www|www|www|





