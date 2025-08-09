# TShark Capture

Focused examples for capturing traffic with TShark, including ring buffers, size/time limits, and practical capture filters.

---

## List interfaces and start a basic capture  
**Command:** `tshark -D && tshark -i 1`  
**Description:** First lists all interfaces, then starts capturing on interface index `1`.

---

## Capture with a capture filter (BPF)  
**Command:** `tshark -i 1 -f "tcp port 80"`  
**Description:** Uses a capture filter to only acquire TCP traffic on port 80 (more efficient than display filters).

---

## Capture and write directly to file  
**Command:** `tshark -i 1 -w capture.pcapng`  
**Description:** Saves packets to `capture.pcapng` for later analysis.

---

## Limit capture by duration (auto-stop)  
**Command:** `tshark -i 1 -a duration:300 -w capture_5min.pcapng`  
**Description:** Captures for 300 seconds (5 minutes) and then stops automatically.

---

## Limit capture by file size (auto-stop)  
**Command:** `tshark -i 1 -a filesize:100 -w capture_100MB.pcapng`  
**Description:** Stops when the file reaches ~100 MB.

---

## Use a ring buffer by file count  
**Command:** `tshark -i 1 -b files:5 -b filesize:50 -w ring.pcapng`  
**Description:** Keeps a rolling set of 5 files, each up to ~50 MB. Oldest files are overwritten.

---

## Use a ring buffer by time  
**Command:** `tshark -i 1 -b duration:60 -w ring_time.pcapng`  
**Description:** Creates a new file every 60 seconds in a rolling fashion.

---

## Split files by both time and size  
**Command:** `tshark -i 1 -b duration:300 -b filesize:200 -w split.pcapng`  
**Description:** Rotates a new file every 5 minutes or at ~200 MB, whichever happens first.

---

## Add a display filter while capturing (view only)  
**Command:** `tshark -i 1 -Y "dns" -w all.pcapng`  
**Description:** Captures everything to `all.pcapng` but **shows** only DNS packets on screen.

---

## Write only packets that match a display filter (two-pass)  
**Command:** `tshark -i 1 -w raw.pcapng && tshark -r raw.pcapng -Y "http" -w http_only.pcapng`  
**Description:** First capture all traffic, then re-filter to write only HTTP packets to a new file.

---

## Disable name resolution (faster)  
**Command:** `tshark -i 1 -n`  
**Description:** Disables DNS/port name resolution for better performance and cleaner output.

---

## Promiscuous mode off (optional)  
**Command:** `tshark -i 1 -p`  
**Description:** Disables promiscuous mode; captures only traffic addressed to the interface.

---

## Monitor mode for Wi‑Fi (if supported)  
**Command:** `tshark -i wlan0 -I -w wifi_monitor.pcapng`  
**Description:** Enables 802.11 monitor mode to capture raw Wi‑Fi frames (requires driver/OS support).

---

## Combine capture and display filters  
**Command:** `tshark -i 1 -f "tcp port 443" -Y "tls.handshake" -w tls_hs.pcapng`  
**Description:** Captures only TCP/443 and displays only TLS handshake packets on screen.

---

## Quiet mode & packet count limit  
**Command:** `tshark -i 1 -q -c 1000 -w sample_1k.pcapng`  
**Description:** Captures exactly 1000 packets with minimal console output.

---

## Timestamp precision (nanoseconds, if supported)  
**Command:** `tshark -i 1 --time-stamp-type adapter_unsynced -t ad`  
**Description:** Example of setting timestamp behavior and absolute time display; options depend on adapter/OS.

---

