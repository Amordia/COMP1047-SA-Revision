## Data and Communication

### Components

* **Sender:** The node sending a message.
* **Receiver:** The node receiving a message.
* **Medium:** A channel through which the message is transmitted.
* **Message:** Any piece of data or information.
* **Protocol:** The system of rules to communicate.

### Data Flow

* **Data Flow:** The route that data takes from sender to receiver.
    * **Simplex:** One-way communication (e.g., keyboard to computer).
    * **Half-duplex:** Two-way communication, but only one direction at a time (e.g., walkie-talkie).
    * **Full-duplex:** Two-way communication simultaneously (e.g., workstations, upload/download).

## Network

### Types of Networks

* **Geographical span:**
    * **Local Area Networks (LANs):** Short distances, local interconnectivity.
    * **Metropolitan Area Networks (MANs):** Connectivity over multiple buildings.
    * **Wide Area Networks (WANs):** Long distances, connectivity over large areas.
    * **Other Categories:** Personal Area Network (PAN), Storage/System Area Networks (SAN), Body Area Network (BAN), Campus Area Network (CAN), etc.
* **Structure:**
    * **Client-server:** Clients access services and resources from a central server.
    * **Peer-to-peer:** Computers are linked to a single system, tasks are split between peers, each peer has the same functionality.
* **Type of connections:**
    * **Wired:** Ethernet, Fiber Optic, Coaxial Cable.
    * **Wireless:** Wi-Fi, Bluetooth, Cellular.

## Topologies

### Types of Topologies

* **Bus:** All stations connected to a single cable (backbone).
    * **Advantages:** Cheap and easy to implement, requires less cable, no specialized network for troubleshooting.
    * **Disadvantages:** Network disruption when computers are added or removed, a break in the cable disrupts the entire network, difficult to troubleshoot.
* **Ring:** Every node is connected to two nearest nodes, forming a circle.
    * **Advantages:** Cable faults are easily located, moderately easy to install.
    * **Disadvantages:** Expansion can cause network disruption, a single break in the cable disrupts the entire network.
* **Star:** All stations connected to a centralized device (hub/switch/router).
    * **Advantages:** Easily expanded without disruption, cable failure affects only a single user, easy to troubleshoot and isolate problems.
    * **Disadvantages:** Requires more cable, a break in the central node's cable disrupts the entire network, more difficult to implement.
* **Mesh:** All nodes are interconnected.
    * **Advantages:** Provides redundant paths between devices, network expansion without disruption.
    * **Disadvantages:** Requires more cable than other LAN topologies, complicated implementation.
* **Hybrid:** Combination of Star, Ring, and Bus topologies.
    * **Example:** Star Ring network, consisting of two or more star topologies connected using a multi-station access unit (MU) as a centralized hub.

## Protocol

### Human Protocol

* Rules for specific messages sent and actions taken when messages are received or other events occur.
* Examples: "What's the time?", "I have a question", introductions.

## Network Core

### Delay

* **Packet delay:** Time taken for a packet to travel from source to destination.
    * **Sources of packet delay:**
        * **Processing delay (dproc):** Time taken by a router to process a packet (check bit errors, determine output link).
        * **Queueing delay (dqueue):** Time a packet spends waiting in a queue at the output link of a router.
        * **Transmission delay (dtrans):** Time taken to push out a packet onto a link (L/R, where L is packet length and R is link transmission rate).
        * **Propagation delay (dprop):** Time taken for a bit to travel across a physical link (d/s, where d is the length of the link and s is the propagation speed).
* **Total nodal delay (dnodal):** dproc + dqueue + dtrans + dprop.

### Throughput

* **Throughput:** Rate at which bits are sent from sender to receiver.
    * **Instantaneous throughput:** Rate at a given point in time.
    * **Average throughput:** Rate over a longer period of time.
* **Bottleneck link:** Link on an end-to-end path that constrains the end-to-end throughput.
* **End-to-end throughput:** Minimum of the transmission rates of the source, bottleneck link, and destination.

### Packet Loss

* Occurs when a packet arrives at a full queue (buffer) in a router.
* The router drops the packet as it has no space to store it.
* Lost packets may be retransmitted by the previous node, the source, or not at all.



## Open System Interconnection by International Standard Organization (ISO)

* **OSI Model:** A conceptual framework that standardizes the communication functions of a telecommunication or computing system without regard to its underlying internal structure and technology.
* **Seven Layers:**
    * **Application Layer:** Provides services to the user.
    * **Presentation Layer:** Responsible for translation, compression, and encryption.
    * **Session Layer:** Responsible for dialog control and synchronization.
    * **Transport Layer:** Responsible for the delivery of a message from one process to another.
    * **Network Layer:** Responsible for the delivery of individual packets from the source host to the destination host.
    * **Data Link Layer:** Responsible for moving frames from one hop (node) to the next.
        * **Logical Link Control (LLC) Sublayer:** Provides flow control and multiplexing for the logical link.
        * **Media Access Control (MAC) Sublayer:** Provides flow control and multiplexing for the transmission medium.
    * **Physical Layer:** Responsible for movements of individual bits from one hop (node) to the next.

## OSI Layers and Their Functions

### Application Layer

* Provides services to the user.
* Examples: HTTP, SMTP, IMAP, DNS, video streaming systems, CDNs.

### Presentation Layer

* Responsible for:
    * **Translation:** Converting data from one format to another.
    * **Compression:** Reducing the size of data for efficient transmission.
    * **Encryption:** Securing data by encoding it.

### Session Layer

* Responsible for:
    * **Dialog control:** Managing the interaction between two communicating devices.
    * **Synchronization:** Ensuring that data is sent and received in the correct order.

### Transport Layer

