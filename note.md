CCNA 200-301
1. What is a network
  - digital telecommunications network
  - for us to share resources (like a printer, or a file) between nodes (computing devices) 
  - in network, we have special devices as nodes: hubs, switches, routers and firewalls
  - Shared using a `datalink`
    - twisted pair or fibre optic cable
    - microwave
    - wi-fi
    - ...

2. What is a network
  - in older days, we use Ethernet cabling, now we have (mostly) Wi-Fi
  - smallest network is between 2 clients (nodes, or computers)
  - UTP - Unshielded Twisted Pair Copper Cable (Ethernet Cable, a.k.a RJ45 Connector)
  - [All ethernet cables ever built](./all_ethernet_cables.png)
  - [RJ45 goes inside Cat 5e cabling](./cat_5e_cabling.png)
  - MAC address - Media Access Control Address
    - A unique identifier assigned to a _network interface controller_ for use as a network address in communications within a network segment
      - This is commin in most IEEE 802 networking technologies, including Ethernet, Wi-Fi and Bluetooth
      - Its _inside_ the network interface card, if you have a USB Wi-Fi dongle, then it's inside that. A bluetooh headphone have a MAC. Every bluetooth capable devices have a MAC address.
  - Modulation is the process of varying one or more properties of a periodic waveform, called the _carrier signal_ with a modulating signal that typically contains information to be transmitted
      - when we share file via bluetooth for e.g., the sender modulates the file content before sending it to the receiver which then de-modulates it
      - most radio systems in 20th century used frequency modulation (FM) or amplitude modulation (AM) for radio broadcast

3. What is a network
  - 10base5 (thick net)
  - 10base2 (thin net - coz much thinner than 10base 5)
  - both uses bus topology, hard to work with
  - today we use UTP or [Fiber cables](./Fiber%20cables.png)

4. Server and client
  - Server provides functionality to client in a server-client model
  - A client accesses the service provided by a server. Typicially the server is a different computing device across a network.
  - Server will be listening on different ports for different protocols
  - What is a protocol? A set of rules used for communication between devices.

5. Cisco Packet Tracer
  - Able to simulate logically the topologies of networking
  - We can't use normal `Ethernet Cable` when connecting from client to server
  - We should use `Crossover Ethernet Cable` where the Pins are crossed to each otNher [Crossover Ethernet Cable](./crossover-ethernet-cable.png)
  - DHCP, typically in networking, the (DHCP) server, usually the home router, will be allocating IP addresses to PCs using DHCP (Dynamic Host Configuration Protocol)
  - The DHCP is a network management protocl used on Internet Protocol networks whereby a DHCP server dynamically assigns an IP address and other netowrk configuration parameter to each device on a entwork so they can communicate with other IP networks

