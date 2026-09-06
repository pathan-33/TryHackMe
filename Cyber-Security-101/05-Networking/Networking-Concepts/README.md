# Networking Concepts — Lab Notes & Walkthrough

* **Room:** [Networking Concepts](https://tryhackme.com/room/networkingconcepts)
* **Path:** Cyber Security 101
* **Module:** 05-Networking
* **Status:** ✅ Completed

---

## 🎯 Lab Overview
This lab covers how data actually moves across networks and provides hands-on practice interacting directly with open TCP ports from the command line using `telnet`. 

Instead of relying on high-level tools or browsers that hide the underlying mechanics, this room demonstrates:
1. How the **OSI (7-layer)** and **TCP/IP (4-layer)** models structure network communication.
2. How IPv4 addressing, private subnets (RFC 1918), and routing function.
3. How the **TCP 3-Way Handshake** establishes reliable connections compared to UDP.
4. **Hands-on Lab:** Connecting to raw TCP ports (7, 13, and 80) and manually crafting an HTTP GET request to retrieve the hidden flag.

---

## 🧠 Core Theory & Reference Notes

### 1. OSI vs. TCP/IP Architecture
The OSI model provides the theoretical 7-layer framework, while TCP/IP is the practical 4-layer model implemented across the Internet:

| OSI Layer | TCP/IP Layer | Key Protocols & Identifiers | Function |
| :--- | :--- | :--- | :--- |
| **7. Application**<br>**6. Presentation**<br>**5. Session** | **Application** | `HTTP`, `HTTPS`, `SSH`, `DNS`, `FTP`, `Telnet` | Delivers network services directly to end-user applications. |
| **4. Transport** | **Transport** | `TCP`, `UDP` (Ports `1`–`65535`) | End-to-end communication between specific processes. |
| **3. Network** | **Internet** | `IPv4`, `IPv6`, `ICMP`, `IPSec` | Logical addressing and packet routing across networks. |
| **2. Data Link**<br>**1. Physical** | **Link** | `Ethernet (802.3)`, `Wi-Fi (802.11)`, MAC addresses | Physical transmission & frame delivery on the same local segment. |

* **MAC Address (Layer 2):** 6 bytes (48 bits). The first 3 bytes represent the vendor/manufacturer.
* **IPv4 Address (Layer 3):** 32 bits (4 octets, 0–255). Roughly 4.3 billion theoretical addresses.

---

### 2. Private IP Ranges (RFC 1918)
Private IP ranges cannot be routed across the public internet without Network Address Translation (NAT):
* `10.0.0.0/8` (10.0.0.0 – 10.255.255.255)
* `172.16.0.0/12` (172.16.0.0 – 172.31.255.255)
* `192.168.0.0/16` (192.168.0.0 – 192.168.255.255)

---

### 3. TCP vs. UDP & The 3-Way Handshake
* **UDP:** Connectionless, no delivery guarantees, low overhead (DNS queries, live video streaming, VoIP).
* **TCP:** Connection-oriented, guarantees packet arrival and ordering using sequence and acknowledgement numbers.
* **TCP Handshake:**
  1. `SYN` — Client initiates and sends initial sequence number.
  2. `SYN-ACK` — Server acknowledges client's sequence number and sends its own.
  3. `ACK` — Client confirms receipt; connection is established.

---

### 4. Encapsulation & Protocol Data Units (PDUs)
As data travels down the protocol stack, each layer wraps the payload with its own header:
$$\text{Data} \xrightarrow{\text{Transport}} \text{Segment (TCP) / Datagram (UDP)} \xrightarrow{\text{Network}} \text{Packet (IP)} \xrightarrow{\text{Link}} \text{Frame (MAC)} \xrightarrow{\text{Physical}} \text{Bits}$$

---

## 🛠️ Hands-on Lab: Interacting with Services via Telnet

In this practical exercise, I used `telnet` on the AttackBox to connect directly to various listening TCP ports on the target machine (`10.49.166.247`).

### Task A: Testing the Echo Service (Port 7)
The echo service simply repeats back any text sent to it:
```bash
telnet 10.49.166.247 7
```
* Entered: `Hi` $\rightarrow$ Server echoed: `Hi`
* Escape character: `Ctrl + ]`, then typed `quit` to close connection.

---

### Task B: Testing the Daytime Service (Port 13)
The daytime service returns the server's current timestamp and immediately terminates the connection:
```bash
telnet 10.49.166.247 13
```
* Server response: `Thu Jun 20 12:36:32 PM UTC 2024`

---

### Task C: Interacting with the Web Server & Capturing the Flag (Port 80)
Instead of using a web browser, I connected directly to TCP Port 80 to manually issue a raw HTTP GET request.

```bash
root@ip-10-49-95-83:~# telnet 10.49.166.247 80
Trying 10.49.166.247...
Connected to 10.49.166.247.
Escape character is '^]'.
```

Once the connection was established, I manually typed the raw HTTP/1.1 request headers:
```http
GET / HTTP/1.1
Host: tryhackme.com
[Enter]
[Enter]
```
*(Hitting Enter twice sends the required blank line that terminates the HTTP request header block)*.

#### Server Response & Flag Capture:
```http
HTTP/1.1 200 OK
Content-Type: text/html
ETag: "2920831920"
Last-Modified: Thu, 20 Jun 2024 12:39:38 GMT
Content-Length: 20
Accept-Ranges: bytes
Date: Sun, 06 Sep 2026 03:25:02 GMT
Server: lighttpd/1.4.63

THM{TELNET_MASTER}
Connection closed by foreign host.
```

* **Captured Flag:** `THM{TELNET_MASTER}`
* **Server Banner:** `lighttpd/1.4.63`
* **Status Code:** `200 OK`

---

## 🚩 Questions & Lab Answers

| Question / Topic | Answer / Finding |
| :--- | :--- |
| How many bytes in a standard MAC address? | `6` bytes (first 3 bytes identify the vendor) |
| How many bits in an IPv4 address? | `32` bits |
| How many packets in the TCP handshake? | `3` packets (`SYN`, `SYN-ACK`, `ACK`) |
| Valid TCP/UDP port number range? | `1` to `65535` |
| What flag is found on the port 80 web server? | `THM{TELNET_MASTER}` |

---

## 🔒 Security Analysis & Pentesting Takeaways

1. **The Insecurity of Telnet:**
   * Telnet transmits all data—including authentication credentials and session tokens—in cleartext. Anyone on the local network running a packet sniffer like Wireshark or performing an ARP spoofing attack can intercept credentials.
   * In modern environments, Telnet has been entirely replaced by **SSH (Secure Shell, Port 22)**, which encrypts the entire session.

2. **Manual Banner Grabbing in Reconnaissance:**
   * Connecting directly to open ports with `telnet` or `nc` (Netcat) is an essential reconnaissance technique. 
   * As seen above, connecting to port 80 immediately disclosed the server version: `lighttpd/1.4.63`. As a penetration tester, identifying the exact server software and version allows you to search exploit databases (Exploit-DB, CVEs) for known vulnerabilities affecting that release.
