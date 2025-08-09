# Wireshark UDP Filters

Display filters and features focused on UDP traffic analysis.

---

## Filter: Show only UDP traffic  
**Syntax:** `udp`  
**Description:** Displays only UDP packets in the capture.

---

## Filter: UDP traffic from a specific port  
**Syntax:** `udp.srcport == 53`  
**Description:** Displays UDP packets where the source port is 53 (commonly DNS responses).

---

## Filter: UDP traffic to a specific port  
**Syntax:** `udp.dstport == 53`  
**Description:** Displays UDP packets where the destination port is 53 (commonly DNS queries).

---

## Filter: UDP traffic from a specific IP  
**Syntax:** `udp && ip.src == 192.168.1.10`  
**Description:** Displays UDP packets where the source IP matches the specified address.

---

## Filter: UDP traffic to a specific IP  
**Syntax:** `udp && ip.dst == 192.168.1.10`  
**Description:** Displays UDP packets where the destination IP matches the specified address.

---

## Filter: UDP traffic between two IPs  
**Syntax:** `udp && ip.src == 192.168.1.10 && ip.dst == 192.168.1.20`  
**Description:** Displays UDP packets exchanged between two specific IPs.

---

## Filter: UDP traffic larger than a specific size  
**Syntax:** `udp && frame.len > 1000`  
**Description:** Displays UDP packets larger than 1000 bytes.

---

## Feature: Follow UDP Stream  
**Description:** Reconstructs the conversation for UDP streams (if Wireshark can detect them).  
**How to use:** Right-click any UDP packet → **Follow** → **UDP Stream**.

---

## Feature: UDP Conversations Statistics  
**Description:** Summarizes statistics for UDP flows.  
**How to use:** Go to **Statistics → Conversations → UDP**.

