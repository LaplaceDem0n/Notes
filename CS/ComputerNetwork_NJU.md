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

CSMA collisions???



### Units

$M:10^6$

$G:10^9$

$ms:10^{-3}s$





# Labs

## Info

7次作业，一堆Lab。

## Lab1







