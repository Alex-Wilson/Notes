# Open Systems Interconnection Model (ISO 7498 AKA "OSI Model" or "OSI Stack")
Originally developed as a theoretical framework to standardize network communications with a comprehensive design. Today, the global internet utilizes the TCP/IP model making it the de facto standard for network communication, but the OSI model is still valuable for understanding, troubleshooting, and teaching networking concepts.

# OSI Cheat Sheet:

| Layer # | Layer Name   | Pneumonic | Protocol Data Unit           | Data Unit Pneumonic | Related Technologies                 | **Additional Information**           | **Client Data Path** | **Server Data Path** |
| ------- | ------------ | --------- | ---------------------------- | ------------------- | ------------------------------------ | ------------------------------------ | -------------------- | -------------------- |
| 7       | Application  | Away      | Data                         |                     | HTTP, FTP, IRC, SSH, DNS             | Network processes in application     | Start                | End                  |
| 6       | Presentation | Pizza     | Data                         |                     | SSL, TLS, SSH, IMAP, FTP, MPEG, JPEG | Data representation/encryption       | \|                   | \|                   |
| 5       | Session      | Sasuage   | Data                         | Do                  | Synch, APIs, Sockets, Ports          | Inner-Host connection                | \|                   | \|                   |
| 4       | Transport    | Throw     | Segment(TCP) / Datagram(UDP) | Some/Dead           | TCP, UDP                             | End-to-End connection                | \|                   | \|                   |
| 3       | Network      | Not       | Packet                       | People              | IP, ICMP, IPSec, ARP                 | Determining path and IP              | \|                   | \|                   |
| 2       | Data         | Do        | Frame                        | Fear                | Ethernet, Switch, Bridge             | Physical addressing with MAC and LLC | \|                   | \|                   |
| 1       | Physical     | Please    | Bit                          | Birthdays           | Fiber, Wireless, Hubs, Repeaters     | Binary transmission                  | End                  | Start                |

