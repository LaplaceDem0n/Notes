

# ComputerNetwork_NJU



[TOC]

## Week1

### Switched network

#### Circuit switching

-   Multiplexing
    -   **Time** division multiplexing
    -   **Frequency** division multiplexing
    -   Both
-   Timing in circuit switching
    -   **Delay**-May lack of resources
-   Pros
    -   **Predictable** performance
    -   **Simple/fast** (once established)
-   Cons
    -   Complexity of **setup/tear down**
    -   **Inefficient** when traffic is **bursty**
    -   **Delay** on setup
    -   …

#### Packet switching/统计性交换

-   统计——在大多数情况下各用户的突发需求合计不超过交换机处理能力
-   Pros
-   Cons



### Performance

#### Delay

-   Four components
    -   Transmission(Due to link properties)
        -   对应数据包化延迟
        -   Packet size/Rate of link
        -   数据包大小/链路传输率
    -   Propagation(Due to link properties)
        -   Link length/Speed of link
        -   大概是链路长度/0.66*光速
    -   Queuing(Due to traffic mix & switch internals)
        -   Queuing theory 
            -   Average rate A
            -   Peak rate P
            -   Waiting time W
        -   对应Little‘s Result
    -   Processing(Due to traffic mix & switch internals)
        -   现代交换机为$ns$级，可忽略
-   Bandwidth-Delay Product
    -   Bandwidth * Propagation delay

TBD:Pic on PDF 51

#### Loss

#### Throughput

## Week 3

### Laying

pros & cons 

### Data link

#### Main function

-   Framing-封装
-   Link manage-决定谁可以通信
-   Reliable-WiFi一次发送双倍的包





Random access MAC protocol

CSMA-载波监听，说话前听听有人讲话嘛w

CD-冲突检测



Ethernet最短包长度64Bytes。如果太短，会在没有监听到的情况下发包，反而不知道自己的包被干涉。



## Week4

### Spanning tree approach

## Week5

Lan & Wlan

无线网络的模式

- 基站模式
- 无基站模式（ad-hoc）



单跳与多跳

多径效应

CSMA/CA

## Week6



### Units

$M:10^6$

$G:10^9$

$ms:10^{-3}s$

# Week7-8

补充阅读：英文第六版虚拟电路内容。

# Week 9

## BGP

**main topic**:

	1. route selcetion
 	2. route export (Gao-Rex rule)![gr](ComputerNetwork_NJU.assets/gr.png)

**Detail**:

	1. 4 Attrs

**Issues**

…



# Week13

## PPT4.1 TCP basic

1. Stop & wait: OK with short distance. Thoughput ~ Data/RTT.
2. Sliding window(with buffer). 

1. Cumilative/Selective ACK