* Responsible for the delivery of a message from one process to another.
* Provides:
    * **Segmentation:** Dividing data into smaller units for transmission.
    * **Flow control:** Managing the rate of data transfer.
    * **Error control:** Detecting and correcting errors in data transmission.
* Examples: TCP (connection-oriented, reliable), UDP (connectionless).

### Network Layer

* Responsible for the delivery of individual packets from the source host to the destination host.
* Provides:
    * **Routing:** Determining the path for packets to travel across the network.
    * **Logical addressing:** Assigning IP addresses to devices on the network.
* Examples: IP, ICMP.

### Data Link Layer

* Responsible for moving frames from one hop (node) to the next.
* Provides:
    * **Framing:** Encapsulating network layer packets into frames.
    * **MAC addressing:** Assigning physical addresses to devices on the network.
    * **Error detection and correction:** Ensuring reliable data transfer over a single link.
    * **Flow control:** Managing the rate of data transfer between two nodes.
* Examples: Ethernet, Wi-Fi.

### Physical Layer

* Responsible for movements of individual bits from one hop (node) to the next.
* Defines:
    * **Physical characteristics of the transmission medium:** Cables, connectors, signaling methods.
    * **Encoding of bits:** How bits are represented as electrical or optical signals.

## TCP/IP Model

* A simplified networking model based on the OSI model.
* **Five Layers:**
    * **Application:** Combines the Application, Presentation, and Session layers of the OSI model.
    * **Transport:** Same as the Transport layer of the OSI model.
    * **Network:** Same as the Network layer of the OSI model.
    * **Data Link:** Same as the Data Link layer of the OSI model.
    * **Physical:** Same as the Physical layer of the OSI model.

## Addressing

* **Physical Addressing:**
    * Identifies a specific device on a local network.
    * Also known as MAC address.
    * 48 bits (6 bytes) long, represented in hexadecimal format (e.g., 07:01:02:01:2C:4B).
* **Logical Addressing:**
    * Identifies a device on the internet.
    * Also known as IP address.
    * 32 bits (IPv4) or 128 bits (IPv6) long.
* **Port Addressing:**
    * Identifies a specific process or service running on a device.
    * 16 bits long, represented as a decimal number (e.g., 80 for HTTP).
* **Specific Addressing:**
    * Identifies a specific piece of data within an application.
    * Examples: URLs, file names.

## Socket Number

* Combination of an IP address and a port number.
* Uniquely identifies a communication endpoint for a specific process on a specific device.
* Used by TCP and UDP to establish connections and send data.
* Example: tcp, hostname, 1028.

## Well-known Port Numbers

* Ports 0 to 1023 are reserved for well-known services (e.g., 80 for HTTP, 25 for SMTP).
* Registered ports are from 1024 to 49151.
* Ports from 49152 to 65535 can be used dynamically by applications.



## Transport-layer Protocols

* Two primary protocols cater to diverse application needs:
    * **UDP (User Datagram Protocol):** Lightweight, minimal overhead, prioritizes speed over reliability.
    * **TCP (Transmission Control Protocol):** Heavyweight, significant overhead, ensures reliable data transfer.

## User Datagram Protocol (UDP)

* **Use Cases:**
    * Streaming multimedia applications (loss-tolerant, rate-sensitive).
    * DNS (Domain Name System).
    * SNMP (Simple Network Management Protocol).
    * HTTP/3.
* **Characteristics:**
    * Connectionless: No formal connection establishment or teardown.
    * Unreliable: No guarantee of data delivery or order.
    * Minimal Overhead: Efficient for applications where speed is paramount.
* **Reliability Enhancement:**
    * If reliable transfer is needed over UDP, it must be implemented at the application layer.
    * Congestion control can also be added at the application layer.

### UDP Message Format

* **Source Port:** Port number used by the sending application.
* **Destination Port:** Port number used by the receiving application.
* **Checksum:** Used for error detection in the UDP packet.
* **Packet Length:** Length of the user data portion in bytes.

### UDP Checksum

* **Goal:** Detect errors (bit flips) in the transmitted segment.
* **Mechanism:**
    * Sender calculates the checksum of the UDP segment (including header and data).
    * Receiver computes the checksum of the received segment.
    * If the checksums match, no error is detected (although errors might still exist).
    * If the checksums don't match, an error is detected.
* **Weakness:** Provides weak protection as some bit flips might not alter the checksum.

## Transmission Control Protocol (TCP)

* **Characteristics:**
    * Connection-oriented: Requires connection establishment and teardown.
    * Reliable: Guarantees data delivery and order.
    * Full-duplex: Allows simultaneous data flow in both directions.
    * Flow controlled: Prevents sender from overwhelming the receiver.
    * Congestion controlled: Adjusts transmission rate to network conditions.

### TCP Message Format

* **Source Port:** Port number used by the sending application.
* **Destination Port:** Port number used by the receiving application.
* **Sequence Number:** Uniquely identifies each byte transmitted to ensure reliable delivery.
* **Acknowledgement Number:** Indicates the next expected byte in the data stream.
* **Flags:** Control bits for various TCP functions (SYN, FIN, RESET, ACK, PUSH, URG).
* **Checksum:** Used for error detection in the TCP header and data.
* **Advertised Window Size:** Used for flow control, indicating the amount of free space in the receiver's buffer.
* **Urgent Data Pointer:** Marks the end of urgent data within the TCP payload.

### TCP Buffer Overflow

* **Congestion:** Occurs when the input rate exceeds the output rate for a period, leading to buffer overflow and packet loss.
* **Causes:**
    * Slower links in the network path.
    * Concentrated flows converging at a bottleneck point.
* **Mitigation:** Congestion control mechanisms aim to reduce transmission rates to alleviate congestion.

