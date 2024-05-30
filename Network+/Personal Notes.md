 Computer Network: A **computer network** is a set of [computers](https://en.wikipedia.org/wiki/Computer "Computer") sharing resources located on or provided by [network nodes](https://en.wikipedia.org/wiki/Node_(networking) "Node (networking)").

Voice and computer network infrastructure used to be completely separate but now they have converged into a "mega-network".

Most networks and services target "5-9" 99.999% service availability resulting in about 5 minutes of downtime per year


Network Components:
**Client**: A device used by an end-user to access the network (laptop, phone, desktop)
**Server**: A dedicated device or software running on a dedicated device that provides resource to the rest of the network
**Hub**: Older technology that connects network devices together
**Wireless Access Point (WAP)** : A device that allows wireless devices to connect into a wired network
**Switch**: A device that connects network devices together providing more security and efficiency than a hub ("next generation" or "smart" hub)
**Router**: Connects two different networks together and forwards traffic to and from a network
**Media**: Connects two devices or a device to a switch port (copper cable, fibre optic, radio waves)
**Wide Area Network (WAN) Link**: Physically connects two geographically dispersed networks, connects an internal network to an external network

Network Resources: 
	Client Server Model:
		Uses a dedicated centralized server to provide access to files, scanners, printers, and other resources
		Easier to manage and scale
		Higher cost
		Requires dedicated resources
	Peer-To-Peer Model
		Peers share resources (files/printers) directly with others
		Harder to manage
		Scales very poorly
		Lower cost
		No dedicated resources

Network Geography:
	**Personal Area Network (PAN)**: Smallest type of wired or wireless network and covers the least amount of area. (Bluetooth, USB)
	**Local Area Network (LAN)**: Connects components within a limited distance, up to a few hundred feet. Typically Ethernet (IEEE 802.3) or Wi-Fi (IEEE 802.11). Typically in the scope of a small office or home office (SOHO) or a classroom.
	**Campus Area Network (CAN)**: Connects LANs that are building-centric across a university, industrial park, or business park. 
	**Metropolitan Area Network (MAN):** Connects scattered locations across a city or metro area, typically covers up to 25 miles. 
	 **Wide Area Network (WAN)**: Connects geographically disparate internal networks, typically connects globally (the "internet"). Consists of leased lines or Virtual Private Networks (VPNs).
	
![](panlanmanwan.jpg)




Logical Network Topology:
	**Bus Topology**:  In a bus topology, all devices are connected to a single central cable called the bus. Simple. Low cost. Prone to failure as there is one large single point of failure (SPF). Each device taps into the main cable, or "backbone", using either a vampire tap or a T-connector. 
	![](Bus+Topology-2021474318.png)
	**Ring Topology:** Uses a cable running in a circular loop where each device connects to the "ring" or "loop", but data travels in a single direction . It's relatively easy to install and can provide high-speed performance. If one device or connection fails, it can disrupt the entire network.
		**Token Ring**: Ring topology that uses an electronic token to prevent collisions when communication on the network. Like a "talking stick" from elementary school.
		**Fiber Distributed Data Interface (FDDI) Ring Topology**: Uses two counter-rotating rings for redundancy. **The only type of modern ring topology.** 
		**RING = REDUNDANCY ON THE EXAM**
		![](Dual-Ring-Topology-2856716358.jpg)
	**Star Topology**: Most popular physical LAN topology where devices connect to a single point. In a star topology, each device on the network is connected to a central hub or switch. All data passes through the central hub, which helps in managing and controlling the network traffic. It's easy to add or remove devices without disrupting the rest of the network. However, if the central hub fails, the entire network can be affected.	![](Star-Topology-2234151453.jpg)
		**Hub-and-Spoke Topology**: Similar to Star but with WAN links instead of LAN connections. Used for for connecting multiple sites.
		![](network-hub-spokes-cluster-1136750162.png)
	**Full-Mesh Topology**: Optimal routing is always available as every node connects to every other node This redundancy ensures that if one connection fails, data can still be routed through alternate paths. It's highly reliable and fault-tolerant. However, it's complex to set up.
	Hybrid-Mesh Topology: Hybrid of the full-mesh and the hub-and-spoke topologies. Provides optimal routes between some sites. Must consider network traffic patterns. 
	![](Fully-connected-mesh-topology-39357025.png)
![](17352a0c2a09a6bd43570cc107315cdf--types-of-computer-1412565952.jpg)
	Wireless  Network Topology:
		**Infrastructure Mode**: uses a wireless access point as a centralized point and supports wireless security controls.
		**Ad Hoc Mode**: Decentralized wireless network which creates P2P connections and does not require a router or access point.
		**Wireless Mesh Topology**: Interconnection of different types of nodes, devices, or radios. Creates redundant and reliable connections.

**Internet of Things (IoT):**
  Typically on: 802.11, Bluetooth, Radio-frequency Identification (RFID), Near-Field Communication (NFC), Infrared (IR), Z-Wave, ANT+
  - Bluetooth:
    - Used for short-range wireless communication between devices such as smartphones, tablets, laptops, and peripherals like headphones, speakers, and smartwatches.
    - Can range from 1 - 100m
- Radio-frequency Identification (RFID):
    - Utilized for identifying objects and tracking assets through radio waves, commonly seen in inventory management, access control systems, and contactless payment cards.
    - Can range from .1-20m
- Near-Field Communication (NFC):
    - Enables short-range communication between compatible devices for tasks like contactless payments, data transfer, and smart card functionality. 
    - Typically about .04-.10m. 
- Infrared (IR):
    - Primarily used for remote controls, transmitting data over short distances without requiring a direct line of sight, common in consumer electronics like TVs, DVD players, and air conditioners.
    - Typically about 1-5m.
- Z-Wave:
    - A wireless communication protocol designed for home automation and IoT devices, offering low-power consumption and secure communication for smart home applications like lighting, security systems, and energy management.
    - Typically about 30m+
- ANT+:
    - Specialized wireless protocol optimized for low-power, low-cost sensor networks in sports, fitness, and health monitoring devices, allowing interoperability between different manufacturers' products.
    - Typically about 30m+


