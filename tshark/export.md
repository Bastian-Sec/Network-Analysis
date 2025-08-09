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

## Export all TCP streams to individual files  
**Command:**  
```bash
for stream in $(tshark -r capture.pcapng -T fields -e tcp.stream | sort -n | uniq); do
  tshark -r capture.pcapng -q -z follow,tcp,raw,$stream > stream_$stream.bin
done