### TCP Advertised Window Size

* **Purpose:** Flow control mechanism to prevent the sender from overwhelming the receiver.
* **Mechanism:**
    * Receiver advertises the amount of free space in its receive buffer through the "Advertised Window Size" field in the TCP header.
    * Sender limits the amount of unacknowledged data to the advertised window size, ensuring the receiver's buffer doesn't overflow.
* **Factors:**
    * Size of the receive buffer: Fixed at connection establishment.
    * Amount of data currently buffered: Dynamically changes as data is received and processed.
* **Calculation:** Advertised Window = SizeRecvBuffer - (LastByteRecv - LastByteRead).

## Summary

* UDP provides a fast but unreliable transport service, suitable for applications where speed is crucial and some data loss is tolerable.
* TCP offers a reliable and ordered data transfer service, essential for applications requiring data integrity and guaranteed delivery.
* Both protocols utilize port numbers for multiplexing, allowing multiple applications to share a single IP address.
* TCP incorporates flow control and congestion control mechanisms to optimize data transfer efficiency and prevent network congestion.



## Congestion Control

* **Congestion:** Occurs when too many sources send too much data too fast for the network to handle.
* **Manifestations:**
    * Long delays (queueing in router buffers).
    * Packet loss (buffer overflow at routers).

### Causes

* **High arrival rate:** When the arrival rate of packets at a router exceeds its output link capacity.
* **Finite buffer size:** Routers have limited buffer space, leading to packet loss when buffers fill up.
* **Retransmissions:** Lost packets trigger retransmissions, increasing the traffic load and exacerbating congestion.
* **Multiple senders:** Many senders competing for the same network resources.
* **Multi-hop paths:** Packets traversing multiple routers, increasing the chance of encountering congestion.

### Costs

* **Increased delay:** Packets experience longer queueing delays at congested routers.
* **Reduced throughput:** Packet loss and retransmissions decrease the effective throughput.
* **Wasted bandwidth:** Unnecessary retransmissions consume bandwidth without contributing to useful data transfer.
* **Upstream capacity waste:** Transmission capacity and buffering used for packets lost downstream are wasted.
* **Unfairness:** Some flows may disproportionately consume bandwidth, starving others.

## Performance Analysis

### Performance Evaluation Approaches

* **Analytical modeling:** Using mathematical models to analyze system behavior.
    * **Closed-form expressions:** Provide exact solutions for simple systems.
    * **Numerical methods:** Approximate solutions for complex systems.
* **Simulation:** Building and running a computer model of the system.
    * **Discrete-event simulation:** Modeling system behavior as a sequence of events.
* **Experimental measurement:** Deploying and measuring the performance of a real system.

### Network Simulator 2 (NS2)

* **Discrete-event simulator:** Simulates network behavior by processing events related to packets.
* **Object-oriented:** Uses C++ for event processing and Otcl for user interface and simulation control.
* **Features:**
    * Simulates various network types: wired, wireless, mesh, satellite.
    * Supports a wide range of protocols: MAC, network, transport, application.
    * Provides tools for trace file analysis and visualization.

### Otcl Scripts for NS2

* **Purpose:** Control and configure NS2 simulations.
* **Steps:**
    1. Create a simulator object.
    2. Define the network topology: nodes, links, queues, loss modules.
    3. Configure the traffic scenario: transport protocols, traffic generators, routing.
    4. Set simulation parameters: time, random number generators.
    5. Start the simulation.
* **Language:** Otcl (Object Tool Command Language).
* **Components:**
    * **Scheduler:** Manages the simulation time and events.
    * **Nodes:** Represent network devices.
    * **Links:** Connect nodes, define bandwidth and delay.
    * **Queues:** Buffer packets at nodes.
    * **Loss modules:** Simulate packet loss.
    * **Agents:** Implement transport protocols.
    * **Traffic generators:** Generate network traffic.

## Analyzing Network Performance

### Delay

* **Definition:** Time taken for a packet to travel from source to destination.
* **Components:**
    * Processing delay: Time spent by routers processing packets.
    * Queueing delay: Time spent waiting in router queues.
    * Transmission delay: Time taken to push a packet onto a link.
    * Propagation delay: Time taken for a bit to travel across a link.
* **Measurement:** Using timestamps in trace files or network monitoring tools.

### Throughput

* **Definition:** Rate at which data is successfully transferred from source to destination.
* **Measurement:**
    * End-to-end throughput: Measured at the application layer.
    * Link throughput: Measured at individual links.
* **Factors affecting throughput:**
    * Bandwidth: Capacity of the network links.
    * Congestion: Packet loss and retransmissions reduce throughput.
    * Flow control: Limits sender's transmission rate, potentially reducing throughput.

### Packet Drop/Delivery

* **Packet drop:** Occurs when a router's buffer is full and it discards incoming packets.
* **Packet delivery:** Successful transmission of a packet from source to destination.
* **Measurement:**
    * Packet drop rate: Percentage of packets dropped by the network.
    * Packet delivery ratio: Percentage of packets successfully delivered.
* **Causes of packet drop:**
    * Congestion: Buffer overflow at routers.
    * Errors: Corrupted packets discarded by the network.
* **Impact of packet drop:**
    * Reduced throughput: Lost packets require retransmissions, consuming bandwidth.
    * Increased delay: Retransmissions introduce additional delay.
    * Application performance degradation: Packet loss can disrupt application functionality.



## Principles behind Internet Protocol

