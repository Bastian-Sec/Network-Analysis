
# Wireshark DNS Filters

Display filters and features focused on DNS traffic analysis.

---

## Filter: Show only DNS traffic  
**Syntax:** `dns`  
**Description:** Displays only DNS packets in the capture.

---

## Filter: Show only DNS queries  
**Syntax:** `dns.flags.response == 0`  
**Description:** Displays only DNS query packets.

---

## Filter: Show only DNS responses  
**Syntax:** `dns.flags.response == 1`  
**Description:** Displays only DNS response packets.

---

## Filter: DNS queries for a specific domain  
**Syntax:** `dns.qry.name == "example.com"`  
**Description:** Shows DNS queries requesting the specified domain name.

---

## Filter: DNS queries containing a keyword  
**Syntax:** `dns.qry.name contains "google"`  
**Description:** Displays DNS queries for domains containing the keyword "google".

---

## Filter: DNS traffic from a specific IP  
**Syntax:** `dns && ip.addr == 192.168.1.10`  
**Description:** Shows DNS packets where either the source or destination IP matches the specified value.

---

## Filter: DNS traffic over TCP  
**Syntax:** `dns && tcp`  
**Description:** Displays DNS traffic that is carried over TCP instead of UDP.

---

## Filter: Malformed DNS packets  
**Syntax:** `dns.flags.rcode != 0`  
**Description:** Displays DNS responses with error codes.

---

## Feature: DNS Statistics  
**Description:** Summarizes DNS queries and responses.  
**How to use:** Go to **Statistics → Resolved Addresses** or **Statistics → Conversations → UDP** filtered by port 53.
