# Security Assessment Report - Mediroza General Hospital

**Target:** https://medirozahospital.com

**Date:** 27 November 2026

**Tester:** Siddhartha Gautam

**Batch:** B084 - NETWORKWALKS Cybersecurity Internship

**Scope:** Black-box Assessment - Simulated Target

**Status:** Findings Only - No Fixes Applied

## 1. Introduction

VAPT was performed on `medirozahospital.com` as part of the Week 4 capstone project.

During which I found a total of **9 findings** in which **3 CRITICAL** issues related to exposed sensitive directories, exposed database backup, and SQL Injection were thoroughly observed.

It was also found that the website uses a custom CMS `Mediroza CMS 1.4.2` on a `LiteSpeed` server. 

P1 level impact was achieved during **M3 - Sensitive Data Exposure**. Here, an old database backup file was publicly downloaded from the `/old/` directory, exposing confidential staff salaries and shareholder records.

---
