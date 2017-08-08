BGP
BGP主要的功能就是交换网络的可达性信息。可达性信息足够构建AS连接图来描述其网络可达性。BGP支持CIDR，路由聚合。BGP采用TCP作为其传输协议，这也就消除了需要实现分片重传、确认以及序列化，BGP监听TCP端口179，而当BGP遇到错误时使用了TCP的graceful close。两台交换机间建立TCP连接，互相通过Open信息确认连接参数。初始数据流是BGP路由表中的一部分，被称为Adj-Ribs-Out。当路由表发生改变时就会发送增量Update消息，BGP不需要周期性的刷新路由表。
KEEPALIVE消息周期性发送来确保一直连接。Notification消息是发生某些问题或者错误时发送来关闭连接。BGP根据其所连接的邻居所在区域位置分为IBGP和EBGP。
路由信息在BGP speaker间使用Update消息传递，多条具有相同路径特征的路由会合并为一条Update消息。RIB中存储着Adj-RIBs-In、Adj-RIBs-Out、Loc-RIB。同时BGP也有机制能够同志邻居来撤销之前发布的路由信息。主要有以下三种办法：1、通过Update消息中的WITHDRAYN ROUTES字段来撤销发布。2、通过一条相同NLRI的路由替换掉。3、关闭BGP连接，将会移除邻居所发布的所有路由。

术语
Adj-RIB-In：由邻居所广播至局部路由器的路由信息，包含了未处理的路由信息。
Adj-RIB-Out：由邻居所广播至局部路由器的路由更新信息。
BGP Identifier：4字节的唯一BGP识别码，BGP启动时决定。
BGP Speaker：实现了BGP协议的路由器
EBGP：外部BGP协议，连接两个外部邻居的协议
Exteranl Peer：不同系统的BGP邻居路由器
Feasible route：能够接受并广播的路径
IBGP：内部BGP协议，连接AS内的邻居路由器的协议
Internal Peer：同一AS内的邻居路由器
IGP：Interior Gateway Protocol，在AS内部交换路由信息的协议
Loc-RIB：由本地BGP speaker‘s决策进程所创建的路由
NLRI：Network Layer Reachability Information
RIB：Routing Infomation Base
Unfeasible Route：feasible route不在可用
操作类型