[Wikipedia](https://en.wikipedia.org/wiki/OSI_model)
![](Pasted%20image%2020240307162838.png)


# Layer 1: Physical Layer

#### What is it?
Where transmission of bits across the network occurs and includes physical and electrical network characteristics. Data is transmitted through some physical medium typically electricity (wired cord via voltage modulation like ethernet OR electromagnetic waves via radio transmission like Wi-Fi) or light (fiber optics use the presence or absence of light to indicate value). 

**Layer 1 devices view networks from a physical topology perspective.** 
#### Communication Methods
**Synchronous Communication:**
In synchronous communication, the sender and receiver are synchronized in time. This means that data is transmitted in a continuous stream at a constant rate, and both the sender and receiver must operate at the same clock rate or have a way to synchronize their clocks. Synchronous communication is often used in scenarios where timing precision is crucial, such as telecommunications networks and synchronous serial communication protocols like synchronous serial interface (SSI) or synchronous optical networking (SONET). 

**Asynchronous Communication:**
In asynchronous communication, data is transmitted in individual units called frames or packets, with each frame containing both data and control information. Unlike synchronous communication, there is no fixed timing relationship between the sender and receiver. Instead, each frame is sent independently, and the receiver must extract the data and control information from each frame using timing signals embedded within the data stream. Asynchronous communication is commonly used in computer networks, serial communication protocols like RS-232, and asynchronous transfer mode (ATM) networks.

#### Bandwidth Utilization
**Broadband:**
Divides bandwidth into separate channels. How TV has many channels but you can pick one to watch.

**Baseband:**
Uses all available frequencies on a medium to transmit data. How a phone is a dedicated channel to communicate with only one other person. Must utilize a reference clock. Example is a wired home ethernet connection as only the devices on the wire can transmit across it. 

**Multiplexing:**
Multiplexing is a technique used in communication systems to efficiently transmit multiple signals over a single communication channel. Think of it like a highway with multiple lanes. Instead of having separate highways for each type of traffic (e.g., cars, trucks, bikes), multiplexing allows different types of data (voice calls, internet data, video streams) to share the same "lane" or communication channel. This allows us to get more out of our networks. 

**Time-Division Multiplexing (TDM):**
Each session takes a turn, using time slots to share the medium between all users. 

**Statistical Time-Division Multiplexing (StatTDM):**
Dynamically allocates the time slots on an as-needed basis.

**Frequency-Division Multiplexing (FDM):**
Divides the medium into channels based on frequencies and each session is transmitted over a different channel 
#### Common Devices
Wires/Cables, Radio Frequencies, Hubs, Access Points, Media Converters.
Really any device that repeats or retransmits its input. 


# Layer 2: Data Layer
#### What is it?
This layer focuses on the reliable transmission of data between adjacent network nodes. It handles framing, error detection, and flow control. MAC addresses are assigned at this layer.

#### Data Link Layer
MAC (Media Access Control) and LLC (Logical Link Control) are closely related components of the Data Link layer (Layer 2). Together, they work to ensure reliable communication between network devices. MAC operates closer to the physical layer, handling tasks such as addressing and access to the physical medium, while LLC operates closer to the network layer, providing services that are independent of the underlying network technology. When data is transmitted over a network, it is encapsulated into frames at the Data Link layer

**Media Access Control (MAC):**
MAC addresses are unique identifiers assigned to network interfaces, such as network interface cards (NICs) or Wi-Fi adapters, by the manufacturer of the device. Each network interface in a device is assigned a globally unique MAC address during the manufacturing process. 
This is typically a 48-bit hexadecimal address like {##:##:##:##:##:##} where [0,2] represent the vendor code (to identify the manufacturer) and [2,4] represent the unique value from the manufacturer (to identify the source). 

 **Logical Link Control (LLC):**
A sublayer which operates alongside the MAC sublayer and is responsible for providing services that are independent of the specific network technology being used. Provides connection services and allows acknowledgment of receipt of messages. Also provides error control via checksum. The most basic form of flow control. 

#### Network Time Synchronization
Different methods for network time synchronization, which is crucial for ensuring accurate timing and coordination of data transmission within a network.

**Isochronous:**
Network Devices use a common reference clock source and create time slots for transmission 

**Synchronous:** 
Network devices agree on clocking method to indicate beginning and end of frames and can use control characters

**Asynchronous:**
Network devices reference their own internal clocks and use start and stop bits. 
#### Devices
Network Interface Cards, Bridges, Switches

# Layer 3: Network Layer
#### What is it?
The network layer is responsible for logical addressing and routing of data packets. It determines the best path for data to travel through the network based on IP addresses. Routers operate at this layer.

#### Routing Methods
**Packet Switching:**
Data is divided into packets and then forwarded. This is by far the most common network type today. 

**Circuit Switching:**
Dedicated communication link is established between two devices. Packets take the same route every time. 

**Message Switching:**
Data is divided into messages which may be stored and then forwarded. 
#### Route Discovery and Selection
Manually configured as a static route or dynamically through a routing protocol.

#### Connection Services
Augment Layer 2 connection services to improve reliability with tools like flow control and packet reordering. Supports Internet Control Message Protocol (ICMP).
#### Devices
Routers, Multi-Layer Switches, IPv4, IPv6, ICMP
# Layer 4: Transport Layer
#### What is it?
This layer ensures reliable end-to-end communication between devices. It segments and reassembles data into packets, handles error detection and recovery, and controls data flow. 

#### Transport  Protocols:
**Transmission Control Protocol:**
Connection-oriented protocol that is a reliable way to transport segments across the network. Starts with three-way handshake below to ensure connection. 

![](Pasted%20image%2020240529155133.png)

**User Datagram Protocol:**
Connectionless protocol that is an unreliable way to transport segments across the network. Most commonly used in real-time communication scenarios like streaming video or audio where sender is unaware if all datagrams were received. 

**Segment Sequencing:**
The process of assigning a sequence number to each segment of data that is transmitted over a TCP connection. These sequence numbers are used to ensure that data segments are received by the receiver in the correct order.

**Windowing:**
A flow control mechanism used to optimize the transmission of data between a sender and a receiver. It involves dynamically adjusting the amount of data that the sender is allowed to transmit without receiving an acknowledgment from the receiver.

**Buffering:**
Occurs when devices allocate memory to store segments if bandwidth isn't readily available. It involves temporarily storing data in a buffer, which is a region of memory used to hold data temporarily while it is being transferred from one location to another.

| TCP                              | UDP                            |
| -------------------------------- | ------------------------------ |
| Reliable                         | Unreliable                     |
| Connection-Oriented              | Connectionless                 |
| Segment retransmission/Windowing | No windowing or retransmission |
| Segment Sequencing               | No Sequencing                  |
| Acknowledges segments            | No acknowledgment              |

#### Devices
TCP/UDP, WAN Accelerators, Load Balancers, Firewalls, 
# Layer 5: Session Layer
#### What is it?
The session layer establishes, maintains, and terminates connections between devices. It manages sessions, or ongoing communications, between applications.

#### Vocab
**Session:**
A session can be thought of as a conversation that has to be kept separate from all of the others to prevent the intermingling of data. Sessions are setup, maintained, and torn down. 

**Establish/Setup Session:**
Checking of user credentials and assigning numbers to sessions for identification. Initiation of communication, negotiations of session parameters, resource allocation. 

**Session Control/Maintenance:**
Manages the data exchange between the two devices. It ensures that data is properly segmented, ordered, and delivered. This includes managing the flow of data to prevent congestion and handling any errors that may occur including reestablishing the connection. Maintains synchronization between the devices, often through checkpoints or synchronization points. Various control functions are performed to maintain the session.

**Session Termination:** 
Ending of a session after the transfer is done or when the other party disconncts. 

**H264:**
A video compression standard used for recording, compressing, and distributing video content. It is widely used for video streaming, video conferencing, and digital video broadcasting.

**H323:**
H.323 is a suite of protocols used for voice, video, and data conferencing over IP networks. It provides standards for audio and video communication, call control, and data sharing.

**Real Time Protocol:**
A protocol designed for delivering audio and video over IP networks in real-time. It provides mechanisms for time-stamping, sequencing, and delivering multimedia content.

NetBios:
NetBIOS is a protocol that allows applications on different computers to communicate over a local area network (LAN). It provides services related to the Session Layer, such as establishing and managing connections between networked applications.
#### Devices
H264, H323, RTP, NetBios

# Layer 6:  Presentation Layer
#### What is it?
This layer translates data into a format that the application layer can understand. It handles data encryption, compression, and conversion between different data formats.

#### Data Formatting:
Data is formatted by the computer to have compatibility between different devices, like ASCII or PNG. 

#### Encryption
**Encryption:**
Encryption is a process used to protect data by transforming it into an unreadable format, known as ciphertext, using a specific algorithm and an encryption key. Only those who have the correct decryption key can transform the ciphertext back into its original readable format, known as plaintext. Encryption ensures the confidentiality and security of data, both when it is stored (data at rest) and when it is transmitted over networks (data in transit).

**TLS:**

**SSL:**
#### Devices
TLS, SSL, xml, html, php, javascript, unicode, ascii, png, tif, mov,
# Layer 7: Application Layer
#### What is it?
The application layer provides network services directly to end-users and applications. It includes protocols like HTTP, FTP, SMTP, and DNS, which enable users to access network resources and services.

**Application Services:**
The various functionalities and operations provided by network applications to users and other applications. These services include protocols and software that directly interact with the end-user or provide backend functionalities for other applications.
1. **End-User Services**: These are the services that users directly interact with, such as web browsing (HTTP/HTTPS), email (SMTP, IMAP, POP3), file transfer (FTP), and remote access (SSH, Telnet).
2. **Middleware Services**: These services provide a layer of abstraction for application developers, enabling easier development and integration of complex applications. Examples include database access services (ODBC, JDBC) and message queuing services (MQTT).
3. **Directory Services**: These services provide directory and authentication services, such as LDAP (Lightweight Directory Access Protocol) and Active Directory, which are crucial for managing user identities and access controls in a network.
4. **Application Protocols**: Protocols like HTTP, FTP, SMTP, and DNS operate at Layer 7 and define how data is formatted, transmitted, and processed for specific applications.

**Service Advertisement:**
The process by which network services announce their presence and availability to other devices and applications on the network. This is essential for service discovery, allowing clients to locate and connect to services dynamically without needing pre-configured addresses or settings.
mDNS (Multicast DNS), UPnP (Universal Plug and Play), Apple Bonjour are examples
#### Devices
HTTP/HTTPS, SMTP, IMAP, POP3, FTP, SSH, Telnet, ODBC, JDBC, MQTT, LDAP, DNS

# Encapsulation and Decapsulation
When data moves from OSI Model Layer 7 -> 1, data is being encapsulated. If you move from OSI Model Layer 1->7, data is being decapsulated. 

**Encapsulation:**
The process of putting headers and trailers around data. Think of putting a letter (data) in an envelope (encapsulation). A bit of data is added (the source and destination address) but the information inside remains unchanged. The people at the post office and the mailmen don't need to know the contents, only the source and destination address (and stamp). They may even add further stamps to your letter to help with internal sorting. This is how data is transmitted across a network. 

**Decapsulation:**
Removing the letter from the envelope. Removing unnecessary information and exposing new information. 

**Protocol Data Unit (PDU):**
A single unit of information transmitted in a computer network. Referred to as L# PDU, where # is replaced with the OSI Model Layer