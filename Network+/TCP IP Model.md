# Transmission Control Protocol/Internet Protocol (TCP/IP)

| Layer # | OSI Layer Name | TCP/IP Layer Name | Description                                                                                                | Tech Used                                        |
| ------- | -------------- | ----------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Layer 7 | Application    | Application       | Dictates how programs are going to interface with the transport layer by conduction session management.    | HTTP, Telnet, FTP, SSH, SNMP, DNS, SMTP, SSL/TLS |
| Layer 6 | Presentation   | Application       |                                                                                                            |                                                  |
| Layer 5 | Session        | Application       |                                                                                                            |                                                  |
| Layer 4 | Transport      | Transport         | Defines the level of service and the status of the connection being used by TCP, UDP, or RTP               | TCP, UDP,  RTP                                   |
| Layer 3 | Network        | Internet          | Where data is taken and packaged into IP datagrams                                                         | IP, ICMP, ARP, Reverse ARP                       |
| Layer 2 | Data Link      | Network Interface | Describes how to transmit bits across a network and determines how the network medium is going to be used. |                                                  |
| Layer 1 | Physical       | Network Interface |                                                                                                            |                                                  |


# TCP (OSI Layer 4)

#### TCP Flags
- **SYN (Synchronization):** Used to synchronize connection during the three-way handshake
- **ACK (Acknowledgment):** Used during the three-way handshake but also used to acknowledge the successful receipt of packets 
- **FIN (Finished):** Used to tear down the virtual connections created using the three-way handshake and the SYN flag
- **RST (Reset):** Used when a client or server receives a packet that it was not expecting during the current connection 
- **PSH (Push):** Used to ensure data is given priority and is processed at the ending or receiving ends.
- **URG (Urgent):** Similar to PSH and identifies incoming data as urgent
#### TCP 3-Way Handshake:
1. **SYN (Synchronize)
    - **Initiation**: The client wants to establish a connection with the server. It starts by sending a TCP segment with the SYN (synchronize) flag set. This segment contains an initial sequence number (ISN), which is a random number that marks the beginning of the sequence of bytes the client will send.
    - **Purpose**: This step is used to initiate the connection and tell the server that the client intends to establish a session.
2. **SYN-ACK (Synchronize-Acknowledge):
    - **Response**: Upon receiving the SYN segment, the server responds with a TCP segment that has both the SYN and ACK (acknowledge) flags set. This segment contains the server’s own initial sequence number and acknowledges the client’s ISN by setting the acknowledgment number to the client’s ISN + 1.
    - **Purpose**: This step confirms receipt of the client’s SYN segment and synchronizes the server’s sequence number with the client.
3. **ACK (Acknowledge):
    - **Confirmation**: Finally, the client sends another TCP segment with the ACK flag set. This segment acknowledges the server’s SYN-ACK by setting the acknowledgment number to the server’s ISN + 1.
    - **Purpose**: This step completes the handshake process, confirming that both the client and server are synchronized and the connection is established.

![](Pasted%20image%2020240529155133.png)


#### TCP Header:
![](Pasted%20image%2020240318232841.png)






# UDP (OSI Layer 4)
#### UDP Header:
![](Pasted%20image%2020240318232911.png)

# IP (OSI Layer 3)
#### IP Header:
![](Pasted%20image%2020240318233029.png)




# Ethernet (OSI Layer 2)
#### Ethernet Header:
![](Pasted%20image%2020240318233113.png)

A frame being sent at layer 2 will also include a payload. In ethernet the minimum size is 42 bytes if VLANs are being used and 46 bytes if no VLAN is being used. 


 