lab 1
AIM 1: Introduction to the OSI Model. (What is the OSI Model?) 
The OSI Model is a seven-layer conceptual framework that describes how network protocols 
and devices interact to facilitate communication. It breaks down the complex process of 
network communication into smaller, more manageable functions, making it easier to 
understand, design, and troubleshoot network systems. 
Purpose of the OSI Model: 
Standardization: Provides a common reference point for developing network protocols and 
products, ensuring interoperability between different vendors' equipment. 
Modularity: Divides network communication into discrete layers, allowing developers to focus 
on specific functions without needing to understand the entire system. 
Troubleshooting: Helps isolate network problems to a specific layer, simplifying the diagnostic 
process. 
Education: Serves as a fundamental concept for teaching network principles and architecture. 
How Data Flows: 
When data is sent, it originates at the Application Layer (Layer 7) on the sender's device and 
moves down through the layers, with each layer adding its own header (and sometimes a trailer) 
to the data. This process is called encapsulation. At the Physical Layer (Layer 1), the data is 
converted into signals and transmitted over the physical medium. 
When data is received, it starts at the Physical Layer (Layer 1) on the receiver's device and 
moves up through the layers. Each layer strips off the header (and trailer) added by its 
corresponding layer on the sender's side, and passes the remaining data up. This process is 
called de-encapsulation. Finally, the original data is presented to the Application Layer (Layer 
7). 
(Figure Suggestion: A diagram showing the 7 layers stacked vertically, with arrows indicating 
data flow down from Layer 7 to Layer 1 on the sender side, and up from Layer 1 to Layer 7 on 
the receiver side. Also show "Encapsulation" happening downwards and "De-encapsulation" 
happening upwards.) 


Page 2: Layer 1 - Physical Layer 
Function: The Physical Layer is the lowest layer of the OSI model and deals with the physical 
connection between devices. It is responsible for the actual transmission and reception of raw 
unstructured bit streams over a physical medium. 
Key Responsibilities: 
Bit Stream Transmission: Converts digital data (0s and 1s) into electrical, optical, or radio 
signals suitable for the transmission medium. 
Physical Characteristics: Defines hardware specifications such as: 
Cabling: Types of cables (copper, fiber optic, etc.), connectors (RJ45, USB, etc.). 
Voltage Levels: Electrical signals and voltage specifications. 
Data Rates: The rate at which bits are transmitted (e.g., Mbps, Gbps). 
Transmission Mode: Simplex (one-way), half-duplex (two-way, one at a time), or full-duplex 
(two-way simultaneously). 
Topology: Physical arrangement of network devices (e.g., bus, star, ring, mesh). 
Bit Synchronization: Ensures that the sender and receiver clocks are synchronized to properly 
interpret the bit stream. 
Devices: Hubs, Repeaters, Network Interface Cards (NICs), Cabling (Ethernet, Fiber Optic), 
Modems (at the physical signaling level). 
Protocols/Standards: Ethernet (physical aspects like 10BASE-T, 100BASE-TX), USB, 
Bluetooth (physical layer), RS-232, DSL. 
PDU (Protocol Data Unit): Bits 
(Figure Suggestion: A diagram showing two computers connected by a cable, with "0s and 1s" 
being transmitted over the cable. Show physical components like NICs, cables, and 
connectors.) 


Page 3: Layer 2 - Data Link Layer 
Function: The Data Link Layer provides reliable node-to-node (or hop-to-hop) data transfer. It 
takes the raw bit stream from the Physical Layer and transforms it into "frames," adding error 
detection and physical addressing. This layer is often divided into two sublayers: Logical Link 
Control (LLC) and Media Access Control (MAC). 
Key Responsibilities: 
Framing: Divides the stream of bits received from the Physical Layer into manageable units 
called "frames." It adds a header and trailer to each frame to mark its beginning and end. 
Physical Addressing (MAC Addressing): Adds the source and destination MAC (Media Access 
Control) addresses to the frame header. MAC addresses are unique hardware identifiers for 
devices on a local network segment. 
Error Detection: Implements mechanisms (like Cyclic Redundancy Check - CRC) to detect 
errors that may occur during transmission over the physical medium. If an error is detected, the 
frame is usually discarded, and retransmission is typically handled by higher layers (though 
some MAC protocols do provide retransmission). 
Flow Control: Regulates the rate of data transmission between directly connected devices to 
prevent a fast sender from overwhelming a slower receiver. 
Media Access Control (MAC Sublayer): Determines how devices gain access to and share the 
physical transmission medium (e.g., CSMA/CD for Ethernet, CSMA/CA for Wi-Fi). It ensures 
that only one device transmits at a time to avoid collisions. 
Logical Link Control (LLC Sublayer): Provides services to the Network Layer, handling 
multiplexing (allowing multiple network layer protocols to share the same MAC), flow control, 
and error control. 
Devices: Switches, Bridges, NICs. 
Protocols/Standards: Ethernet (at the framing and MAC level), Wi-Fi (802.11), PPP (Point-to
Point Protocol), HDLC (High-Level Data Link Control), Frame Relay. 
PDU: Frames 
(Figure Suggestion: A diagram showing two computers connected via a switch. Illustrate 
frames with MAC addresses and FCS. Show the MAC and LLC sublayers within the Data Link 
Layer.) 


