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





