# 计算机网络_CS144_斯坦福

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

  - ###### Syn

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



### 3-4: Playback Buffers

### 3-5 Simple Deterministic Queue Model

### 3-6 Queueing Model Properties

### 3-7: Switching and Forwarding (1)

### 3-8: Switching and Forwarding (2)

### 3-9: Rate Guarantees

### 3-10: Delay Guarantees

### 3-11: Packet Switching (recap)

### 3-12: DC Switches -- Tom Edsall

## Unit 4: Congestion Control

### 4-0: Congestion Control

### 4-1: Basics: what it is, time scales, fairness

### 4-2: Approaches: network vs end host, max min fairness, AIMD

### 4-3: Dynamics of a single AIMD flow

### 4-4: Multiple AIMD flow

### 4-5: TCP Tahoe

### 4-6: TCP RTT estimation

### 4-7: TCP Reno

### 4-8: Why AIMD

### 4-9: Reading an RFC

### 4-10: Congestion control

### 4-11: Shortcomings and improvements of TCP and congestion control -- Nandita Dukkipati

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