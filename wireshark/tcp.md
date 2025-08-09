# Wireshark TCP Filters

Display filters and features focused on TCP traffic analysis.

---

## Filter: Show only TCP traffic  
**Syntax:** `tcp`  
**Description:** Displays only TCP packets in the capture.

---

## Filter: TCP handshake packets only (SYN, SYN-ACK, ACK)  
**Syntax:** `tcp.flags.syn == 1 || tcp.flags.ack == 1`  
**Description:** Displays TCP packets that are part of the connection handshake process.

---

## Filter: TCP packets with the SYN flag set (connection start)  
**Syntax:** `tcp.flags.syn == 1 && tcp.flags.ack == 0`  
**Description:** Shows initial SYN packets from clients starting a TCP connection.

---

## Filter: TCP reset packets (RST)  
**Syntax:** `tcp.flags.reset == 1`  
**Description:** Displays TCP packets that reset an existing connection.

---

## Filter: TCP retransmissions  
**Syntax:** `tcp.analysis.retransmission`  
**Description:** Filters packets marked by Wireshark as TCP retransmissions, useful for identifying packet loss or latency.

---

## Filter: TCP duplicate ACKs  
**Syntax:** `tcp.analysis.duplicate_ack`  
**Description:** Shows duplicate acknowledgments, often related to packet loss or reordering.

---

## Filter: TCP zero window  
**Syntax:** `tcp.analysis.zero_window`  
**Description:** Displays packets where the receiver has advertised a zero window size, meaning it cannot receive more data at the moment.

---

## Filter: TCP window size less than a value  
**Syntax:** `tcp.window_size_value < 1000`  
**Description:** Filters packets where the TCP window size is less than 1000 bytes, potentially indicating performance issues.

---

## Feature: Follow TCP Stream  
**Description:** Reconstructs the entire TCP conversation.  
**How to use:** Right-click any TCP packet → **Follow** → **TCP Stream**.

---

## Feature: TCP Conversation Statistics  
**Description:** Summarizes statistics for TCP streams.  
**How to use:** Go to **Statistics → Conversations → TCP**.