6. Network Devices
  - for early cables (like 10base5), the signal would attenuate from one end of the cable until the other
  - Attenuation refers to the reduction in the strength or intensity of a signal.The longer the distance the less strong the signal.
  ### 6.1 Therefore, Repeaters.
    - A repeater is an electronic device that receives a signal and re-transmits it. (also amplifies it)
    - Repeaters are used to extend transmissions so that the signal can cover longer distances or be received on the other side of an obstruction
    - A HUB, is a MULTI-port repeater
      - Usually can accomodate different cable types together, 10base5 and UTP 
      - A WiFi network is essentially a HUB in the air (sharing the air-waves)
    - It (has no intelligent) doesn't understand the signal, just amplifies and repeats it over all the ports
    - Layer 1 devices. Dumb devices.
  ### 6.2 Switches
    - A switch has intelligence (big difference from a HUB)
      - Works on Layer 2 (in OSI - Open System Interconnection model, aka TCP/IP model). Use Ethernet Frame.
      - Has a MAC address table
      - Has the ability to read and only forward Ethernet frames out of the correct port
      - Learns MAC addresses much more quickly (compared to a Bridge) by using hardware ASICs (application Specific Integrated Circuits)
      - Used to sending traffic within a LAN (Local Area Network)
      - For e.g. Cisco 3560 CX switch, Cisco 2960 switch
  ### 6.3 Bridges
    - Software to learn MAC addresses (to compensate on HUB's shortcoming)
    - Intermediate to HUB
  ### 6.4 Routers
    - Layer 3 devices (supports IP)
    - Allow routing from one IP network to another
    - In some cases, a router could route from one physical media to another physcial media
      - like from VoIP to Analog phones
    - Allow us to go from Ethernet LAN to WAN (Wide Area Network, i.e. Internet)
      - A WAN is a telecommunications network that extends over a large geographical area for primary purpose of computer networking
    - For e.g. Cisco Integrated Service Router 4321
  ### 6.5 Firewall
    - Router often has built in firewall, but there's also dedicated hardware firewall
    - Use Firewall Rules
      - Can specify what is Outside and Inside interface
    - For e.g. Cisco ASA 5505
    - Can be used [in front](./firewall-in-front.png) or [behind the router](./firewall-behind.png)
    - Usually used behind router, because firewall only supports ethernet while router supports other technology like ADSL (Asymmetrical digital subscriber line - the phone line) or cable
    - Newer Next Generation Firewall
      ### 2 types of Next Generation Firewall: IDS and IPS
        - IDS - Intrusion Detection System
          - Sits out of band of network traffic
          - Warns if there's malicious activiy detected
        - IPS - Intrusion Prevention System
          - Sits in line with the network traffic (traffic is going thru IPS)
          - Block malicious activity
  ### 6.6 Wireless LAN Controller (WLC)
    - Used to manage access points
    - Only make sense if there are mulitple access points
    - For e.g. WLC 2504
  ### 6.7 Access Points
    - Used to create a wireless network within a wired environment
    - Can be Lightweight or Autonomous
      - Lightweight Access Points can only be managed by WLC
      - Autonomous Acess Points can be deployed alone

7. OSI Model
  - [7 layers](./OSI-7-layers.png)
    - All People Sleeping Through Networking Don't Pass 
  - [TCP/IP 5 layers](./TCP-IP-5-layers.png)
    - Currently, CCNA teaches the TCP/IP 5 layers model (hybrid model of OSI + TCP/IP) 
      - Original TCP/IP model only 4 layers, with a Link layer for Data Link + Physical
    - These models (aka protocol stack) serves as a guideline, in reality, there could be a deviation of implementation
    - As networking engineer, we concentrate on the lower 4 layers: Transport, Network, Data Link and Physical
    - For CCNA, we concentrate on TCP/IP _hybrid_ 5 layers model
      - We _refer_ the TOP layer as Layer 7, because it originates from the OSI model

8. TCP/IP Model
  - [TCP/IP 5 layers + protocols](./TCP-IP-5-layers-protocols.png)
  - Layer 1 - Hub - Physical, Dumb
  - Layer 2 - Switch/Bridge - knows MAC address
  - Layer 3 - Router (or Layer 3 switches) - Knows IP
  - Layer 4 - Transmission Control Protocol or User Datagram Protocol - TCP or UDP
  - Layer 7 - Applications
  - What is a Protocol?
    - In telecommunication, a communiation protocol is a system of rules that allow two or more entities of a comm. system transmit information via any kind of variation of a physical quantity
    - The protocol defines the rules, syntax, semantics and synchronization of comm. and possible error recovery methods.
  - [Data Terms](./TCP-IP-data-terms.png)
    - Layer 1 - Bits, if there's _light_ or _electricity_, its 1, else its zero
      - Light (fibre), electricity (copper cable)

9. How network works?
  - PDU (Protocol Data Unit) formats - breakdown of the information fields at different layers
    - Layer 2 (Ethernet)'s `type` field dictates which protocol stack to use at Layer 3 (to determine how the payload is processed)
      - 0x806 => ARP
      - 0x0800 => IPv4
        - [EtherType](https://en.wikipedia.org/wiki/EtherType)
        - [Also](https://www.iana.org/assignments/ieee-802-numbers/ieee-802-numbers.xhtml)
          - But here says its assigned by IEEE, instead of IANA
    - Layer 3 (IP)'s `PRO` (protocol) field dictates which protocol stack to use at Layer 4
      - 0x06 => TCP
        - check for Layer 3 [protocol numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
    - Layer 4 (TCP)'s `DESTINATION PORT` field decides which protocol to use at Layer 7
      - 80 => HTTP
        - [Port Numbers](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml?&page=2)
  - ARP (Address resolution protocol) - layer 2.5, in between Layer 2 and 3
  - TCP - before communication takes place (before HTTP packet is sent), they do 3-way handshake (sequence number, how much data they can send etc) 
  - Service Port Numbers
    - A server running multiple services, listening at different ports for different services
      - Note from the [Port Numbers] link, 
        ```
        Port numbers are assigned in various ways, based on three ranges: System
        Ports (0-1023), User Ports (1024-49151), and the Dynamic and/or Private
        Ports (49152-65535)
        ```
      - the SRC port when sending a HTTP request (a well known port aka port 80), uses the range from User Ports
        - that's why we see Layer 4 info, for e.g. FROM client -> server SRC: 1205 to DEST: 80
          - the reply is swapped around, server -> client SRC: 80 to DEST: 1205
      - Dynamic Ports, also called Ephemeral Port Numbers (like those used by K8s Service's Node Port)
        - Ephemeral port is short lived transport portocol port for Internet Protocol comm. 
        - Ephemeral ports are allocated automatically from a pre-defined range by the IP stack software.
        - Typically used as "port assignments" for the **client end** of a client-server comm. to a particular port (usually a well-known port) on a server
        - The dynamic range may differs between OS
      - Just knowing the well known port numbers is suffice

  ### 9.1 Network Flow:
    - When a client first send a request 
      - First send an ARP to discover the target MAC address
      - The target server with the correct IP will respond with another ARP with the correct MAC address
        - Layer 2: 
        ```
        Ethernet II Header <client_mac_addr> >> FFFF.FFFF.FFFF
        ARP Packet Src. IP: <client_ip>, Dest. IP: <target_ip>
        ```
        Target mac is unknown, that's why the `FFFF.FFFF.FFFF`
        In outbound PDU, Target MAC is 0000.0000.0000
    - When the client received the ARP reply, it will encapsulate the PDU (with the Dest Addr) into an Ethernet Frame
      and set type to 0x0800 (IPv4) and resends it (to start the 3 way handshake) 
        -  TCP info src and desc port at layer 4 is in the outbound PDU details
        - [First TCP](./TCP-1.png)
    - When the Server
        - [First TCP reply](./TCP-1-reply.png)

  ### 9.2 Network flow after ARP 
  [TCP flags](https://www.howtouselinux.com/post/tcp-flags)
  ```
  Flag 	Decimal Value
  URG 	32
  ACK 	16
  PSH 	8
  RST 	4
  SYN 	2
  FIN 	1
  ```
  #### 3 way handshake
  client -> SYN     server - for client to fix the port for communication with server
  client <- SYN+ACK server
  client -> ACK     server
  
  #### At server (dest):
    1. <- TCP SYN (look at the flags)
    ``` 
      The device receives a TCP SYN segment on server port 80.
      Received segment information: the sequence number 0, the ACK number 0, and the data length 24.
      TCP retrieves the MSS value (Maximum segment size - OS dependent) of 1460 bytes (OS M$ Windows's size) from the Maximum Segment Size Option in the TCP header.
      The connection request is accepted.
      The device sets the connection state (???) to SYN_RECEIVED
    ```
    2. -> TCP SYN+ACK
    ```
     TCP accepts a window size (???) up to 16384 bytes.
        (? does this means the receiving device - i.e. client can currently receive up till 16384 bytes without furuther acknowledgement)
     TCP adds Maximum Segment Size Option to the TCP SYN-ACK header with Maximum Segment Size equal to 1460 bytes.
     The device sends a TCP SYN+ACK segment.
     Sent segment information: the sequence number 0, the ACK number 1, and the data length 24.
    ```

  #### At client (source):
    1. <- TCP SYN+ACK 
    ```
     The device receives a TCP SYN+ACK segment on the connection to 10.1.1.100 on port 80.
     Received segment information: the sequence number 0, the ACK number 1, and the data length 24.
     The TCP segment has the expected peer sequence number.
     The TCP connection is successful.
     TCP retrieves the MSS value of 1460 bytes from the Maximum Segment Size Option in the TCP header.
     The device sets the connection state to ESTABLISHED.
    ```
    2. -> TCP ACK
    ```
     The device sends a TCP ACK segment.
     Sent segment information: the sequence number 1, the ACK number 1, and the data length 20.
    ```
    This is actually the end of the 3 way handshake
    3. -> TCP ACK+PSH (right after no.2)
    [TCP ACK+PSH](./TCP-ACK+PSH_sending_HTTP.png)
    ```
    Layer 4:
     Sent segment information: the sequence number 1, the ACK number 1, and the data length 99.
    Layer 7:
     The HTTP client sends a HTTP request to the server.
      - notice here is HTTP client, it could be _any_ Layer 7 protocol's client, FTP, Telnet etc..
    ```
    4. TCP ACK would be sent and received by server first, before TCP ACK+PSH with the HTTP request
    
  #### At server (dest):
    1. <- TCP PSH+ACK
    ```
      The device receives a TCP PUSH+ACK segment on the connection to 10.1.1.99 on port 1025.
      Received segment information: the sequence number 1, the ACK number 1, and the data length 99.
        (*data length here refers to the entire PDU, HTTP request payload + TCP header and any encapsulating headers)
      The TCP segment has the expected peer sequence number.
      TCP processes payload data.
      TCP reassembles all data segments and passes to the upper layer.
    ```
    L7: The server receives the HTTP request here
    2. -> TCP ACK+PSH
    ```
    Sent segment information: the sequence number 1, the ACK number 100 (*increase by 1 + 99, indicating that it has successfully received and acknowledged all 99 bytes of data up to sequence number 100), and the data length 519.
    ```
    L77: It would send the HTTP reply here

  #### Back at Client (source):
    1. <- TCP PSH+ACK
    ```
      The device receives a TCP PUSH+ACK segment on the connection to 10.1.1.100 on port 80.
      Received segment information: the sequence number 1, the ACK number 100, and the data length 519.
      The TCP segment has the expected peer sequence number.
      The TCP segment has the expected ACK number. The device pops the last sent segment from the buffer.
      TCP processes payload data.
      TCP reassembles all data segments and passes to the upper layer.
    ```
    L7: The HTTP client receives a HTTP reply from the server. It displays the page in the web browser.

    2. -> TCP FIN+ACK
    ```
      The device closes the TCP connection to 10.1.1.100 on port 80.
      The device sets the connection state to FIN_WAIT_1.
      The device sends a TCP FIN+ACK segment.
      Sent segment information: the sequence number 100, the ACK number 520, and the data length 20.
        (* the sequence number 100 indicates to the server that the client has received and acknowledged all bytes up to sequence number 100)
        (* this is also the next byte that the server is expecting to received, since previous segment sent up till byte 99)
        (* in some sense, this sequence number is also derived from the ACK number sent by the server previously)
    ```

  #### At server:
    1. <- TCP FIN+ACK
    ```
     The device receives a TCP FIN+ACK segment on the connection to 10.1.1.99 on port 1025.
     Received segment information: the sequence number 100, the ACK number 520, and the data length 20.
     The TCP segment has the expected peer sequence number.
     The TCP connection was disconnected.
     The device sets the connection state to CLOSE_WAIT.
     The device sets the connection state to LAST_ACK.
     The TCP segment has the expected ACK number. The device pops the last sent segment from the buffer.
    ```
    2. -> TCP FIN+ACK
    ```
     The device sends a TCP FIN+ACK segment.
     Sent segment information: the sequence number 520, the ACK number 101 (acknowledge received up till byte 101?) , and the data length 20.
    ```

10. SMTP (port 25)


11. POP3 (port 110)


12. TELNET
  - Developed in 1969, is a protocol that provides a command line interface for communication with a remote device or server
  - No longer used, in favor of SSH
  - Serious security concerns when using Telnet over an open network such as the Internet

13. IPv4 address
  - An address used to uniquely identify a device on an IP network
  - for e.g. 192.168.0.1
  - Consists of 4 octets (4 sets binary of 8 bits = total 32 bits)
    - so 192.168.0.1 is 1100 0000 . 1010 1000 . 0000 0000 . 0000 0001
  - Devices such as routers and firewalls use binary to determinate whats permitted or denied

14. HexaDemical
  - MAC and IPv6
  - for e.g. 0004.9ADD.C016 or 00-04-9A-DD-C0-16
    - A hex value is 4 binary bits
    - So MAC address is a 4 * 12 = 48 bits number
  - In windows, `ipconfig /all` to show MAC addresses
  - [MAC addresses](./MAC-addresses.png)
    - First half is a vendor's OUI - organization unique identifier (6 hexadecimal values)
    - Second half is a unique number (another 6 hexadecimal values)
  - Once the device has learnt (via ping command for e.g.) the MAC address of another device
    - we can do `arp -a` (in Windows) to list out all the addresses
    - the other device (which get pinged) would also have saved the MAC address in the arp list
    - the switch will save the the addresses in the MAC table 
    ```
    Switch>en
    Switch#show ma
    Switch#show mac 
    Switch#show mac address-table 
              Mac Address Table
    -------------------------------------------
    
    Vlan    Mac Address       Type        Ports
    ----    -----------       --------    -----
    
       1    0001.9797.2382    DYNAMIC     Gig1/0/2
       1    0090.2b63.37ec    DYNAMIC     Gig1/0/1
   ```
  
15. Hex <-> Binary conversion

Decimal   Binary   Hex   Hex to Decimal
128       10000000 80    (8x16 + 0x1)
255       11111111 FF    (15x16 + 15x1)
224       11100000 E0    (14x16 + 0x1)
240       11110000 F0    (15x16 + 0x1)

16. 255.255.255.255 is a _broadcast_ address in IPv4 
  - means *all* devices in the network

  255.255.255.255
  11111111 11111111 11111111 11111111
  FF FF FF FF FF FF
  - used by _linked local broadcast_ 
  [ICPM first broadcast](./ICMP-broadcast.png)
    - notice how the Dest MAC is FFFF.FFFF.FFFF, and the Dest IP is 255.255.255.255

17. Connecting to Cisco Switch

i. Rollover Cable/ DB9 to RJ45 rollover cable
[rollover cable](./rollover-cable.png)
Pin 1 connect to Pin 8... all the way to 8 to 1
Do NOT connect the rollover (console) cable directly into the ethernet port of the laptop, it will blow the console port (on the router/switches)

This is an _out-of-band_ connection, TCP/IP connection is not going through the Rollover Cable, it is actually a _serial_ port. We would need DB9 to RJ45 connector to connect to the serial port of the laptop.
So, RJ45 to the router/switch, DB9 to the laptop serial port.

ii. USB to Serial converter + DB9 to RJ45 cable

iii. USB only

User EXEC (aka user mode)
Prompt: Switch >

Privileged EXEC (aka enable mode)
Prompt: Switch #





Glossary:
ICMP - Internet Control Message Protocol
STP - Spanning Tree Protocol
SMTP - Simple Mail Transfer Protocol -> to send email
POP3 - older Protocol -> to receive email
DHCP - Dynamic Host Configuration Protocol -> A server allocates an IP address to your device


Question:
1. How does sequence + acknowledgement works?

seq number, ACK number, data length

      ---- 3 way handshake start ----
      0   0   24 client -> TCP SYN (port 25)

      0   0   24 server <- TCP SYN, connection state SYN_RECEIVED 
      0   1   24 server -> TCP SYN+ACK

      0   1   24 server <- TCP SYN+ACK
      1   1   20 client -> TCP ACK

      1   1   20 server <- TCP ACK, connection state ESTABLISHED

      ---- 3 way handshake complete ----

      ---- sending data start ----
  
      1   1   78 client -> TCP PUSH+ACK (with SMTP content)

      1   1   78 server <- TCP PUSH+ACK
      1  79   24 server -> TCP PUSH+ACK (reply for above)
        (does reply consist of the sent SMTP data as well??)

      ---- sending data complete ----

      ---- TCP close process start ----
      79  25  20 client -> TCP FIN_ACk, connection state FIN_WAIT_1 (means waiting for server to close?) 

      79  25  20 server <-TCP FIN_ACK, connection state CLOSE_WAIT, LAST_ACK
      25  80  20 server -> TCP FIN_ACK

      25  80  20 client <- TCP FIN_ACK, connection state CLOSING
      80  25  20 client -> TCP ACK

      80  25  20 server <- TCP ACK, connection state CLOSED

      ---- TCP close process end ----

Observations: 
1. If a client or server increase the ACK by 1, means they expect the counterparty to send the next sequence as such number
2. If a client or server did not increaset the ACK, means they do not expect to receive any more data from counter party
3. We could see this play out in the 3-way handshake as well as the TCP close process, where the client ACK with same Seq number as received, the server then stop responding (though the connection state, in 3-way its CONNECTION ESTABLISH while in close process its CLOSED)
4. For 3-way handshake and close process, the data length does not matter and does not need to be ACK. This works differently when TCP is sending data, where the previous data length needs to be included in ACK


2. How does window size works?