* **Internet Protocol (IP):** Network layer protocol responsible for routing and addressing data packets across network boundaries.
* **Connectionless:** Provides unreliable, best-effort delivery of datagrams.
* **Key Features:**
    * **Routing:** Determines the path for packets to travel from source to destination.
    * **Addressing:** Assigns unique IP addresses to devices on the network.
    * **Fragmentation and Reassembly:** Divides large packets into smaller fragments for transmission and reassembles them at the destination.
    * **Error Control:** Detects and reports errors, but does not guarantee delivery.
    * **Flow Control:** Limited support for flow control using ICMP.

### IP Datagram Header

* Contains essential information for routing and processing datagrams.
* **Header Format:**
    * **Version:** Indicates the IP version (e.g., 4 for IPv4).
    * **Header Length:** Length of the header in 32-bit words.
    * **Type of Service:** Specifies how the datagram should be handled by the network.
    * **Total Length:** Total length of the datagram in bytes.
    * **Identification:** Unique identifier for the datagram.
    * **Flags:** Control bits for fragmentation and other options.
    * **Fragment Offset:** Position of a fragment within the original datagram.
    * **Time to Live (TTL):** Remaining hops allowed for the datagram.
    * **Protocol:** Identifies the upper layer protocol (e.g., TCP or UDP).
    * **Header Checksum:** Used for error detection.
    * **Source Address:** IP address of the sender.
    * **Destination Address:** IP address of the receiver.
    * **Options:** Optional fields for additional functionality.
    * **Padding:** Fills the header to a multiple of 32 bits.

## IP: Addressing

### Addressing Types

* **MAC Address (Layer 2):** Physical address assigned to a network interface card (NIC).
* **Logical Address (Layer 3):** IP address assigned to a device on the network.
    * **Static Addressing:** Manually assigned by an administrator.
    * **Dynamic Addressing:** Automatically assigned by DHCP (Dynamic Host Configuration Protocol).

### IP Classes

* **Class A:** First octet range: 1-126. Used for large networks.
* **Class B:** First octet range: 128-191. Used for medium-sized networks.
* **Class C:** First octet range: 192-223. Used for small networks.
* **Class D:** Used for multicast addressing.
* **Class E:** Reserved for research and experimental use.

### Addressing Format

* **IPv4 Address:** 32 bits long, represented in dotted decimal notation (e.g., 192.168.1.1).
* **Subnet Mask:** 32-bit value used to distinguish the network portion from the host portion of an IP address.

### Subnetting

* **Purpose:** Divide a network into smaller subnetworks (subnets).
* **Benefits:**
    * Efficient use of IP addresses.
    * Improved network performance.
    * Enhanced security.
* **Implementation:** Using a subnet mask to identify the subnet portion of the IP address.

### Classless Inter-Domain Routing (CIDR)

* **Purpose:** More flexible subnetting method that allows arbitrary-length subnet prefixes.
* **Notation:** Uses a slash (/) followed by the number of bits in the subnet prefix (e.g., 192.168.1.0/24).
* **Benefits:**
    * Efficient use of IP addresses.
    * Reduced routing table size.

### Supernetting

* **Purpose:** Combine multiple contiguous networks into a single, larger network.
* **Benefits:**
    * Reduced routing table size.
    * Simplified network management.
* **Implementation:** Using a shorter subnet prefix to represent the combined network.

---



---

# 数据与通信

## 组件

- **发送者 (Sender):** 发送消息的节点。
- **接收者 (Receiver):** 接收消息的节点。
- **介质 (Medium):** 消息传输的通道。
- **消息 (Message):** 任何数据或信息。
- **协议 (Protocol):** 通信规则的系统。

## 数据流

- **数据流 (Data Flow):** 数据从发送者到接收者的路径。
  - **单工 (Simplex):** 单向通信（例如，键盘到电脑）。
  - **半双工 (Half-duplex):** 双向通信，但一次只能一个方向（例如，对讲机）。
  - **全双工 (Full-duplex):** 同时进行的双向通信（例如，工作站的上传/下载）。

# 网络

## 网络类型

- **地理范围 (Geographical span):**
  - **局域网 (Local Area Networks, LANs):** 短距离，本地互联。
  - **城域网 (Metropolitan Area Networks, MANs):** 跨越多栋建筑的互联。
  - **广域网 (Wide Area Networks, WANs):** 长距离，大范围互联。
  - **其他类别 (Other Categories):** 个人区域网 (Personal Area Network, PAN)、存储/系统区域网 (Storage/System Area Networks, SAN)、人体区域网 (Body Area Network, BAN)、校园区域网 (Campus Area Network, CAN) 等。
- **结构 (Structure):**
  - **客户端-服务器 (Client-server):** 客户端从中央服务器访问服务和资源。
  - **对等网络 (Peer-to-peer):** 计算机链接到一个单一系统，任务在对等点之间分配，每个对等点具有相同的功能。
- **连接类型 (Type of connections):**
  - **有线 (Wired):** 以太网 (Ethernet)、光纤 (Fiber Optic)、同轴电缆 (Coaxial Cable)。
  - **无线 (Wireless):** Wi-Fi、蓝牙 (Bluetooth)、蜂窝网络 (Cellular)。

# 拓扑结构

## 拓扑结构类型

- **总线拓扑 (Bus):** 所有站点连接到一根电缆（骨干）。
  - **优点:** 便宜且易于实现，需用电缆少，无需专门的网络故障排除。
  - **缺点:** 添加或删除计算机时会中断网络，电缆断裂会中断整个网络，难以排除故障。
- **环形拓扑 (Ring):** 每个节点连接到两个最近的节点，形成一个圆环。
  - **优点:** 电缆故障易于定位，安装相对容易。
  - **缺点:** 扩展会导致网络中断，电缆中的一个断裂会中断整个网络。
- **星形拓扑 (Star):** 所有站点连接到一个集中设备（集线器/交换机/路由器）。
  - **优点:** 易于扩展，无需中断，电缆故障仅影响单个用户，易于故障排除和隔离问题。
  - **缺点:** 需要更多的电缆，中心节点的电缆断裂会中断整个网络，实施较难。