Page 4: Layer 3 - Network Layer 
Function: The Network Layer is responsible for logical addressing, routing, and determining 
the best path for data packets to travel across different networks (inter-network 
communication). It handles the movement of packets from source to destination, even if they 
are on different networks. 
Key Responsibilities: 
Logical Addressing (IP Addressing): Assigns unique logical addresses (e.g., IP addresses in 
TCP/IP) to devices, allowing them to be identified across an entire internetwork, not just a local 
segment. 
Routing: Determines the optimal path for data packets to travel from the source network to the 
destination network, often using routing tables and routing algorithms. Routers are key devices 
at this layer. 
Packet Forwarding: Moves packets from one network segment to another based on their logical 
destination address. 
Internetworking: Connects different network segments to form larger networks 
(internetworks). 
Congestion Control: Can participate in managing network congestion by dropping packets or 
signaling congestion. 
Devices: Routers, Layer 3 Switches. 
Protocols/Standards: IP (Internet Protocol - IPv4, IPv6), ICMP (Internet Control Message 
Protocol), ARP (Address Resolution Protocol), Routing Protocols (e.g., OSPF, EIGRP, BGP). 
PDU: Packets (sometimes called Datagrams) 
(Figure Suggestion: A diagram showing multiple interconnected networks (LANs) with routers 
connecting them. Illustrate packets moving between different networks using IP addresses, and 
show routing tables.) 



Page 5: Layer 4 - Transport Layer 
Function: The Transport Layer provides end-to-end communication between application 
processes running on different hosts. It ensures the reliable and transparent transfer of data 
from one application to another, providing services like segmentation, reassembly, flow 
control, and error recovery. 
Key Responsibilities: 
Segmentation and Reassembly: Breaks down large messages from the Session Layer into 
smaller units called "segments" for efficient transmission. At the receiver, it reassembles these 
segments into the original message. 
Service-Point Addressing (Port Addressing): Uses port numbers to identify specific 
applications or services running on a host. This allows multiple applications to share the same 
network connection simultaneously. 
Connection-Oriented Communication (TCP): Provides a reliable, ordered, and error-checked 
delivery of data. It establishes a virtual connection (handshake), ensures all segments arrive in 
order, and retransmits lost or corrupted segments. 
Connectionless Communication (UDP): Provides a fast, unreliable delivery without 
guarantees. It sends data without establishing a connection or ensuring delivery. Suitable for 
real-time applications where speed is critical (e.g., streaming). 
Flow Control (End-to-End): Manages the rate of data flow between the sending and receiving 
applications to prevent the receiver's buffer from overflowing. This is distinct from the Data 
Link Layer's hop-to-hop flow control. 
Error Control (End-to-End): Ensures that the data arrives at the destination application without 
errors. It uses acknowledgments and retransmissions for lost or corrupted segments. 
Devices: Gateways (can operate at this layer), Firewalls (can inspect transport layer headers). 
Protocols/Standards: TCP (Transmission Control Protocol), UDP (User Datagram Protocol), 
SCTP (Stream Control Transmission Protocol). 
PDU: Segments (for TCP), Datagrams (for UDP, though "packet" is also commonly used at 
Network Layer). 
(Figure Suggestion: A diagram showing two applications on different computers 
communicating. Illustrate segmentation of data into segments, port numbers, and the concept 
of reliable (TCP) vs. unreliable (UDP) delivery.) 



