# Task 3 — Basic Vulnerability Scan on Personal Computer

## Objective
Perform a vulnerability assessment on a personal Ubuntu machine using Nmap to identify, document, and remediate common security vulnerabilities.

## Tools Used
- **Nmap 7.94SVN** — Network scanner with NSE vulnerability scripts
- **OS:** Ubuntu 24.04 (Aspire AS15-42)

## Why Nmap instead of Nessus/OpenVAS?
Nmap with `--script vuln` performs equivalent vulnerability detection using its built-in NSE (Nmap Scripting Engine) scripts. It detects CVEs, misconfigurations, and service vulnerabilities — same core objective, zero installation overhead.

---

## Steps Performed

### 1. Identified open ports and running services
```bash
ss -tulnp
```
Found two services running without user awareness:
- **MySQL 8.0.46** on port 3306
- **CUPS 2.4** (printer service) on port 631

### 2. Ran full vulnerability scan
```bash
sudo nmap -sV --script vuln 127.0.0.1 -oN vuln-report.txt
```

### 3. Reviewed findings
- Found 3 vulnerabilities on CUPS service
- MySQL had only informational findings (CVSS 0.0)

### 4. Applied fixes
- Stopped and disabled CUPS service
- Blocked port 631 via UFW firewall
- Stopped and disabled MySQL service

### 5. Verified fixes with rescan
```bash
sudo nmap -sV --script vuln 127.0.0.1 -oN final-report.txt
```
Result: **0 open ports — fully hardened**

---

## Scan Results Summary

| Vulnerability | Severity | Service | Status |
|---|---|---|---|
| CVE-2024-47850 | High (CVSS 7.5) | CUPS 2.4 | ✅ Fixed |
| HTTP Verb Tampering | High | CUPS 2.4 | ✅ Fixed |
| Slowloris DOS (CVE-2007-6750) | Medium | CUPS 2.4 | ✅ Fixed |
| MySQL info (NODEJS:602) | Low (CVSS 0.0) | MySQL 8.0.46 | ✅ Fixed |

---

## Key Concepts Learned
- **Vulnerability Scanning** — Automated detection of known security weaknesses
- **CVE** — Common Vulnerabilities and Exposures (unique ID per vulnerability)
- **CVSS** — Common Vulnerability Scoring System (0-10 severity scale)
- **Attack Surface Reduction** — Disabling unused services removes potential entry points
- **Defense in Depth** — Applied 3 layers of protection (stop + disable + firewall)
- **False Positives** — Admin folder findings were scanner noise, not real vulnerabilities

## Repository Structure
```
task3-vulnerability-scan/
├── README.md
├── reports/
│   ├── vuln-report.txt      ← Initial scan with vulnerabilities
│   └── final-report.txt     ← Final scan showing 0 open ports
└── screenshots/
    ├── scan-results.png
    ├── cups-disabled.png
    └── final-clean-scan.png
```
