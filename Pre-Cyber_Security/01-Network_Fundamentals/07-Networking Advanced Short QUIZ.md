>[!Question] 00
> You have network 10.10.0.0/21. How many usable host IPs are in this subnet?

- [ ] 2062

- [ ] 2048

- [ ] 2030

- [x] 2046
>[!Reason]
>21 - 32
> = 11
> 11^2
> = 2048
> 2 - 2048 
> (network + broadcast) is the value of 2
> = 2046

---
>[!Question] 01
> ARP is best described as:

- [ ] A Layer 3 protocol that encapsulates packets into frames

- [x] A Layer 2 protocol that maps IP > MAC using broadcasts
>[!Reason] **ARP** (Address Resolution Protocol) is responsible for resolving a known **IP address** (Layer 3) to a physical **MAC address** (Layer 2) within a local network. It achieves this by sending a **broadcast** request to all devices on the LAN asking "Who has this IP?", and the device with that IP replies with its MAC address.

- [ ] A Layer 4 protocol used for port resolution

---
>[!Question] 02
> The OSI Presentation layer maps exactly to a single distinct layer in the TCP/IP model

- [ ] صحيح

- [x] خطأ
>[!Reason]
> The **TCP/IP model** is more condensed than the OSI model. It combines the top three layers of the OSI model (**Application, Presentation, and Session**) into a single, comprehensive layer known as the **Application Layer**.
>
>Therefore, the OSI Presentation layer does not map to a distinct layer in TCP/IP; instead, its functions (such as data formatting, encryption, and compression) are absorbed into the TCP/IP Application layer.

---
>[!Question] 03
> Which statement is correct?

- [ ] A frame is a Network layer unit; a packet is a Data Link layer unit

- [ ] A packet contains headers for L2 encapsulation; a frame contains TCP segments

- [x] A packet is a Layer-3 unit (IP); a frame is a Layer-2 unit (Ethernet)
>[!Reason]
> In networking, data is encapsulated into different units (PDUs) at each layer:
> 
> - **Layer 3 (Network Layer):** The unit is called a **Packet**. This is where IP addressing (Source/Destination IP) is added.
> 
> - **Layer 2 (Data Link Layer):** The packet is then wrapped inside a **Frame**. This is where MAC addressing (Source/Destination MAC) and error checking are added to traverse the physical medium (like Ethernet).

- [ ] Packet and frame are interchangeable terms for wireless networks only

---
>[!Question] 04
> Which TCP flags are necessarily set in the first packet

- [x] SYN only
>[!Reason]
>The **TCP 3-way handshake** begins with the client initiating a connection.
>
> 1. **First Packet (SYN):** The client sends a packet with only the **SYN** (Synchronize) flag set to establish the initial sequence number.
>
> 2. **Why not ACK?** The **ACK** flag is not set because there is no received data from the server to acknowledge yet. The server will respond with **SYN-ACK** in the second step.

- [ ] SYN + ACK

- [ ] ACK only

---
>[!Question] 05
> UDP provides sequence numbers and retransmission like TCP, but only if configured on the application layer

- [ ] صحيح

- [x] خطأ
>[!Reason]
>UDP itself is connectionless and lacks sequence numbers/retransmissions, applications must implement reliability if needed

---
>[!Question] 06
> Which of the following is the correct pair of protocol and default port?

- [ ] HTTPS: TCP 80

- [x] DNS: UDP 53 (also can use TCP 53)

- [x] SMTP: TCP 25

- [x] SSH: TCP 22

---
>[!Question] 07
> Order DORA: which is correct?

- [ ] Offer, Discover, Request, Acknowledge

- [x] Discover, Offer, Request, Acknowledge
>[!Reason]
>The **DORA** process describes the four steps of **DHCP** (Dynamic Host Configuration Protocol) IP assignment:
>
>1. **Discover:** The client broadcasts a message looking for a DHCP server.
> 
> 2. **Offer:** The DHCP server replies with an available IP address.
>
>3. **Request:** The client asks to lease that specific IP address.
>
>4. **Acknowledge:** The server confirms the lease and finalizes the configuration.

