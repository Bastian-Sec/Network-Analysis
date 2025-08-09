# TShark Export

Commands to extract objects, flows, and specific data from capture files.

---

## Export HTTP objects  
**Command:** `tshark -r capture.pcapng --export-objects http,./http_files`  
**Description:** Extracts HTTP-transferred files into the folder `http_files`.

---

## Export SMB objects (files)  
**Command:** `tshark -r capture.pcapng --export-objects smb,./smb_files`  
**Description:** Extracts files transferred via SMB into the folder `smb_files`.

---

## Export TFTP objects  
**Command:** `tshark -r capture.pcapng --export-objects tftp,./tftp_files`  
**Description:** Saves files transferred via TFTP into the folder `tftp_files`.

---

## Export specific TCP stream (ASCII format)  
**Command:** `tshark -r capture.pcapng -q -z follow,tcp,ascii,5 > stream5.txt`  
**Description:** Extracts TCP stream number `5` in ASCII format to `stream5.txt`.

---

## Export specific UDP stream (ASCII format)  
**Command:** `tshark -r capture.pcapng -q -z follow,udp,ascii,2 > stream2.txt`  
**Description:** Extracts UDP stream number `2` in ASCII format to `stream2.txt`.

---

## Export selected fields to CSV  
**Command:** `tshark -r capture.pcapng -T fields -E header=y -E separator=, -e frame.number -e ip.src -e ip.dst -e frame.len > packets.csv`  
**Description:** Writes selected fields to a CSV file with headers.

---

## Export packets matching a display filter to a new pcap  
**Command:** `tshark -r capture.pcapng -Y "http" -w http_only.pcapng`  
**Description:** Writes only HTTP packets from the original file into `http_only.pcapng`.

---

## Export packets from a specific time range to a new pcap  
**Command:** `tshark -r capture.pcapng -Y "frame.time >= \"2025-08-09 10:00:00\" && frame.time <= \"2025-08-09 10:05:00\"" -w range.pcapng`  
**Description:** Saves packets from the specified 5-minute window into `range.pcapng`.

---

## Export packets containing a specific string in payload  
**Command:** `tshark -r capture.pcapng -Y "frame contains \"password\"" -w password_hits.pcapng`  
**Description:** Writes packets containing the word "password" to `password_hits.pcapng`.
