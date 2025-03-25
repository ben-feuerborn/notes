> **WHAT IS A NETWORK**
> A network is a collection of interconnected devices that communicate and share resources using wired or wireless connections. Networks can be small, like a home network, or large, like the internet.


# NETWORK ADDRESSING
**IP Address**
An *Internet Protocol* (IP) Address is a unique numerical label assigned to each device connected to a network. It allows devices to locate and communicate with each other over the internet. IP Addresses come in two version:
1. IPv4: 32-bit addresses (e.g. 192.168.50.206)
2. IPv6: 128-bit addresses (e.g. fe80::976c:33f6:1b79:8d39)

**MAC Address**
A *Media Access Control* (MAC) Address is a unique identifier assigned to a device's Network Interface Card (NIC). It consists of 48 bits, usually written as six pairs of hexadecimal numbers (e.g. f4:a4:75:e7:f6:0d). Unlike an IP Address, a MAC Address does not change.


## TYPES OF NETWORKS
**Local Area Network (LAN)**
A LAN is a network that connects devices within a small area, such as a home, office, or school. It typically uses Ethernet cables or WiFi to connect devices.

**Wide Area Network (WAN)**
A WAN covers a larger geographical area, connecting multiple *LANs*. The internet is the largest WAN, enabling global communication.


# KEY NETWORKING TERMS
## COMMUNICATION
**HOPS**
A hop is a point in a network path where data passes from one router to another before reaching its destination.

**PACKETS**
A packet is a small unit of data transmitted over a network. Each packet contains:
1. Source & Destination IP addresses
2. Payload (data being transmitted)
3. Error-checking information


## DEVICES
**SWITCHES**
A switch is a networking device that connects multiple devices within a LAN. It uses MAC addresses to forward data to the correct device.

**ROUTERS**
A router directs data packets between different networks. It connects a LAN to the internet and assigns IP addresses to devices.

**ACCESS POINTS (APs)**
An access point extends the wireless network, allowing devices to connect to a LAN via WiFi.


## COMPONENTS
**ENDPOINTS**
Endpoints are devices that communicate on a network, such as computers, smartphones, and IoT devices.

**HOSTS**
A host is any device with an IP address that can send or receive data over a network.


# 7 LAYERS OF THE INTERNET
The **OSI (Open Systems Interconnection) Model** describes how data travels across a network. The seven layers are:

1. **Physical Layer** - Deals with hardware connections, cables, and signal transmission.
2. **Data Link Layer** - Manages MAC addresses and data frames for direct device communication.    
3. **Network Layer** - Handles IP addressing and routing between networks.
4. **Transport Layer** - Ensures reliable data delivery using protocols like TCP and UDP.
5. **Session Layer** - Manages communication sessions between applications.
6. **Presentation Layer** - Formats, encrypts, and compresses data for proper interpretation.
7. **Application Layer** - Interfaces directly with user applications like web browsers and email clients.

[[03_osi_model]]