Page 6: Layer 5 - Session Layer 
Function: The Session Layer establishes, manages, and terminates communication sessions 
between applications on different devices. It controls the dialogues (conversations) between 
applications, ensuring orderly data exchange. 
Key Responsibilities: 
Session Establishment, Maintenance, and Termination: Coordinates the setup, ongoing 
management, and graceful teardown of communication sessions between two application 
processes. 
Dialog Control: Determines which application can send data and when. It can manage half
duplex (one-way at a time) or full-duplex (two-way simultaneously) communication. 
Synchronization and Checkpointing: Inserts checkpoints into the data stream. If a session fails, 
communication can resume from the last checkpoint rather than starting from the beginning, 
which is crucial for large file transfers or long-running processes. 
Token Management: For certain protocols, it can manage "tokens" to ensure only one side 
performs a critical operation at a time. 
Protocols/Standards: NetBIOS, RPC (Remote Procedure Call), Sockets (API related), some 
parts of SQL and NFS. 
PDU: Data (or Session Data Unit) 
(Figure Suggestion: A diagram showing two application windows on different computers (e.g., 
a video conferencing app). Illustrate the concept of a "session" being established, maintained, 
and terminated, with checkpoints for recovery.) 



Page 7: Layer 6 - Presentation Layer 
Function: The Presentation Layer is responsible for the syntax and semantics of the information 
exchanged between applications. It ensures that the data is in a format that the receiving 
application can understand, regardless of the format used by the sending application. It acts as 
a data translator. 
Key Responsibilities: 
Data Translation/Formatting: Converts data into a common format for transmission and then 
back into the application-specific format at the receiver. This includes character code 
translation (e.g., ASCII to EBCDIC), data type conversion. 
Encryption and Decryption: Handles the encryption of data for security during transmission 
and decryption upon reception. 
Data Compression and Decompression: Reduces the number of bits in the data stream to 
optimize network bandwidth and transmission speed. The receiving Presentation Layer 
decompresses the data. 
Protocols/Standards: JPEG, MPEG (for image and video formats), ASCII, EBCDIC, TLS/SSL 
(Transport Layer Security/Secure Sockets Layer - primarily at this layer, though often 
implemented with Transport Layer functions), XDR (eXternal Data Representation). 
PDU: Data (or Presentation Data Unit) 
(Figure Suggestion: A diagram showing a sending application with raw data, the Presentation 
Layer transforming/compressing/encrypting it, and then the receiving Presentation Layer 
reversing the process before passing to the application.) 



Page 8: Layer 7 - Application Layer & Conclusion 
Function: The Application Layer is the top layer of the OSI model and provides the interface 
between network services and end-user applications. It is closest to the end-user, enabling users 
to interact with network services. This layer does not include the applications themselves, but 
rather the protocols that applications use to communicate over the network. 
Key Responsibilities: 
Network Services to Applications: Provides services directly to software applications, allowing 
them to access network resources. 
User Interface: Acts as a window for application services to access the network and for 
displaying received information to the user. 
Resource Sharing: Facilitates file transfer, email, remote login, virtual terminals, and directory 
services. 
Data Identification: Identifies and establishes the availability of communication partners and 
synchronizes applications. 
Protocols/Standards: 
HTTP/HTTPS: (Hypertext Transfer Protocol/Secure) for web Browse. 
FTP: (File Transfer Protocol) for file transfer. 
SMTP/POP3/IMAP: (Simple Mail Transfer Protocol, Post Office Protocol version 3, Internet 
Message Access Protocol) for email. 
DNS: (Domain Name System) for resolving domain names to IP addresses. 
Telnet/SSH: (Teletype Network, Secure Shell) for remote terminal access. 
SNMP: (Simple Network Management Protocol) for network management. 
PDU: Data (or Application Data Unit) 
Conclusion: The OSI Model's Importance 
While the OSI model is a theoretical framework and not perfectly mapped by real-world 
protocols (like the TCP/IP suite, which combines some layers), it remains invaluable for: 
Conceptual Understanding: Providing a clear, structured way to understand the complex 
process of network communication. 
Troubleshooting: Helping network administrators and engineers isolate problems to specific 
layers. For example, if you can ping a device (Network Layer) but can't access a web page 
(Application Layer), the problem likely lies in the upper layers (Session, Presentation, or 
Application). 
Protocol Development: Offering a guideline for developing new network protocols and 
services, ensuring they fit within the broader networking ecosystem. 
