# 计算机网络_CS144_斯坦福

## Self-Reading

>   ### Engineering.Networking-SP.SelfPaced
>
>   This is the wiki for **Engineering**'s Introduction to Computer Networking : CS144
>
>   # Textbook Readings
>
>   Kurose, J. and Ross, K. Computer Networking: A Top-Down Approach.
>
>   -   Unit 1: 6th/7th Editions: Sections 1.1-1.3; 1.5; 2.1.
>   -   Unit 2: 6th/7th Editions: Sections 3.1-3.5.
>   -   Unit 3: 6th Edition pp. 22-31; 640-648. 7th Edition pp. 21-43; 709-719.
>   -   Unit 4: 6th Edition pp. 259-265; 269-279. 7th Edition pp. 261-282.
>   -   Unit 5: 6th Edition pp. 83-114. 7th Edition pp. 83-110.
>   -   Unit 6: 6th Edition pp. 305-379. 7th Edition pp. 305-348; 373-384.
>   -   Unit 7: 6th Edition pp. 433-443; 461-482. 7th Edition pp. 439-449; 467-487.
>   -   Unit 8: 6th Edition pp. 671-693. 7th Edition pp. 593-614.
>
>   # Notable Request for Comments
>
>   -   [RFC 768](https://tools.ietf.org/html/rfc768) - User Datagram Protocol (UDP)
>   -   [RFC 791](https://tools.ietf.org/html/rfc791) - Internet Protocol (IP)
>   -   [RFC 792](https://tools.ietf.org/html/rfc792) - Internet Control Message Protocol (ICMP)
>   -   [RFC 793](https://tools.ietf.org/html/rfc793) - Transmission Control Protocol (TCP)
>   -   [RFC 826](https://tools.ietf.org/html/rfc826) - An Ethernet Address Resolution Protocol (ADR)
>
>   Find more notable RFC's from [Wikipedia - List of RFCs](https://en.wikipedia.org/wiki/List_of_RFCs)
>
>   The homepage of the Internet Engineering Task Force - <https://www.ietf.org/>
>
>   View all [Official Internet Protocol Standards](https://www.rfc-editor.org/standards) here.
>
>   Wish you well!



## Unit 1: The Internet and IP

### 1-1: A Day in the Life of an Application

- 网页访问(HTTP)
  - Client-Server模型
- BT下载
  - Peer2Peer模型
  - tracker和swarm。动态交换数据
- Skype
  - Mix of these two
  - 第三方主机

### 1-2: The 4 layer Internet model  

- Application
  - 复用下面的层次
- Transport
  - TCP保证稳定传输
  - 视频通话可以用UDP，无所谓重新传
  - 包含阻塞控制
- Network
  - 负责告诉下面一层往哪里传，不管到没到
- Link
  - 以太网orWiFi，只负责传输

### 1-3: The IP service model  

- 四大性质
  - 数据报（离散数据包）
  - 不可靠（可丢包）
  - 尽力（除非必要才丢包）
  - 连接无关性（数据包可能不按顺序）
- 其他性质
  - 数据报简介（包含一些field，性质云云）

### 1-4: A day in the life of a packet

- Handshake

  - Syn

  - Syn/Ack

  - Ack

- Tools

  - Wireshark/Tshark/Traceroute

###  1-5: The Principle of Packet Switching

### 1-6: The Principle of Layering

### 1-7: The Principle of Encapsulation

### 1-8: Byte order and packet formats

Network order is Big-endian.

*The layout of a character string in memory is the same on big-endian and little-endian architectures.*

### 1-9: IPv4 addresses and CIDR

**Classes Inter-Domain Routing**

Subnet.

### 1-10: Longest prefix match (LPM)

Match the forwarding table entry or the default.

### 1-11: Address resolution protocol (ARP)

### 1-12: The Internet and IP (recap)

### 1-13: SIP -- Jon Peterson



## Unit 2: Transport

### 2-0: Transport (intro)

### 2-1: TCP service model

- 打电话——reliable
- Handshake
	- Syn-Syn/Ack-Ack
- 4 Properties
- TCP Segment Format 

### 2-2: UDP service model

- 自言自语
- 3 Properties

### 2-3: ICMP service model

- 传纸条
- Examples
	- Ping
	- Traceroute

### 2-4: End-to-end principle

- 在终端实现要实现的功能

### 2-5: Error detection

- Checksum
	- 保证检验一位错
- CRC
	- 保证检验奇数位、连续的少于CRC位数的突发错
- MAC
	- 由于key的存在，安全性高，但检错性低

### 2-6: Finite State Machines

- Boring FSM model

### 2-7: Reliable Communications - Stop and wait

- Only one packet on the flight

### 2-8: Reliable Communications - Sliding window

- N packets on the flight

- 连续性ACK。

	- 如收到1，2，3，5。只回复ACK3
	- 对TCP，回复要收的下一个，比如上一行回复ACK4

- Drop后处理

	- 回退N
		- 接收窗只有1位的时候，没法缓存，发送的只好全都再发一遍

- 算带宽

	```
	The total RTT(round trip time) for the flight = 200ms{50ms(A->B) + 150ms(B->A)}
	
	Net data Send( on the flight)=20*100bytes
	
	Bandwidth= Net data send/RTT= 10Kb
	```

	

### 2-9: Reliable Communications - Retransmission strategies

- 回退N
- 选择性重复

### 2-10: Reliable Communications - TCP header

### 2-11: Reliable Communications - Connection setup and teardown

### 2-12: Transport (recap)

讲得挺好的可以复习。

### 2-13: TCP/IP -- Kevin Fall

## Unit 3: Packet Switching

### 3-0: Packet Switching

### 3-1: The History of Networks; History of the Internet

### 3-2: What is Packet Switching?



### 3-3: Terminology, End to End Delay and Queueing Delay

- 数据包化延迟
- 传输延迟
- 排队等待延迟

*习题里大小不同的数据包消耗的总延迟算法不一样，不过暂时没看懂，上课再想吧。*

### 3-4: Playback Buffers

Q:Problem 3-4C
If a voice call has missing data it makes it hard to understand the speaker. Therefore, we commonly allow time for a limited number of retransmissions before playing the sound to the listener. If the network path (in each direction) has total packetization delay of 15ms, total propagation delay of 25ms, and queuing delay varying between 0ms and 10ms, how large (in milliseconds) does the playback buffer need to be if we want to allow for one retransmission?

*110ms*

Hint:The maximum RTT of the network is 100ms, so the packet can be retransmitted if a response has not been heard within 100ms.

### 3-5 Simple Deterministic Queue Model

### 3-6 Queueing Model Properties

- 突发慢

- 规矩快

- Little’s Result

	$L=\lambda d$

	$L$:等待队列长度

	$\lambda$:输入速率

	$d$:平均延迟

	说人话就是：average_delay = average_occupancy / arrival_rate

- 泊松过程与M\M\1队列

	*没听懂最后一个……*

	

### 3-7: Switching and Forwarding (1)

- 输出处队列
	- 最小化数据包延迟

### 3-8: Switching and Forwarding (2)

- 输入处队列
	- 高性能
	- 结合虚拟输出处队列达到最大输出带宽

### 3-9: Rate Guarantees

- 绝对等级队列
- 权重队列

### 3-10: Delay Guarantees

### 3-11: Packet Switching (recap)

### 3-12: DC Switches -- Tom Edsall

## Unit 4: Congestion Control

### 4-0: Congestion Control

### 4-1: Basics: what it is, time scales, fairness

### 4-2: Approaches: network vs end host, max min fairness, AIMD

- 一点点试探，一大步退却

### 4-3: Dynamics of a single AIMD flow

- 规则的锯齿

### 4-4: Multiple AIMD flow

- 服务器的buffer经常处于99%占用的状态

### 4-5: TCP Tahoe

- 从微小的地方指数形式起步
- drop一个就进入放阻塞状态，试探得更慢

### 4-6: TCP RTT estimation

- 改进timeout的预计算法，得到更加精确的时间
- Self-Clocking

*跳过了一道计算题*

### 4-7: TCP Reno

**这里只记录和Tohoe不同的地方**

-   多余ACK的时候并不把congestion window变成1，而是折半。
-   timeout的时候变成1

*网课的计算题好麻烦啊……*

```
Problem 4-7A
1/1 point (graded)
Recall that TCP Reno and Tahoe differ in how they handle a triple-duplicate ACKs. Reno enters a fast retransmit state while Tahoe re-enters slow start. Suppose you have a network which supports a maximum window size of 16 packets before it starts dropping packets. On this network, you first run a TCP Tahoe flow that slow starts and observe its behaviour as it reaches steady state (where you see a repetitive pattern of congestion windows emerging).

In this steady state, what is the throughput of the TCP Tahoe flow in packets/second? Call this value “A.” Assume a constant RTT estimate of 1s, and a RTT variance estimate of 0.5s.

Now, you run a TCP Reno flow and observe its steady state behaviour. What is its throughput in packets/second (call it “B”), assuming the same RTT and variance estimates as above?

Now that you’ve computed A and B, what is the value of B/A? Assume ACKs never get lost, cwnd/ssthresh are always integers, and queueing delays are negligible.


~0.51
~1
~1.18 correct
~1.52
~1.3
Explanation

Explanation: In steady state, TCP Tahoe will have a ssthresh of 8 packets. So, you have a SS phase that transmits 1+2+4+8 packets lasting 4s, and then a CA phase transmitting 9+...+16+16*+16 (the 17th packet is the round marked * is dropped) lasting 10s. Since you get a triple duplicate ACK, you enter slow start, setting ssthresh=17/2 = 8, after which the behaviour repeats. So, you transmit 15+100+16+16=147 packets every 14s, which is 10.5 packets/sec.

In steady state, TCP Reno will have also a ssthresh of 8 packets, but it always stays in CA phase. In the CA phase, you always transmit 8+9+...+16+16*+16=140 packets which lasts 11s.

The train of packets in the 10th second triggers a triple-duplicate ACK in the 11th second, and you immediately retransmit the packet in the 12th second. Then, during fast recovery, the congestion window is set to cwnd / 2 = 17 / 2 = 8. For each of the 17 duplicate ACKs (one ACK from the last packet sucessfully received in the 16* window, and an additional 16 from the packets received in the following window), cwnd is increased by one. A packet is sent once cwnd grows to 18; another is sent once cwnd grows to 19; and so on until cwnd grows to 8 + 17 = 25. Thus, a total of 1 + (25 - 18 + 1) = 9 packets are sent in the 12th second. This whole sequence repeats from the 13th second. The throughput in this case is 149/12=12.42 packets/sec.

Thus, B/A ~ 1.18.
```



### 4-8: Why AIMD

-   Chiu Jain Plot
    -   维持了用户间的平衡
        -   送数据包多的那个half的时候window size掉的也多
        -   最终接近Fair与Payload的平衡

### 4-9: Reading an RFC

### 4-10: Congestion control

### 4-11: Shortcomings and improvements of TCP and congestion control -- Nandita Dukkipati

# Midterm



## Unit 5: Applications and NATs

### 5-0: Applications and NATs





### 5-1: Network Address Translation

### 5-2: NATs - Types

### 5-3: NATs - Implications

### 5-4: NATs - Operation

### 5-5: HTTP

### 5-6: HTTP/1.1 Keep-alive

### 5-7: BitTorrent

### 5-8: DNS 1

### 5-9: DNS 2

### 5-10: DNS 3

### 5-11: DHCP

### 5-12: Applications and NATs (recap)

## Unit 6: Routing

### 6-0: Routing

### 6-1: Flooding, source routing and spanning trees

### 6-2: Bellman Ford

### 6-3: Dijkstra

### 6-4: Internet (RIP, OSPF) AS's

### 6-5: BGP

### 6-6: Multicast

### 6-7: Spanning Tree

### 6-8: IPv6

### 6-9: Routing

### 6-10: Routing Today -- David Ward

### 6-11: BGP Past, Present and Future -- Jennifer Rexford

## Unit 7: Lower Layers

### 7-0: Lower Layers

### 7-1: Shannon Capacity and Modulation

### 7-2: Bit Errors

### 7-3: Clocks

### 7-4: FEC and Reed-Solomon

### 7-5: MAC and CSMA/CD

### 7-6: Ethernet

### 7-7: Wireless is Different

### 7-8: MAC

### 7-9: CSMA/CA

### 7-10: RTS/CTS

### 7-11: WiFi

### 7-12: IP Fragmentation

### 7-13: Lower Layers (recap)

### 7-14: Cloud Managed Wifi -- Sanjit Biswas

## Unit 8: Security

### 8-0: Security

### 8-1: Introduction to Network Attacks

### 8-2: Layer 2 Attacks

### 8-2a: Demo: MAC Overflow Attack

### 8-2b: Demo: DHCP/DNS Masquearade Attack

### 8-3: Layer 3 Attacks

### 8-4: Denial of Service

### 8-5: Security Principles

### 8-6: Confidentiality

### 8-7: Integrity

### 8-8: Public Key Cryptography

### 8-9: Certificates

### 8-10: TLS

### 8-11: Security

### 8-12: Security and Openess -- Reed Hunt

### 8-13: Security -- Dan Boneh

### 