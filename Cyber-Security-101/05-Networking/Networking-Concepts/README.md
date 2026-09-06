# Networking Concepts

- **Path:** Cyber Security 101
- **Module:** Networking
- **Status:** ✅ Completed
- **Room Link:** [Networking Concepts on TryHackMe](https://tryhackme.com/room/networkingconcepts)

---

## What this room is about
This room covers core computer networking models and communication protocols:
* The 7-layer ISO OSI model vs. the 4-layer TCP/IP model.
* IPv4 addressing structure, CIDR notation, and private vs. public address spaces.
* Connectionless (UDP) vs. connection-oriented (TCP) transport mechanisms.
* Data encapsulation and the life of a network packet.
* Interacting directly with TCP services using Telnet.

---

## Key concepts & notes

### 1. The OSI 7-Layer Model
Remembered from bottom to top using *"Please Do Not Throw Spinach Pizza Away"*:
* **Layer 7 - Application:** Provides services directly to software (`HTTP`, `DNS`, `SSH`, `FTP`).
* **Layer 6 - Presentation:** Handles data formatting, encryption, and compression (`SSL/TLS`, `ASCII`, `JPEG`).
* **Layer 5 - Session:** Manages sessions and connections between apps (`RPC`, `NFS`).
* **Layer 4 - Transport:** Manages host-to-host delivery, ports, and reliability (`TCP`, `UDP`).
* **Layer 3 - Network:** Logical addressing and routing across different networks (`IP`, `ICMP`).
* **Layer 2 - Data Link:** Node-to-node transfer on the same local segment (`MAC addresses`, `Ethernet 802.3`, `WiFi 802.11`). MAC address is 6 bytes long; the first 3 bytes identify the vendor.
* **Layer 1 - Physical:** Physical transmission media (copper cables, optical fiber, radio frequencies).

### 2. TCP/IP Model (DoD)
Developed in the 1970s for resilience against network link failures. Simplifies the OSI model into 4 layers:
* **Application Layer:** Merges OSI layers 5, 6, and 7.
* **Transport Layer:** OSI layer 4 (`TCP`, `UDP`).
* **Internet Layer:** OSI layer 3 (`IP`, `ICMP`).
* **Link Layer:** Merges OSI layers 1 and 2.

### 3. IPv4 & Private IP Ranges (RFC 1918)
IPv4 addresses are 32 bits (4 octets, 0–255). Private address ranges cannot be routed across the public internet without NAT:
* `10.0.0.0/8` (10.0.0.0 – 10.255.255.255)
* `172.16.0.0/12` (172.16.0.0 – 172.31.255.255)
* `192.168.0.0/16` (192.168.0.0 – 192.168.255.255)

Subnet mask `/24` (`255.255.255.0`) means the first 24 bits represent the network:
* `X.X.X.0` = Network Address
* `X.X.X.255` = Broadcast Address
* `X.X.X.1` to `X.X.X.254` = Usable host addresses (254 hosts)

### 4. Transport Protocols & The TCP 3-Way Handshake
* **UDP:** Connectionless, fast, no delivery confirmation or packet ordering (DNS, VoIP, video streaming).
* **TCP:** Connection-oriented, reliable, guarantees packet delivery using sequence numbers and ACKs.
* **TCP 3-Way Handshake:**
  1. `SYN` (Client $\rightarrow$ Server)
  2. `SYN-ACK` (Server $\rightarrow$ Client)
  3. `ACK` (Client $\rightarrow$ Server)
* **Port Range:** Ports `1` through `65535` (16 bits). Port `0` is reserved.

### 5. Encapsulation & Protocol Data Units (PDUs)
* Data moves down the stack: **Data** (App) $\rightarrow$ **Segment/Datagram** (Transport) $\rightarrow$ **Packet** (Network) $\rightarrow$ **Frame** (Data Link) $\rightarrow$ **Bits** (Physical).
* Decapsulation strips headers in reverse order on arrival.

---

## Commands & steps I used

### Checking local IP configuration
```bash
# Linux
ip a s
# or
ifconfig

# Windows
ipconfig
```

### Banner Grabbing & Service Interaction via Telnet
```bash
# Connecting to Echo service (Port 7)
telnet <TARGET_IP> 7

# Connecting to Daytime service (Port 13)
telnet <TARGET_IP> 13

# Connecting to HTTP Web Server (Port 80)
telnet <TARGET_IP> 80
```

Once connected to port 80, manually sent the raw HTTP GET request:
```http
GET / HTTP/1.1
Host: tryhackme.com
[Enter]
[Enter]
```

Server returned HTTP response headers and body containing the flag:
* **Server Banner:** `lighttpd/1.4.63`
* **HTTP Status:** `200 OK`

---

## Questions & answers
* **MAC address size:** 6 bytes (first 3 bytes identify the vendor)
* **IPv4 address size:** 32 bits (4 octets)
* **TCP Handshake packets:** 3 packets (SYN, SYN-ACK, ACK)
* **Flag captured on Port 80:** `THM{TELNET_MASTER}`

---

## My takeaways
* Telnet communicates entirely in plaintext—credentials and data can easily be captured over the wire using Wireshark. It is no longer suitable for administrative access and was replaced by SSH.
* However, `telnet` (and `netcat`) remains a valuable testing utility for quick manual banner grabbing and validating whether a TCP port responds before using heavier tools.
