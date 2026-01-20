Here is the complete, professionally formatted **README.md** structure for your GitHub repository. It combines your project overview, the technical analysis from **Task 3**, and references to your uploaded evidence.

---

# 🛡️ Network Traffic Analysis Lab

## 📊 Project Overview

This repository documents a hands-on exploration of network protocols, packet capturing, and security analysis. Using **Wireshark** on a **Kali Linux** environment, I intercepted live data to analyze the fundamental "handshakes" of the internet and identify critical security vulnerabilities.

### 🎯 Final Outcome

Demonstrated the professional **ability to analyze network traffic** by dissecting the TCP/IP stack and auditing unencrypted application-layer communications.

---

## 🛠️ Skills & Tools

* **Capture Tool:** Wireshark 4.4.7
* **Environment:** Kali Linux (eth0 interface)
* **Protocols Analyzed:** DNS, TCP, HTTP, and TLSv1.3
* **Techniques:** Display filtering, packet dissection, and flow analysis

---

## 📂 Repository Structure

* **`/captures`**: Contains `capture.pcap`, the raw trace of 7,662 packets.
* **`/screenshots`**: Visual evidence of protocol analysis and security leaks.
* **`README.md`**: Project overview and detailed Task 3 analysis.

---

## 🔬 Task 3: Filtering and Detailed Analysis

### 1. DNS Resolution (The "Phonebook" Phase)

* **Filter:** `dns`
* **Observation:** The client (`10.0.2.15`) queried the DNS server (`10.0.2.3`) for `www.google.com`.
* **Result:** Successfully translated the domain name to IP address `142.251.43.228`.
* **Significance:** Proves understanding of how the application layer initiates communication.

### 2. TCP Three-Way Handshake (The "Handshake" Phase)

* **Filter:** `tcp.flags.syn == 1`
* **Observation:** Captured the **SYN** packet initiated by the client.
* **Finding:** Verified the "introduction" between the client and server to ensure a reliable connection before data transfer.

### 3. HTTP vs. HTTPS Security Audit

This section highlights the most critical vulnerability identified in the `capture.pcap` file.

* **HTTP (Unencrypted) Vulnerability:**
* **Activity:** Analyzed an interaction with `testphp.vulnweb.com/userinfo.php`.
* **Filter:** `http.request.method == "POST"`
* **Discovery:** In **Packet #7**, the credentials were found in plain text within the "HTML Form URL Encoded" layer.
* **Data Found:** `uname=test` and `pass=test`.


* **HTTPS (Encrypted) Protection:**
* **Observation:** Traffic to Google (Port 443) used **TLSv1.3**.
* **Result:** Data appeared as "Application Data" (encrypted gibberish), protecting user privacy.



#### 📸 Evidence of Credential Leak

> *Below is the captured plain-text password from Packet #7 as seen in the analysis:*

---

## ✅ Deliverables Checklist

* [x] **Packet Capture:** `capture.pcap` saved and uploaded.
* [x] **Analysis Report:** Detailed observations written in simple language.
* [x] **Screenshots:** Visual proof of DNS, TCP, and HTTP analysis.

---

**Would you like me to help you write a summary of this project for your resume or portfolio?**