- [ ] Discover, Request, Offer, Acknowledge

- [ ] Request, Discover, Offer, Acknowledge

---
>[!Question] 08
> Given MAC AC:1F:6B:9A:BC:02, which portion is the OUI/vendor assignment?

- [x] AC:1F:6B
>[!Reason]
>A **MAC address** is a 48-bit (6-byte) identifier. It is split into two equal parts:
>
> 1. **First 24 bits (3 bytes):** This is the **Organizationally Unique Identifier (OUI)**, which identifies the manufacturer (vendor). In this case, `AC:1F:6B`.
>
> 2. **Last 24 bits (3 bytes):** This is the **Network Interface Controller (NIC) Specific**, which is unique to the specific device. In this case, `9A:BC:02`.

- [ ] 9A:BC:02

- [ ] AC:1F

- [ ] 9A

---
>[!Question] 09
> TLS typically operates to secure which of the following OSI layers primarily (choose the best answer)?

- [ ] Layer 2 (Data Link)

- [ ] Layer 7 (Application) only

- [x] Layer 6 (Presentation) and interacts with Layer 4 (Transport)
>[!Reason]
>TLS is usually considered Presentation layer functionality (encryption) but is tightly bound to Transport level sockets (TCP)

- [ ] Layer 1 (Physical)

---
>[!Question] 10
> Which OSI layers are collapsed into the TCP/IP “Application” layer?

- [ ] Application, Presentation, Transport

- [x] Application, Presentation, Session
>[!Reason]
>The **TCP/IP model** simplifies the 7-layer **OSI model** by combining the top three layers (**Layer 5, 6, and 7**) into a single layer called the **Application Layer**.
>- **Application (Layer 7):** User interface and network services.
>
>- **Presentation (Layer 6):** Data formatting, encryption, and compression.
>
>- **Session (Layer 5):** Dialog control and synchronization.
>
> In TCP/IP, all these functions are handled by the application protocols (like HTTP, SMTP, FTP) directly.

- [ ] Data Link and Network

- [ ] Physical and Data Link

---
>[!Question] 11
> ICMP echo replies are sent from the destination system only if that destination has no firewall blocking ICMP, firewalls may drop or rate-limit ICMP responses

- [x] صحيح
>[!Reason]
>Firewalls/hosts can block or limit ICMP echo requests/replies

- [ ] خطأ

---
>[!Question] 12
> Which header field exists in TCP but not in UDP?

- [ ] Source Port

- [ ] Destination Port

- [x] Sequence Number
>[!Reason]
>UDP is stateless, so it doesn't use sequence number

- [ ] Checksum

---
>[!Question] 13
> How many total ports are available?

- [x] 65535
>[!Reason]
>TCP and UDP use a **16-bit** field to define port numbers in their packet headers.
>
>- **Math:** $2^{16} = 65,536$.
>
>- **Range:** The ports are numbered from **0 to 65,535**.
>
>While the total _count_ including port 0 is technically 65,536, **65,535** is the highest usable port number and the correct choice among the options.

- [ ] 65534

- [ ] 65533

- [ ] 65531

---
>[!Question] 14
> Scenario: Your LAN is suffering ARP spoofing/poisoning attacks from a malicious host. Which of the following are valid mitigations? (More than one option could help. pick the BEST single option)

- [ ] Configure static ARP entries on every critical host

- [ ] Encrypt all traffic with IPsec between endpoints

- [x] Enable DHCP Snooping and Dynamic ARP Inspection on the switches
>[!Reason]
This is the most effective and scalable defense mechanism enforced by network switches.
>
>1. **DHCP Snooping:** Builds a trusted database (Binding Table) that maps legitimate IP addresses to MAC addresses and switch ports by observing DHCP traffic.
>
>2. **Dynamic ARP Inspection (DAI):** Uses this database to validate every ARP packet. If a malicious host sends a spoofed ARP reply (claiming an IP it doesn't own), the switch detects the mismatch against the trusted database and **drops the packet**, preventing the poisoning.
>
>
>_Static ARP entries are unmanageable at scale, and blocking ARP entirely breaks network connectivity._

- [ ] Block ARP packets at the router

---