- **网状拓扑 (Mesh):** 所有节点互相连接。
  - **优点:** 提供设备之间的冗余路径，网络扩展无中断。
  - **缺点:** 需要比其他局域网拓扑更多的电缆，实施复杂。
- **混合拓扑 (Hybrid):** 星形、环形和总线拓扑的组合。
  - **示例:** 星形环形网络，由使用多站访问单元 (MU) 作为集中式集线器连接的两个或多个星形拓扑组成。

# 协议

## 人类协议

- 发送特定消息和在收到消息或发生其他事件时采取行动的规则。
- 示例：“几点了？”，“我有个问题”，“介绍”。

# 网络核心

## 延迟

- **包延迟 (Packet delay):** 包从源到目的地所花的时间。
  - **包延迟的来源:**
    - **处理延迟 (Processing delay, dproc):** 路由器处理包所需的时间（检查位错误，确定输出链路）。
    - **排队延迟 (Queueing delay, dqueue):** 包在路由器的输出链路队列中等待的时间。
    - **传输延迟 (Transmission delay, dtrans):** 将包推送到链路上的时间（L/R，其中L是包长度，R是链路传输速率）。
    - **传播延迟 (Propagation delay, dprop):** 比特在物理链路上传播的时间（d/s，其中d是链路长度，s是传播速度）。
- **总节点延迟 (Total nodal delay, dnodal):** dproc + dqueue + dtrans + dprop。

## 吞吐量

- **吞吐量 (Throughput):** 从发送方到接收方的比特传输速率。
  - **瞬时吞吐量 (Instantaneous throughput):** 在给定时间点的速率。
  - **平均吞吐量 (Average throughput):** 在较长时间内的速率。
- **瓶颈链路 (Bottleneck link):** 端到端路径上限制端到端吞吐量的链路。
- **端到端吞吐量 (End-to-end throughput):** 源、瓶颈链路和目的地的传输速率的最小值。

## 包丢失

- 当包到达路由器中的满队列（缓冲区）时发生。
- 路由器丢弃包，因为没有空间存储它。
- 丢失的包可能会由前一个节点、源重新传输，或者根本不传输。

# 国际标准组织 (ISO) 的开放系统互连 (OSI)

- **OSI模型:** 标准化电信或计算系统通信功能的概念框架，无需考虑其底层内部结构和技术。
- **七层:**
  - **应用层 (Application Layer):** 为用户提供服务。
  - **表示层 (Presentation Layer):** 负责翻译、压缩和加密。
  - **会话层 (Session Layer):** 负责对话控制和同步。
  - **传输层 (Transport Layer):** 负责将消息从一个进程传递到另一个进程。
  - **网络层 (Network Layer):** 负责将单个包从源主机传递到目标主机。
  - **数据链路层 (Data Link Layer):** 负责将帧从一个跳跃（节点）移动到下一个。
    - **逻辑链路控制 (Logical Link Control, LLC) 子层:** 提供流量控制和多路复用。
    - **媒体访问控制 (Media Access Control, MAC) 子层:** 提供流量控制和多路复用传输介质。
  - **物理层 (Physical Layer):** 负责将单个比特从一个跳跃（节点）移动到下一个。

# OSI层及其功能

## 应用层

- 为用户提供服务。
- 示例: HTTP, SMTP, IMAP, DNS, 视频流系统, 内容分发网络 (CDNs)。

## 表示层

- 负责：
  - **翻译 (Translation):** 将数据从一种格式转换为另一种格式。
  - **压缩 (Compression):** 减少数据的大小以实现高效传输。
  - **加密 (Encryption):** 通过编码来保护数据。

## 会话层

- 负责：
  - **对话控制 (Dialog control):** 管理两个通信设备之间的交互。
  - **同步 (Synchronization):** 确保数据按正确顺序发送和接收。

## 传输层

- 负责将消息从一个进程传递到另一个进程。
- 提供：
  - **分段 (Segmentation):** 将数据划分为较小的单位进行传输。
  - **流量控制 (Flow control):** 管理数据传输速率。
  - **错误控制 (Error control):** 检测和纠正数据传输中的错误。
- 示例: TCP（面向连接，可靠），UDP（无连接）。

## 网络层

- 负责将单个包从源主机传递到目标主机。
- 提供：
  - **路由 (Routing):** 确定包跨网络传输的路径。
  - **逻辑地址 (Logical addressing):** 为网络上的设备分配IP地址。
- 示例: IP, ICMP。

## 数据链路层

- 负责将帧从一个跳跃（节点）移动到下一个。
- 提供：
  - **成帧 (Framing):** 将网络层的包封装成帧。
  - **MAC地址 (MAC addressing):** 为网络上的设备分配物理地址。
  - **错误检测和纠正 (Error detection andcorrection):** 确保在单一链路上的可靠数据传输。

  - **流量控制 (Flow control):** 管理两个节点之间的数据传输速率。
- 示例: 以太网 (Ethernet), Wi-Fi。

## 物理层

- 负责将单个比特从一个跳跃（节点）移动到下一个。
- 定义：
  - **传输介质的物理特性 (Physical characteristics of the transmission medium):** 电缆、连接器、信号方法。
  - **比特编码 (Encoding of bits):** 如何将比特表示为电信号或光信号。

# TCP/IP模型

- 基于OSI模型的简化网络模型。
- **五层:**
  - **应用层 (Application):** 合并了OSI模型的应用层、表示层和会话层。
  - **传输层 (Transport):** 与OSI模型的传输层相同。
  - **网络层 (Network):** 与OSI模型的网络层相同。
  - **数据链路层 (Data Link):** 与OSI模型的数据链路层相同。
  - **物理层 (Physical):** 与OSI模型的物理层相同。

