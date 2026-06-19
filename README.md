# Network_Traffic_Sniffer_Python

## Project Description
This repository features a custom-built, lightweight **Network Traffic Sniffer** developed during my **CodeAlpha Cybersecurity Internship**. The primary objective of this project is to build an active protocol analyzer capable of intercepting, parsing, and documenting live network traffic directly from a local network adapter.

By leveraging Python's network handling capabilities, this tool hooks into active data streams, allowing security analysts to inspect packet headers, track communication paths, and read raw payload bytes for diagnostic and security auditing purposes.

---

##  Key Technical Capabilities
* **Live Ingestion Engine:** Captures inbound and outbound frames traversing the active network interface card in real-time.
* **Protocol Dissection:** Automatically detects, breaks down, and categorizes vital internet protocols:
  * **IPv4 Layer:** Isolates source and destination IP routing addresses.
  * **TCP Layer:** Parses connection-oriented streams along with source and destination ports.
  * **UDP Layer:** Tracks connectionless broadcast and unicast packets (e.g., local app discoveries).
  * **ICMP Layer:** Monitors diagnostic and control traffic (such as network pings).
* **Payload Inspection:** Grabs raw payload summaries, facilitating immediate visibility into unencrypted data transmissions.
* **Graceful Terminate:** Built to handle instant keyboard interrupts safely, offering clean runtime statistics upon shutdown.

---

##  Core Competencies Covered

###  1. Protocol Architecture & Telemetry
* **OSI Model Mapping:** Practical manipulation of data units moving across Layer 3 (Network) and Layer 4 (Transport) of the OSI stack.
* **Network Tracing:** Reading socket telemetry to understand how data moves between local nodes and external servers.

###  2. Security Auditing & Traffic Analysis
* **Deep Packet Extraction:** Examining binary payloads to identify cleartext transmission risks within a local network segment.
* **Traffic Verification:** Dissecting background broadcast behaviors (such as unencrypted local application configurations) to identify passive data leakage.

---

##  How It Works & Execution Flow
1. **Socket Initialization:** The script requests administrative access to control the network adapter via kernel packet drivers (**Npcap**).
2. **Sniffing Loop:** It runs a background loop that intercepts matching IPv4 communication frames.
3. **Parsing Routine:** For every packet caught, a callback routine strips down the layers, extracting the IPs, Transport Protocol, Port Numbers, and Payload Strings.
4. **Terminal Output:** The structured analysis is cleanly formatted and displayed instantly inside the integrated shell terminal.

---

 "port": 17500, "host_int": 1042959...
