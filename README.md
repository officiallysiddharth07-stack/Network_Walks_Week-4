# Security Assessment Report - Mediroza General Hospital

**Target:** https://medirozahospital.com

**Date:** 27 November 2026

**Tester:** Siddhartha Gautam

**Batch:** B084 - NETWORKWALKS Cybersecurity Internship

**Scope:** Black-box Assessment - Simulated Target

**Status:** Findings Only - No Fixes Applied

## 1. Introduction

A black-box security assessment was performed on `medirozahospital.com` as part of the Week 4 capstone project.

A total of **9 findings** were identified, including **3 CRITICAL** issues related to exposed sensitive directories, exposed database backup, and SQL Injection.

The website uses a custom CMS `Mediroza CMS 1.4.2` on a `LiteSpeed` server. 

The most severe impact was achieved during **M3 - Sensitive Data Exposure**, where an old database backup file was publicly downloaded from the `/old/` directory, exposing confidential staff salaries and shareholder records.

---
