# Security Assessment Report - Mediroza General Hospital

**Target:** https://medirozahospital.com

**Date:** 27 November 2026

**Tester:** Siddhartha Gautam

**Batch:** B084 - NETWORKWALKS Cybersecurity Internship

**Scope:** Black-box Assessment - Simulated Target

**Status:** Findings Only - No Fixes Applied

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
- `Zenmap / Nmap` - Network Scanning

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