# 地址

- **物理地址 (Physical Address):**
  - 识别本地网络上的特定设备。
  - 也称为MAC地址。
  - 长度为48位（6字节），以十六进制表示（例如，07:01:02:01:2C:4B）。
- **逻辑地址 (Logical Address):**
  - 识别互联网设备。
  - 也称为IP地址。
  - 长度为32位（IPv4）或128位（IPv6）。
- **端口地址 (Port Address):**
  - 识别设备上运行的特定进程或服务。
  - 长度为16位，以十进制表示（例如，HTTP的80端口）。
- **特定地址 (Specific Address):**
  - 识别应用程序中的特定数据。
  - 示例: URLs, 文件名。

# 套接字号

- IP地址和端口号的组合。
- 唯一标识特定设备上特定进程的通信端点。
- 由TCP和UDP用于建立连接和发送数据。
- 示例: tcp, 主机名, 1028。

# 众所周知的端口号

- 端口0到1023保留用于众所周知的服务（例如，HTTP的80端口，SMTP的25端口）。
- 注册端口从1024到49151。
- 49152到65535的端口可由应用程序动态使用。

# 传输层协议

- 两种主要协议满足不同的应用需求：
  - **用户数据报协议 (User Datagram Protocol, UDP):** 轻量级，开销小，优先速度而非可靠性。
  - **传输控制协议 (Transmission Control Protocol, TCP):** 重量级，开销大，确保可靠的数据传输。

# 用户数据报协议 (UDP)

- **使用场景:**
  - 流媒体应用（容错，速率敏感）。
  - DNS（域名系统）。
  - SNMP（简单网络管理协议）。
  - HTTP/3。
- **特性:**
  - 无连接 (Connectionless): 无需正式连接建立或拆除。
  - 不可靠 (Unreliable): 无数据传输或顺序保证。
  - 开销小 (Minimal Overhead): 适用于速度至关重要的应用。
- **可靠性增强:**
  - 如果需要通过UDP实现可靠传输，必须在应用层实现。
  - 拥塞控制也可以在应用层添加。

## UDP消息格式

- **源端口 (Source Port):** 发送应用程序使用的端口号。
- **目的端口 (Destination Port):** 接收应用程序使用的端口号。
- **校验和 (Checksum):** 用于检测UDP包中的错误。
- **包长度 (Packet Length):** 用户数据部分的长度（字节）。

## UDP校验和

- **目标:** 检测传输段中的错误（比特翻转）。
- **机制:**
  - 发送方计算UDP段的校验和（包括头和数据）。
  - 接收方计算收到段的校验和。
  - 如果校验和匹配，则未检测到错误（尽管可能仍存在错误）。
  - 如果校验和不匹配，则检测到错误。
- **弱点:** 提供较弱的保护，因为某些比特翻转可能不会改变校验和。

# 传输控制协议 (TCP)

- **特性:**
  - 面向连接 (Connection-oriented): 需要连接建立和拆除。
  - 可靠 (Reliable): 保证数据传输和顺序。
  - 全双工 (Full-duplex): 允许同时双向数据流。
  - 流量控制 (Flow controlled): 防止发送方超负荷接收方。
  - 拥塞控制 (Congestion controlled): 根据网络条件调整传输速率。

## TCP消息格式

- **源端口 (Source Port):** 发送应用程序使用的端口号。
- **目的端口 (Destination Port):** 接收应用程序使用的端口号。
- **序列号 (Sequence Number):** 唯一标识每个传输字节，以确保可靠传输。
- **确认号 (Acknowledgement Number):** 表示数据流中的下一个期望字节。
- **标志 (Flags):** 控制位，用于各种TCP功能（SYN, FIN, RESET, ACK, PUSH, URG）。
- **校验和 (Checksum):** 用于检测TCP头和数据中的错误。
- **广告窗口大小 (Advertised Window Size):** 用于流量控制，指示接收方缓冲区的空闲空间。
- **紧急数据指针 (Urgent Data Pointer):** 标记TCP负载中紧急数据的结束。

## TCP缓冲区溢出

- **拥塞 (Congestion):** 当输入速率超过一段时间的输出速率时发生，导致缓冲区溢出和包丢失。
- **原因:**
  - 网络路径中的慢速链路。
  - 汇聚在瓶颈点的集中流量。
- **缓解:** 拥塞控制机制旨在降低传输速率以缓解拥塞。

## TCP广告窗口大小

- **目的:** 流量控制机制，防止发送方超负荷接收方。
- **机制:**
  - 接收方通过TCP头中的“广告窗口大小”字段告知其接收缓冲区中的空闲空间。
  - 发送方将未确认数据的量限制在广告窗口大小内，确保接收方缓冲区不溢出。
- **因素:**
  - 接收缓冲区的大小: 在连接建立时固定。
  - 当前缓冲的数据量: 随着数据接收和处理动态变化。
- **计算:** 广告窗口 = 接收缓冲区大小 - (接收到的最后一个字节 - 读取的最后一个字节)。

# 总结

- UDP提供快速但不可靠的传输服务，适用于速度至关重要且容忍一定数据丢失的应用。
- TCP提供可靠且有序的数据传输服务，对于需要数据完整性和保证交付的应用至关重要。
- 两种协议都利用端口号进行多路复用，允许多个应用共享一个IP地址。
- TCP结合流量控制和拥塞控制机制，优化数据传输效率并防止网络拥塞。

# 拥塞控制

- **拥塞 (Congestion):** 当过多源发送数据过快，网络无法处理时发生。
- **表现:**
  - 长时间延迟（路由器缓冲区排队）。
  - 包丢失（路由器缓冲区溢出）。

