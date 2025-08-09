# Wireshark HTTP Filters

Display filters and features focused on HTTP and HTTPS traffic analysis.

---

## Filter: Show only HTTP traffic  
**Syntax:** `http`  
**Description:** Displays only HTTP packets in the capture.

---

## Filter: HTTP requests only  
**Syntax:** `http.request`  
**Description:** Displays only HTTP request packets (GET, POST, etc.).

---

## Filter: HTTP responses only  
**Syntax:** `http.response`  
**Description:** Displays only HTTP response packets.

---

## Filter: HTTP GET requests  
**Syntax:** `http.request.method == "GET"`  
**Description:** Shows only HTTP GET request packets.

---

## Filter: HTTP POST requests  
**Syntax:** `http.request.method == "POST"`  
**Description:** Shows only HTTP POST request packets.

---

## Filter: HTTP traffic to a specific host  
**Syntax:** `http.host == "example.com"`  
**Description:** Displays HTTP packets where the Host header matches "example.com".

---

## Filter: HTTP traffic to/from a specific IP  
**Syntax:** `http && ip.addr == 192.168.1.10`  
**Description:** Displays HTTP packets where the IP address matches the specified value.

---

## Filter: HTTP packets containing a specific string in the URI  
**Syntax:** `http.request.uri contains "login"`  
**Description:** Displays HTTP requests whose URI contains the string "login".

---

## Feature: Follow HTTP Stream  
**Description:** Reconstructs the HTTP conversation for a given TCP stream.  
**How to use:** Right-click any HTTP packet → **Follow** → **HTTP Stream**.

---

## Feature: Export HTTP Objects  
**Description:** Extracts files or objects transferred via HTTP.  
**How to use:** **File → Export Objects → HTTP**.

