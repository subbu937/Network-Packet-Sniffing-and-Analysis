# Network-Packet-Sniffing-and-Analysis
Packet sniffing and analysis using **Wireshark** to detect vulnerabilities and credential leakage.

---

## Project Files
- **Network Packet Sniffing and Analysis.docx** → Detailed project report  
- **Network Packet Sniffing and Analysis.pdf** → PDF version of the report (for easy viewing)  
- **wireshark.pcapng** → Raw packet capture file (open in Wireshark for analysis)  

---

## How to Open the Capture
1. Download `wireshark.pcapng` from this repository.  
2. Open it in **Wireshark** (`File → Open`).  
3. Apply filter:

   ```wireshark
   http.request.method == "POST"
   ```

   This filter shows all HTTP POST request packets.

4. Inspect captured packets:  
   - **Protocol:** HTTP  
   - **Source Port (Kali):** 39586  
   - **Destination Port (Target):** 80  
   - **Sequence / Acknowledgment numbers**  
   - **TCP Payload details**

5. On analyzing the HTTP packet (`/userinfo.php`), credentials entered on the target site were visible in **plain text**.

---

## Findings
- The target website transmits sensitive credentials **without encryption**.  
- This confirms a **serious vulnerability**, since credentials can be intercepted easily.

---

## Tools Used
- **Wireshark**  
- **Kali Linux**

---

## Conclusion
The exercise highlights the risks of transmitting sensitive information over **unencrypted HTTP**.

**To prevent such attacks:**  
- Use **HTTPS/TLS encryption**  
- Implement **secure authentication mechanisms**