## 原因

- **高到达率 (High arrival rate):** 当包到达路由器的速率超过其输出链路容量时。
- **有限的缓冲区大小 (Finite buffer size):** 路由器的缓冲区空间有限，当缓冲区填满时导致包丢失。
- **重传 (Retransmissions):** 丢失的包触发重传，增加了交通负担，加剧了拥塞。
- **多个发送者 (Multiple senders):** 多个发送者竞争相同的网络资源。
- **多跳路径 (Multi-hop paths):** 包经过多个路由器，增加了遇到拥塞的机会。

## 成本

- **增加的延迟 (Increased delay):** 包在拥塞路由器处经历较长的排队延迟。
- **减少的吞吐量 (Reduced throughput):** 包丢失和重传降低了有效吞吐量。
- **浪费的带宽 (Wasted bandwidth):** 不必要的重传消耗带宽，而不贡献有用的数据传输。
- **上游容量浪费 (Upstream capacity waste):** 用于传输下游丢失包的传输容量和缓冲被浪费。
- **不公平 (Unfairness):** 一些流量可能过度消耗带宽，使其他流量饥饿。

# 性能分析

## 性能评估方法

- **分析建模 (Analytical modeling):** 使用数学模型分析系统行为。
  - **闭式表达 (Closed-form expressions):** 为简单系统提供精确解。
  - **数值方法 (Numerical methods):** 为复杂系统提供近似解。
- **仿真 (Simulation):** 构建和运行系统的计算机模型。
  - **离散事件仿真 (Discrete-event simulation):** 将系统行为建模为一系列事件。
- **实验测量 (Experimental measurement):** 部署并测量实际系统的性能。

## 网络模拟器2 (Network Simulator 2, NS2)

- **离散事件模拟器 (Discrete-event simulator):** 通过处理与包相关的事件来模拟网络行为。
- **面向对象 (Object-oriented):** 使用C++进行事件处理，使用Otcl进行用户界面和仿真控制。
- **特点:**
  - 模拟各种网络类型：有线、无线、网状、卫星。
  - 支持多种协议：MAC、网络、传输、应用层。
  - 提供工具进行跟踪文件分析和可视化。

## 用于NS2的Otcl脚本

- **目的:** 控制和配置NS2仿真。
- **步骤:**
  1. 创建一个模拟器对象。
  2. 定义网络拓扑：节点、链路、队列、丢包模块。
  3. 配置流量场景：传输协议、流量生成器、路由。
  4. 设置仿真参数：时间、随机数生成器。
  5. 开始仿真。
- **语言:** Otcl（对象工具命令语言）。
- **组件:**
  - **调度器 (Scheduler):** 管理仿真时间和事件。
  - **节点 (Nodes):** 表示网络设备。
  - **链路 (Links):** 连接节点，定义带宽和延迟。
  - **队列 (Queues):** 在节点缓冲包。
  - **丢包模块 (Loss modules):** 模拟包丢失。
  - **代理 (Agents):** 实现传输协议。
  - **流量生成器 (Traffic generators):** 生成网络流量。

# 网络性能分析

## 延迟

- **定义:** 包从源到目的地所花的时间。
- **组件:**
  - 处理延迟：路由器处理包所花的时间。
  - 排队延迟：包在路由器队列中等待的时间。
  - 传输延迟：将包推送到链路上的时间。
  - 传播延迟：比特在链路上传播的时间。
- **测量:** 使用跟踪文件中的时间戳或网络监控工具。

## 吞吐量

- **定义:** 数据从源到目的地成功传输的速率。
- **测量:**
  - 端到端吞吐量：在应用层测量。
  - 链路吞吐量：在单个链路测量。
- **影响吞吐量的因素:**
  - 带宽：网络链路的容量。
  - 拥塞：包丢失和重传减少吞吐量。
  - 流量控制：限制发送方的传输速率，可能降低吞吐量。

## 包丢失/传输

- **包丢失 (Packet drop):** 当路由器的缓冲区满了，丢弃传入的包。
- **包传输 (Packet delivery):** 包从源到目的地的成功传输。
- **测量:**
  - 包丢失率：网络丢弃包的百分比。
  - 包传输率：成功传输包的百分比。
- **包丢失的原因:**
  - 拥塞：路由器缓冲区溢出。
  - 错误：网络丢弃损坏的包。
- **包丢失的影响:**
  - 减少吞吐量：丢失的包需要重传，消耗带宽。
  - 增加延迟：重传引入额外的延迟。
  - 应用性能下降：包丢失可能会中断应用功能。

# 互联网协议 (Internet Protocol, IP) 原理

- **互联网协议 (IP):** 负责跨网络边界路由和寻址数据包的网络层协议。
- **无连接 (Connectionless):** 提供不可靠的，尽力而为的数据报传输。
- **关键特性:**
  - **路由 (Routing):** 确定包从源到目的地的路径。
  - **地址 (Addressing):** 为网络上的设备分配唯一的IP地址。
  - **分片与重组 (Fragmentation and Reassembly):** 将大包分成小片传输，并在目的地重组。
  - **错误控制 (Error Control):** 检测和报告错误，但不保证交付。
  - **流量控制 (Flow Control):** 使用ICMP提供有限的流量控制支持。

## IP数据报头

