# Transport Layer Protocol Analysis (Cisco Packet Tracer)

A network simulation study analyzing Protocol Data Units (PDUs), multiplexing, port dynamics, and behavioral differences between TCP and UDP communications.

---

## ⚠️ Important Note on Opening the Simulation File
> **Opening Warning:** Do not launch the project by double-clicking the `.pkt` file directly, as Packet Tracer may fail to load the active canvas and topology configurations.
>
> **Correct Opening Steps:**
> 1. Launch **Cisco Packet Tracer** first.
> 2. From the top navigation menu, select **File** -> **Open...** (or press `Ctrl + O`).
> 3. Browse and select the `.pkt` file from your local directory.

---

## Network Topology
A centralized star topology centered around a Cisco Catalyst switch (`2960-24TT`), connecting a multi-service host (`MultiServer` at `192.168.1.254`) to dedicated protocol testing clients:
* **HTTP Client:** Web service communications
* **FTP Client:** File transfer sessions
* **DNS Client:** Name resolution operations
* **E-Mail Client:** SMTP/POP3 message exchange

---

## Protocol Experiments & Analysis

### 1. HTTP & TCP Handshake
* Observed the complete TCP 3-way handshake (`SYN` -> `SYN+ACK` -> `ACK`) prior to payload delivery.
* Tracked sequence and acknowledgement number incrementation across client port `1025` and destination port `80`.

### 2. FTP Session & Stateful Management
* Validated reliable data stream initialization over control port `21`.
* Monitored persistent connection states using `netstat`, demonstrating long-lived socket retention while awaiting user authentication.

### 3. DNS over UDP
* Contrasted connectionless transport against TCP; validated low-overhead transmission without handshake phases or Sequence/ACK tracking over port `53`.

### 4. Email Services (SMTP / POP3)
* Analyzed message submission via SMTP (Port `25`) and retrieval via POP3 (Port `110`).
* Inspected packet flags verifying immediate segment push (`PSH+ACK`) during message data exchange.

---

## Software Requirements
* Cisco Packet Tracer (v8.0 or later recommended)
