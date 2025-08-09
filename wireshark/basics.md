# Wireshark Basics

General display filters and features that are useful for any type of traffic analysis.

---

## Filter: Show all traffic from/to a specific IP  
**Syntax:** `ip.addr == 192.168.1.10`  
**Description:** Displays packets where either the source or destination IP matches the specified address.

---

## Filter: Show only TCP traffic  
**Syntax:** `tcp`  
**Description:** Filters to display only TCP packets.

---

## Filter: Show only UDP traffic  
**Syntax:** `udp`  
**Description:** Filters to display only UDP packets.

---

## Filter: Show packets from a specific port  
**Syntax:** `tcp.port == 443`  
**Description:** Shows packets where either the source or destination port is 443 (HTTPS).

---

## Filter: Show only source IP traffic  
**Syntax:** `ip.src == 10.0.0.5`  
**Description:** Displays packets where the specified IP is the source.

---

## Filter: Show only destination IP traffic  
**Syntax:** `ip.dst == 10.0.0.5`  
**Description:** Displays packets where the specified IP is the destination.

---

## Filter: Show packets between two IPs  
**Syntax:** `ip.src == 192.168.1.10 && ip.dst == 192.168.1.20`  
**Description:** Displays packets sent from one IP to another.

---

## Filter: Show packets larger than a specific size  
**Syntax:** `frame.len > 1000`  
**Description:** Displays packets larger than 1000 bytes.

---

## Feature: Follow TCP Stream  
**Description:** Reconstructs the complete conversation of a TCP stream.  
**How to use:** Right-click on a TCP packet → **Follow** → **TCP Stream**.

---

## Feature: Coloring Rules  
**Description:** Apply custom colors to highlight traffic patterns.  
**How to use:** Go to **View → Coloring Rules** → Add/Edit.

