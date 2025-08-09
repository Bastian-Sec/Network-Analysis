# TShark Display Filters & Output Formatting

Commands for applying display filters, selecting fields, and customizing TShark output.

---

## Apply a basic display filter  
**Command:** `tshark -r capture.pcapng -Y "http"`  
**Description:** Displays only packets matching the display filter `http`.

---

## Combine multiple display filters (AND)  
**Command:** `tshark -r capture.pcapng -Y "ip.src == 192.168.1.10 && tcp.port == 443"`  
**Description:** Shows packets from the given source IP **and** TCP port 443.

---

## Combine multiple display filters (OR)  
**Command:** `tshark -r capture.pcapng -Y "tcp || udp"`  
**Description:** Shows only TCP or UDP packets.

---

## Display filter for specific string in a field  
**Command:** `tshark -r capture.pcapng -Y "http.host contains \"example.com\""`  
**Description:** Shows HTTP packets where the Host header contains "example.com".

---

## Display filter for packet size  
**Command:** `tshark -r capture.pcapng -Y "frame.len > 1000"`  
**Description:** Shows packets larger than 1000 bytes.

---

## Show only selected fields  
**Command:** `tshark -r capture.pcapng -T fields -e frame.number -e ip.src -e ip.dst -e frame.len`  
**Description:** Prints only the packet number, source IP, destination IP, and packet length.

---

## Show fields with a delimiter (CSV output)  
**Command:** `tshark -r capture.pcapng -T fields -E separator=, -e ip.src -e ip.dst -e tcp.port`  
**Description:** Outputs selected fields separated by commas (CSV format).

---

## Show protocol hierarchy  
**Command:** `tshark -r capture.pcapng -q -z io,phs`  
**Description:** Displays a protocol hierarchy summary for the capture.

---

## Show conversations (IP pairs)  
**Command:** `tshark -r capture.pcapng -q -z conv,ip`  
**Description:** Lists IP conversations, with packet and byte counts.

---

## Show top talkers by IP  
**Command:** `tshark -r capture.pcapng -q -z endpoints,ip`  
**Description:** Shows IP endpoints sorted by packet and byte usage.

---

## Show HTTP requests only  
**Command:** `tshark -r capture.pcapng -Y "http.request" -T fields -e http.host -e http.request.uri`  
**Description:** Lists HTTP hostnames and URIs from requests.

---

## Show DNS queries only  
**Command:** `tshark -r capture.pcapng -Y "dns.flags.response == 0" -T fields -e dns.qry.name`  
**Description:** Lists only DNS query names from the capture.

---

## Show DNS responses with answers  
**Command:** `tshark -r capture.pcapng -Y "dns.flags.response == 1" -T fields -e dns.a`  
**Description:** Lists DNS A record answers from responses.

---

## Filter packets by absolute time range  
**Command:** `tshark -r capture.pcapng -Y "frame.time >= \"2025-08-09 10:00:00\" && frame.time <= \"2025-08-09 10:05:00\""`  
**Description:** Displays only packets captured in the specified 5-minute time window.

---

## Match packets containing specific string in payload  
**Command:** `tshark -r capture.pcapng -Y "frame contains \"password\""`  
**Description:** Displays packets whose raw payload contains the word "password".

