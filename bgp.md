BGP
BGP主要的功能就是交换网络的可达性信息。可达性信息足够构建AS连接图来描述其网络可达性。BGP支持CIDR，路由聚合。BGP采用TCP作为其传输协议，这也就消除了需要实现分片重传、确认以及序列化，BGP监听TCP端口179，而当BGP遇到错误时使用了TCP的graceful close。两台交换机间建立TCP连接，互相交换Open信息确认连接参数。
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

