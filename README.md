# Penetration Testing Report - Mediroza General Hospital

**Target:** https://medirozahospital.com

**Date:** 27 November 2026

**Tester:** Siddhartha Gautam

**Batch:** B084 - NETWORKWALKS Cybersecurity Internship


## 1. Security Assessment

VAPT was performed on `medirozahospital.com` as part of the Week 4 capstone project.

During which I found a total of **9 findings** in which **3 CRITICAL** issues related to exposed sensitive directories, exposed database backup, and SQL Injection were thoroughly observed.

It was also found that the website uses a custom CMS `Mediroza CMS 1.4.2` on a `LiteSpeed` server. 

P1 level impact was achieved during **M3 - Sensitive Data Exposure**. Here, an old database backup file was publicly downloaded from the `/old/` directory, exposing confidential staff salaries and shareholder records.

---

## 2. Methodology & Tools Used

**M1 - Initial Access / Reconnaissance:**
- `whois` - Domain Registration Info
- `curl` - Header & Response Analysis
- `wafw00f` - WAF Detection
- `whatweb` - Technology Fingerprinting
- `subfinder` - Subdomain finding
- `Zenmap / Nmap` - Network Scanning (Several ports open at 199.188.201.16)

**M1 - Authentication Bypass:**
- SQL Injection Testing - Patient Portal Login

**M2 - Cracking / Post-Exploitation:**
- PDF Hash Extraction & Password Cracking - Patient Reports (NetworkWalk Tools Used)

**M3 - Sensitive Data Exposure:**
- Directory Enumeration - Gobuster - `/old/` Directory Discovery
- Database Backup Analysis - `.sql` File Review
- Staff Salaries Extraction
- Shareholder Details Extraction

All tests performed were under supervision and done for learning purposes only.

---
## 3. Evidences

1. WHOIS
![WHOIS](./whois.png)

2. WHOIS 2
![WHOIS 2](./whois2.png)

3. WhatWeb
![WhatWeb](./whatweb.png)

4. WAFW00F
![WAFW00F](./wafw00f.png)

5. Subfinder
![Subfinder](./subfinder.png)

6. Curl
![Curl](./curl.png)

7. Mediroza Old
![Mediroza Old](./mediroza-old.png)

8. Mediroza Staff
![Mediroza Staff](./mediroza-staff.png)

9. Database
![Database](./database.png)

10. SQL Injection 1
![SQL Injection 1](./sqli-1.png)

11. SQL Injection 2
![SQL Injection 2](./sqli-2.png)

12. PDF 1
![PDF 1](./pdf1.png)

13. PDF 2
![PDF 2](./pdf2.png)

14. Nmap 1
![Nmap 1](./nmap1.png)

15. Nmap 2
![Nmap 2](./nmap2.png)

16. Nmap 3
![Nmap 3](./nmap3.png)

17. Nmap 4
![Nmap 4](./nmap4.png)

## 4. Privacy Violation and Major Threat
**PDF Cracking Analysis:**
All 3 PDFs were password-protected. Hashes were extracted and cracked successfully, proving weak passwords were used for sensitive medical reports.

- PDF 1 - Password cracked: `123456`
- PDF 2 - Password cracked: `password`
- PDF 3 - Password cracked: `!@#$%^&`

After cracking, decrypted patient content was exposed, confirming patient privacy violation.

**Risk:** Patient reports are publicly downloadable. Exposure of medical reports violates patient privacy.

**Recommendation:** Remove public access to patient reports. Protect PDFs with strong passwords and proper access control.

## 5. Conclusion Remarks
This final assessment marks the ending of my one month online internship at Network Walks Pvt. Ltd.<br>
The main priority is to fix Directory Indexing, Database Backup Exposure , and SQL Injection immediately, as they expose hospital internal directories, allow login bypass, and expose a full confidential database backup.<br><br>
With that asserted, I've learned quite great techniques of VAPT from this internship.
