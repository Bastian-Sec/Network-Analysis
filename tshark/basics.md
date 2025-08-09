# TShark Basics

Essential TShark commands and options for packet capture and analysis via CLI.

---

## Show available interfaces  
**Command:** `tshark -D`  
**Description:** Lists all available network interfaces and their corresponding numbers.

---

## Capture on a specific interface  
**Command:** `tshark -i 1`  
**Description:** Starts capturing packets on the interface with index `1` (use `-D` to find the index).

---

## Capture with a display filter  
**Command:** `tshark -i 1 -Y "http"`  
**Description:** Captures packets on interface `1` and applies a display filter to show only HTTP traffic.

---

## Capture with a capture filter  
**Command:** `tshark -i 1 -f "tcp port 80"`  
**Description:** Captures only TCP packets on port 80 (faster than display filters as it limits capture at the start).

---

## Read from a pcap file  
**Command:** `tshark -r capture.pcap`  
**Description:** Reads and displays packets from an existing capture file.

---

## Save captured packets to a file  
**Command:** `tshark -i 1 -w output.pcap`  
**Description:** Captures packets and writes them directly to `output.pcap` for later analysis.

---

## Apply a display filter to a pcap file  
**Command:** `tshark -r capture.pcap -Y "ip.addr == 192.168.1.10"`  
**Description:** Reads a pcap file and displays only packets involving the specified IP.

---

## Limit the number of packets captured  
**Command:** `tshark -i 1 -c 100`  
**Description:** Captures exactly 100 packets and then stops.

---

## Capture with a time limit  
**Command:** `tshark -i 1 -a duration:60`  
**Description:** Captures for 60 seconds and then stops.

---

## Show packet summary only  
**Command:** `tshark -i 1 -q`  
**Description:** Displays only a summary of captured packets without packet details.

---

## Show detailed packet information  
**Command:** `tshark -i 1 -V`  
**Description:** Displays each captured packet with full protocol details.

---

## Combine detailed view with filtering  
**Command:** `tshark -i 1 -V -Y "dns"`  
**Description:** Captures packets and shows detailed view only for DNS traffic.

