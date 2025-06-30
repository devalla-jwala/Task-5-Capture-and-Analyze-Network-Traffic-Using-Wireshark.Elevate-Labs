# 🧪 Wireshark Network Packet Analysis (Kali Linux)

> A hands-on project capturing and analyzing network traffic using **Wireshark** on **Kali Linux**.

---

## 📌 Objective

- Capture live network packets on a Linux machine.
- Manually trigger known traffic using `ping`, `dig`, and web browsing.
- Analyze at least 3 protocols using filters in Wireshark.
- Export findings and `.pcapng` for future reference.

---

## 🛠 Tools Used

- 🐧 Kali Linux
- 🧪 [Wireshark](https://www.wireshark.org/)
- 📡 eth0 Interface

---

## steps
# Update the system and install Wireshark

`sudo apt update`

`sudo apt install wireshark -y`

# Launch Wireshark

# In Wireshark:
# - Select interface (eth0 or wlan0)
# - Click the blue shark fin icon to start capture

![image alt](https://github.com/devalla-jwala/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark.Elevate-Labs/blob/8a4dce4bfeb317c1d14f6d1b2ab9b7245c7ee32d/2.png)

# Send ICMP packets (ping)
`ping -c 4 google.com`

![image alt](https://github.com/devalla-jwala/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark.Elevate-Labs/blob/8a4dce4bfeb317c1d14f6d1b2ab9b7245c7ee32d/.Filter%20captured%20packets%20by%20protocol.png)

# Perform a DNS lookup
`dig facebook.com`

# Generate HTTP (non-secure) request
`curl http://neverssl.com`

# Generate HTTPS (TLS encrypted) request
`curl https://wikipedia.org`

![image alt](https://github.com/devalla-jwala/Task-5-Capture-and-Analyze-Network-Traffic-Using-Wireshark.Elevate-Labs/blob/8a4dce4bfeb317c1d14f6d1b2ab9b7245c7ee32d/3.png)

> Capturing packets from interface `eth0`, filtered by protocol (TCP, TLS, UDP, ICMPv6, ARP).

# After 30–60 seconds, stop capture in Wireshark (red square button)

# Save the capture:
# File > Save As > wireshark_task5_jwala.pcapng
---

## 🎯 Protocols Identified

| Protocol   | Purpose                          | Notes |
|------------|----------------------------------|-------|
| **TCP**    | Reliable data transmission       | Observed with ACK, RST, FIN |
| **TLSv1.2**| Encrypted web traffic            | Shows Client Hello & Application Data |
| **UDP**    | Unreliable but fast communication| Seen on port 57621 |
| **ARP**    | Resolves IP to MAC addresses     | Local device discovery |
| **ICMPv6** | Router Advertisement             | IPv6 network announcement |

---

## 🔍 Sample Packet Details

| Packet # | Protocol | Source → Destination | Description |
|----------|----------|----------------------|-------------|
| 60710    | TCP      | 172.20.10.2 → 172.64.150.5 | ACK, Seq=873, RST flag |
| 60712    | UDP      | 172.20.10.6 → 172.20.10.15 | Length=44 |
| 60720    | ARP      | Broadcast → AzureWaveTec   | Who has 172.20.10.1 |
| 60721    | ICMPv6   | fe80::a851 → ff02::1       | Router Advertisement |
| 60706    | TLSv1.2  | 172.20.10.2 → 172.64.150.5 | TLS Handshake |

---


---

## ✅ Outcome

- Learned how to capture clean, manual traffic on a Linux machine.
- Gained familiarity with common protocols and packet filtering.
- Successfully used Wireshark for transport & network layer analysis.

---

## 📚 References

- [Wireshark Display Filters](https://wiki.wireshark.org/DisplayFilters)
- [Packet Analysis Techniques](https://wiki.wireshark.org/PacketAnalysis)

---
