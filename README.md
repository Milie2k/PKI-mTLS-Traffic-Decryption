# 🔐 PKI Implementation & Mutual TLS (mTLS) Traffic Analysis

## 📌 Project Overview
This project involved building a small-scale **Public Key Infrastructure (PKI)** from scratch to secure communication between a Windows Server and a Kali Linux client. I demonstrated the full lifecycle of certificate management, implemented **mTLS**, and performed traffic decryption for security auditing purposes.



## 🛠️ Technical Stack
- **Tools:** OpenSSL, Wireshark, tcpdump, John the Ripper (JtR).
- **Encryption:** RSA 4096-bit (Root/Intermediate), Ed25519 (SSH).
- **Protocols:** TLS 1.3, mTLS, HTTPS, SSH.
- **Operating Systems:** Windows 11 (Server), Kali Linux (Client).

## 🚀 Key Implementation Steps
1. **PKI Hierarchy:** Created a self-signed **Root CA** and a subordinate **Intermediate CA** using OpenSSL to sign server and client certificates.
2. **mTLS Configuration:** Configured a secure tunnel requiring both the server and the client to present valid certificates before establishing a connection.
3. **Traffic Capture:** Used `tcpdump` to capture encrypted handshakes and data exchange between the two nodes.
4. **Decryption & Analysis:** Utilized an **SSL/TLS Key Log file** to decrypt the captured `.pcap` in Wireshark, exposing the underlying HTTP traffic.
5. **Vulnerability Auditing:** Simulated a brute-force attack on a weak private key passphrase using **John the Ripper** and mitigated the risk by implementing high-entropy passphrases.

## 🔍 Security Findings
- **Forward Secrecy:** Verified that the use of ephemeral keys (ECDHE) protected session data even if long-term keys were compromised.
- **Certificate Validation:** Successfully blocked unauthorized clients that did not possess a certificate signed by the Intermediate CA.

## 📊 Project Evidence
*(Full report and evidence screenshots included in the repository files)*