- 包含路由和处理数据报所需的基本信息。
- **头格式:**
  - **版本 (Version):** 指示IP版本（例如，IPv4为4）。
  - **头长度 (Header Length):** 头的长度，以32位字为单位。
  - **服务类型 (Type of Service):** 指定数据报应如何由网络处理。
  - **总长度 (Total Length):** 数据报的总长度，以字节为单位。
  - **标识 (Identification):** 数据报的唯一标识符。
  - **标志 (Flags):** 控制位，用于分片和其他选项。
  - **片偏移 (Fragment Offset):** 片在原始数据报中的位置。
  - **生存时间 (Time to Live, TTL):** 数据报允许的剩余跳数。
  - **协议 (Protocol):** 标识上层协议（例如，TCP或UDP）。
  - **头校验和 (Header Checksum):** 用于检测错误。
  - **源地址 (Source Address):** 发送方的IP地址。
  - **目的地址 (Destination Address):** 接收方的IP地址。
  - **选项 (Options):** 可选字段，用于附加功能。
  - **填充 (Padding):** 将头填充到32位的倍数。

# IP: 地址

## 地址类型

- **MAC地址 (MAC Address) (层2):** 分配给网络接口卡（NIC）的物理地址。
- **逻辑地址 (Logical Address) (层3):** 分配给网络上设备的IP地址。
  - **静态地址 (Static Addressing):** 由管理员手动分配。
  - **动态地址 (Dynamic Addressing):** 由DHCP（动态主机配置协议）自动分配。

## IP类别

- **A类 (Class A):** 第一个八位字节范围：1-126。用于大型网络。
- **B类 (Class B):** 第一个八位字节范围：128-191。用于中型网络。
- **C类 (Class C):** 第一个八位字节范围：192-223。用于小型网络。
- **D类 (Class D):** 用于多播地址。
- **E类 (Class E):** 保留用于研究和实验。

## 地址格式

- **IPv4地址:** 长度为32位，以点分十进制表示（例如，192.168.1.1）。
- **子网掩码 (Subnet Mask):** 32位值，用于区分IP地址的网络部分和主机部分。

## 子网划分

- **目的:** 将网络划分为较小的子网络（子网）。
- **好处:**
  - 有效利用IP地址。
  - 提高网络性能。
  - 增强安全性。
- **实现:** 使用子网掩码来识别IP地址的子网部分。

## 无类别域间路由 (Classless Inter-Domain Routing, CIDR)

- **目的:** 更灵活的子网划分方法，允许任意长度的子网前缀。
- **表示法:** 使用斜杠（/）后跟子网前缀的位数（例如，192.168.1.0/24）。
- **好处:**
  - 有效利用IP地址。
  - 减少路由表大小。

## 超网 (Supernetting)

- **目的:** 将多个连续网络组合为一个较大的网络。
- **好处:**
  - 减少路由表大小。
  - 简化网络管理。
- **实现:** 使用较短的子网前缀来表示组合后的网络。

---



---

In TCL script, the template for creating nodes and connections can be summarized as follows:

Creating nodes:
```tcl
set node_(i) [$ns node]  ; # Create a new node, where i is the node number
```

Setting node position:
```tcl
$node_(i) set X_ $x  ; # Set the x-coordinate of the node
$node_(i) set Y_ $y  ; # Set the y-coordinate of the node
$node_(i) set Z_ 0.0  ; # Set the z-coordinate of the node
```

Creating TCP connections:
```tcl
set tcp(i) [new Agent/TCP]  ; # Create a new TCP agent, where i is the agent number
set sink(i) [new Agent/TCPSink]  ; # Create a new TCP sink, where i is the sink number
$ns attach-agent $node_(j) $tcp(i)  ; # Attach the TCP agent to node j, where j is the node number
$ns attach-agent $node_(k) $sink(i)  ; # Attach the TCP sink to node k, where k is the node number
$ns connect $tcp(i) $sink(i)  ; # Connect the TCP agent and the TCP sink
```

Creating UDP connections:
```tcl
set udp(i) [new Agent/UDP]  ; # Create a new UDP agent, where i is the agent number
set null(i) [new Agent/Null]  ; # Create a new Null agent, where i is the agent number
$ns attach-agent $node_(j) $udp(i)  ; # Attach the UDP agent to node j, where j is the node number
$ns attach-agent $node_(k) $null(i)  ; # Attach the Null agent to node k, where k is the node number
$ns connect $udp(i) $null(i)  ; # Connect the UDP agent and the Null agent
```



在TCL代码中，创建节点和连接的模板可以概括如下：

创建节点：
```tcl
set node_(i) [$ns node]  ; # 创建一个新的节点，i是节点的编号
```

设置节点的位置：
```tcl
$node_(i) set X_ $x  ; # 设置节点的x坐标
$node_(i) set Y_ $y  ; # 设置节点的y坐标
$node_(i) set Z_ 0.0  ; # 设置节点的z坐标
```

创建TCP连接：
```tcl
set tcp(i) [new Agent/TCP]  ; # 创建一个新的TCP代理，i是代理的编号
set sink(i) [new Agent/TCPSink]  ; # 创建一个新的TCP接收器，i是接收器的编号
$ns attach-agent $node_(j) $tcp(i)  ; # 将TCP代理附加到节点j上，j是节点的编号
$ns attach-agent $node_(k) $sink(i)  ; # 将TCP接收器附加到节点k上，k是节点的编号
$ns connect $tcp(i) $sink(i)  ; # 连接TCP代理和TCP接收器
```

创建UDP连接：
```tcl
set udp(i) [new Agent/UDP]  ; # 创建一个新的UDP代理，i是代理的编号
set null(i) [new Agent/Null]  ; # 创建一个新的Null代理，i是代理的编号
$ns attach-agent $node_(j) $udp(i)  ; # 将UDP代理附加到节点j上，j是节点的编号
$ns attach-agent $node_(k) $null(i)  ; # 将Null代理附加到节点k上，k是节点的编号
$ns connect $udp(i) $null(i)  ; # 连接UDP代理和Null代理
```
