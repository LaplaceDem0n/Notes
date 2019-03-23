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





### Units

$M:10^6$

$G:10^9$

$ms:10^{-3}s$





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





