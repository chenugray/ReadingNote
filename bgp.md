#BGP
> BGP(Border Gateway Protocol)自治区间路由协议，主要作用就是交换网络可达性信息(NLRI)。NLRI足够构建出AS间的网络连接图。BGP4支持CIDR、路由聚合。
> BGP使用TCP协议作为其传输协议，这就免除了分片重组、重传、确认、以及序列。BGP监听TCP端口179，当处理BGP ERROR Notification时，TCP支持Graceful Close很好的关闭BGP连接。BGP使用TCP连接两个系统，通过Open消息建立交换协商连接参数。BGP以增量更新路由表的变化，并不要求周期性刷新路由表。Keepalive消息周期的发送确保连接不中断。Notification消息当遇到Error时，发送关闭连接。

## 术语
|术语|解释|
|:---------:|:--------------------------------:|
Adj-RIBs-In|邻居所发过来的未经处理过的路由通告信息
Adj-RIBs-Out|通过UPDATE消息至特定邻居的路由通告信息
Autonomous System|使用相同的路由策略的区域
BGP Identifier|4字节无符号整数识别发送BGP消息的发送者
BGP speaker|运行BGP协议的路由器
EBGP|外部BGP（连接外部邻居的BGP）
External Peer|不同AS间的邻居
Feasible Route|发布出去的路由，能够被收到发布消息接受者所使用
IBGP|内部BGP（连接AS内部邻居的BGP）
Internal Peer|同一AS内的邻居
IGP|AS内部交换路由信息的协议
Loc-RIBs|由BGP speaker所优选出来的路由
NLRI|Network Layer Reachability Information，网络层可达性信息
Unfeasible Route|不再可用的Feasible Route

## 路由
> BGP speaker之间通过Update消息发布路由消息，具有相同路径属性(path attributes)的多重路由可以发布在一条Update消息中。
> 存储在RIB(Routing Information Bases)的路由包含了：Adj-RIBs-In、Adj-RIBs-Out、Loc-RIBs。
> 当BGP speaker选择发布之前接收的路由，它需要在发布前添加或者修改路径属性。
> BGP同时也提供三种机制来撤销之前所发布出的路由：
> 1. 通过Update消息中的Withdrawn Route字段撤销发布路由
> 2. 通过一条同样NLRI的替代路由来替换撤销
> 3. 中断BGP speaker之间的连接，就会撤销所有该speaker所发布的所有路由信息

## 消息格式
### 消息头格式
![message_header_format.png](message_header_format.png)
> 19字节消息头：16字节Marker（全0）、2字节Length、1字节Type(1-Open、2-Update、3-Notification、4-Keepalive)。
### Open消息格式
![open_header.png](open_header.png)
> 当TCP连接建立之后，两端第一个所发送的消息就是Open消息，如果接收了Open消息之后，那么就回发回Keepalive消息来确认。
> Version:1字节标识协议版本，当前是4
> My Autonomous System:2字节标识自治系统符
> Hold Time:2字节发送者协商Hold Timer时间，最大Keepalive/Update发送间隔等待时间。该值要么为0要么至少大于3。
> BGP Identifier:4字节无符号整数，标识BGP speaker的标识符，一般用分配给其的IP地址作为标识符
> Optional Parameters Length:1字节无符号整数，表示多少字节可选参数长度
> Optional Parameters:可选参数以`<Parameter Type, Parameter Length, Parameter Value>`三元组表示。
![OptionalParameters.png](OptionalParameters.png)
> Open消息最短29字节

### Update消息格式