1. GBN(Used in data center
2. Selective Repeat(Compare in screenshot)

## PPT4.2 TCP setup & teardown

MaxSegSize+IPhdr+TCPhdr=MTU

esitimateRTT:K/P algorithm(see screenshot)

## PPT4.3 TCP FLow Control

min{CWND(Router),RWND(Reciever)}=SenderSideWindows

Slow start->(ssthresh)->AIMD->Why AIMD(Theory)

Summary(Screenshot)

## PPT4.4 TCP Congestion control

7 implications

1. 不同RTT有不公平的吞吐量
2. 需要多条TCP链接使高速Link占满
3. 新变种：RateBasedTCPCongestionControl-用方程计算，更加稳定，对流媒体应用友好。
4. 存在不是因为拥塞而造成的包丢失
5. 对于短流，不适用。他们甚至没有达到ssthresh
6. 短流也要参与Buffer里的排队
7. 很容易Cheat
8. …



# Week15

NAT->DNS->HTTP

## HTTP

- History
- Components
  - URL定位内容
    - 文件
    - 函数
  - HTTP表达内容
    - 用HTTP1.1举例

HTTP1.1

1. 使用明文表示动作，如GET\RESPONSE
2. stateless->Cookies
3. Performance
   1. Indepently
   2. Persistantly
   3. Pipeline over same connection
   4. Parallel connection
   5. Caching
      1. How
      2. Where
         1. Client
         2. Forward proxy
         3. Reverse proxy



## 网络安全



# Final review

-   闭卷
-   不用手写程序
-   可带计算器
-   可能有OfficeHour
-   范围内大概率会考，PPT出现的都可能会考
-   8个问题

## Q

网络层：LS/DV与RIP/OSPF/BGP的对应关系。

传输层：TCP分手分几种。流控和拥塞控制的区别。

应用层：CDN？

安全：

# Labs

## Info

7次作业，一堆Lab。

## Lab1

## Lab2

### 上课讲解



**Q**

内核协议栈？

网卡混杂模式？

为什么头文件要这样定义？

```C++
enum
  {
    IPPROTO_IP = 0,	   /* Dummy protocol for TCP.  */
#define IPPROTO_IP		IPPROTO_IP
    IPPROTO_ICMP = 1,	   /* Internet Control Message Protocol.  */
#define IPPROTO_ICMP		IPPROTO_ICMP
    IPPROTO_IGMP = 2,	   /* Internet Group Management Protocol. */
#define IPPROTO_IGMP		IPPROTO_IGMP
    IPPROTO_IPIP = 4,	   /* IPIP tunnels (older KA9Q tunnels use 94).  */
#define IPPROTO_IPIP		IPPROTO_IPIP
    IPPROTO_TCP = 6,	   /* Transmission Control Protocol.  */
#define IPPROTO_TCP		IPPROTO_TCP
    IPPROTO_EGP = 8,	   /* Exterior Gateway Protocol.  */
#define IPPROTO_EGP		IPPROTO_EGP
    IPPROTO_PUP = 12,	   /* PUP protocol.  */
#define IPPROTO_PUP		IPPROTO_PUP
    IPPROTO_UDP = 17,	   /* User Datagram Protocol.  */
#define IPPROTO_UDP		IPPROTO_UDP
    IPPROTO_IDP = 22,	   /* XNS IDP protocol.  */
#define IPPROTO_IDP		IPPROTO_IDP
    IPPROTO_TP = 29,	   /* SO Transport Protocol Class 4.  */
#define IPPROTO_TP		IPPROTO_TP
    IPPROTO_DCCP = 33,	   /* Datagram Congestion Control Protocol.  */
#define IPPROTO_DCCP		IPPROTO_DCCP
    IPPROTO_IPV6 = 41,     /* IPv6 header.  */
#define IPPROTO_IPV6		IPPROTO_IPV6
    IPPROTO_RSVP = 46,	   /* Reservation Protocol.  */
#define IPPROTO_RSVP		IPPROTO_RSVP
    IPPROTO_GRE = 47,	   /* General Routing Encapsulation.  */
#define IPPROTO_GRE		IPPROTO_GRE
    IPPROTO_ESP = 50,      /* encapsulating security payload.  */
#define IPPROTO_ESP		IPPROTO_ESP
    IPPROTO_AH = 51,       /* authentication header.  */
#define IPPROTO_AH		IPPROTO_AH
    IPPROTO_MTP = 92,	   /* Multicast Transport Protocol.  */
#define IPPROTO_MTP		IPPROTO_MTP
    IPPROTO_BEETPH = 94,   /* IP option pseudo header for BEET.  */
#define IPPROTO_BEETPH		IPPROTO_BEETPH
    IPPROTO_ENCAP = 98,	   /* Encapsulation Header.  */
#define IPPROTO_ENCAP		IPPROTO_ENCAP
    IPPROTO_PIM = 103,	   /* Protocol Independent Multicast.  */
#define IPPROTO_PIM		IPPROTO_PIM
    IPPROTO_COMP = 108,	   /* Compression Header Protocol.  */
#define IPPROTO_COMP		IPPROTO_COMP
    IPPROTO_SCTP = 132,	   /* Stream Control Transmission Protocol.  */
#define IPPROTO_SCTP		IPPROTO_SCTP
    IPPROTO_UDPLITE = 136, /* UDP-Lite protocol.  */
#define IPPROTO_UDPLITE		IPPROTO_UDPLITE
    IPPROTO_MPLS = 137,    /* MPLS in IP.  */
#define IPPROTO_MPLS		IPPROTO_MPLS
    IPPROTO_RAW = 255,	   /* Raw IP packets.  */
#define IPPROTO_RAW		IPPROTO_RAW
    IPPROTO_MAX
  };

/* If __USE_KERNEL_IPV6_DEFS is 1 then the user has included the kernel
   network headers first and we should use those ABI-identical definitions
   instead of our own, otherwise 0.  */
#if !__USE_KERNEL_IPV6_DEFS
enum
  {
    IPPROTO_HOPOPTS = 0,   /* IPv6 Hop-by-Hop options.  */
#define IPPROTO_HOPOPTS		IPPROTO_HOPOPTS
    IPPROTO_ROUTING = 43,  /* IPv6 routing header.  */
#define IPPROTO_ROUTING		IPPROTO_ROUTING
    IPPROTO_FRAGMENT = 44, /* IPv6 fragmentation header.  */
#define IPPROTO_FRAGMENT	IPPROTO_FRAGMENT
    IPPROTO_ICMPV6 = 58,   /* ICMPv6.  */
#define IPPROTO_ICMPV6		IPPROTO_ICMPV6
    IPPROTO_NONE = 59,     /* IPv6 no next header.  */
#define IPPROTO_NONE		IPPROTO_NONE
    IPPROTO_DSTOPTS = 60,  /* IPv6 destination options.  */
#define IPPROTO_DSTOPTS		IPPROTO_DSTOPTS
    IPPROTO_MH = 135       /* IPv6 mobility header.  */
#define IPPROTO_MH		IPPROTO_MH
  };
#endif /* !__USE_KERNEL_IPV6_DEFS */
```

跳过了Header？？

### 入门PDF阅读

SOCK_RAW包含IP header以及其他subsequent header







# Homework

| *Deadline* | *Homework*                                                   |
| ---------- | ------------------------------------------------------------ |
| *Mar 21*   | *Introduction: (Textbook Charpter 1: R12, R23, R24, R25)*    |
| *Apr 4*    | *Direct Link Networks: (Textbook Charpter 5: R4, R5, R6, R8, P3, P5, P6, P8, P10, P18, P19, P23, P24, P25, P26) (Textbook Charpter 6: R7, P5, P6, P8)* |
| *Apr 18*   | *Packet Switching Networks (Textbook Charpter 4: R1, R2, R21, P1, P2, P26, P28, P30, P34)* |
| *May 2*    | *Internetworking (Text book Charpter 4: R14, R16, R19, R20, R23, R29, R35, R36, P13, P17, P22, P35, P37, P45)* |
| *May 16*   | *End-to-End Protocols (Textbook Charpter 3: R5, R8, R14, P1, P19, P27, P32, P40, P50, P52)* |
| *May 30*   | *Congestion Control and QoS (Textbook Charpter 7: R19, P1, P3, P5, P18, P20)* |
| *Jun 13*   | *Network Security (Textbook Charpter 8: R5, R6, R15, R23, P3, P7, P8, P9, P16, P18, P19)* |