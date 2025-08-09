# TShark Stats

Commands to generate summaries, counts, and time‑based statistics from capture files.

---

## Protocol hierarchy summary  
**Command:** `tshark -r capture.pcapng -q -z io,phs`  
**Description:** Displays a protocol hierarchy breakdown with packet/byte counts.

---

## IP conversations (pairwise)  
**Command:** `tshark -r capture.pcapng -q -z conv,ip`  
**Description:** Lists IP conversations with packets, bytes, and relative stats.

---

## TCP conversations  
**Command:** `tshark -r capture.pcapng -q -z conv,tcp`  
**Description:** Shows TCP conversations with packet/byte counts per flow.

---

## UDP conversations  
**Command:** `tshark -r capture.pcapng -q -z conv,udp`  
**Description:** Shows UDP conversations with packet/byte counts per flow.

---

## IP endpoints (top talkers)  
**Command:** `tshark -r capture.pcapng -q -z endpoints,ip`  
**Description:** Summarizes per‑host usage (packets/bytes), useful to find top talkers.

---

## Per‑interval I/O graph (all traffic)  
**Command:** `tshark -r capture.pcapng -q -z io,stat,1`  
**Description:** Prints packet/byte rates per 1‑second interval for the whole capture.

---

## Per‑interval I/O graph (with display filter)  
**Command:** `tshark -r capture.pcapng -Y "http" -q -z io,stat,1`  
**Description:** Same as above but only for packets that match the display filter (HTTP here).

---

## Per‑interval stats with custom fields  
**Command:** `tshark -r capture.pcapng -q -z io,stat,5,COUNT(dns),COUNT(tcp)`  
**Description:** Every 5 seconds, prints counts of DNS and TCP packets.

---

## TCP analysis: retransmissions over time  
**Command:** `tshark -r capture.pcapng -q -z io,stat,1,COUNT(tcp.analysis.retransmission)`  
**Description:** Counts TCP retransmissions per second to spot loss/latency patterns.

---

## HTTP summary  
**Command:** `tshark -r capture.pcapng -q -z http,stat`  
**Description:** Summarizes HTTP requests/responses, methods, status codes, and sizes.

---

## DNS summary  
**Command:** `tshark -r capture.pcapng -q -z dns,stat`  
**Description:** Shows DNS query/response stats, types, and error codes.

---

## TLS handshake summary  
**Command:** `tshark -r capture.pcapng -q -z tls,stat`  
**Description:** Summarizes TLS handshakes, versions, cipher suites, and alerts.

---

## Expert info (errors, warnings)  
**Command:** `tshark -r capture.pcapng -q -z expert`  
**Description:** Prints Wireshark’s expert analysis (timeouts, malformed packets, etc.).

---

## Top HTTP hosts (quick field count)  
**Command:** `tshark -r capture.pcapng -Y "http.host" -T fields -e http.host | sort | uniq -c | sort -nr | head`  
**Description:** Lists the most frequent HTTP hosts by count (shell pipeline).

