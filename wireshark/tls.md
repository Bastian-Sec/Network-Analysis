# Wireshark TLS/SSL Filters

Display filters and features focused on TLS/SSL encrypted traffic analysis.

---

## Filter: Show only TLS/SSL traffic  
**Syntax:** `tls || ssl`  
**Description:** Displays only TLS or SSL packets in the capture.

---

## Filter: TLS handshake packets only  
**Syntax:** `tls.handshake`  
**Description:** Displays packets involved in the TLS handshake process.

---

## Filter: TLS Client Hello packets  
**Syntax:** `tls.handshake.type == 1`  
**Description:** Shows Client Hello messages sent by the client to initiate a TLS handshake.

---

## Filter: TLS Server Hello packets  
**Syntax:** `tls.handshake.type == 2`  
**Description:** Shows Server Hello messages sent by the server during the TLS handshake.

---

## Filter: TLS traffic to a specific host (via SNI)  
**Syntax:** `tls.handshake.extensions_server_name == "example.com"`  
**Description:** Displays TLS packets where the Server Name Indication matches the specified host.

---

## Filter: TLS packets from/to a specific IP  
**Syntax:** `(tls || ssl) && ip.addr == 192.168.1.10`  
**Description:** Displays TLS or SSL packets to or from the specified IP.

---

## Filter: TLS traffic using a specific version  
**Syntax:** `tls.record.version == 0x0303`  
**Description:** Displays TLS packets using TLS 1.2 (0x0303 is the hexadecimal code for TLS 1.2).

---

## Filter: TLS packets with alerts  
**Syntax:** `tls.alert_message`  
**Description:** Shows TLS packets that contain alert messages, which may indicate errors or session terminations.

---

## Feature: Follow TLS Stream  
**Description:** Reconstructs the encrypted conversation (limited visibility).  
**How to use:** Right-click any TLS packet → **Follow** → **TCP Stream**.

---

## Feature: Decrypt TLS Traffic  
**Description:** Allows decryption of TLS if you have the session keys or private key.  
**How to use:**  
1. Obtain the key log file or private key.  
2. Go to **Edit → Preferences → Protocols → TLS**.  
3. Set the key log file path.  
4. Reload the capture.

