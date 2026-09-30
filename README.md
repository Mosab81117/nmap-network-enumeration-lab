
# Nmap Network Enumeration & Vulnerability Assessment

## Project Overview

This project demonstrates a complete network enumeration and
vulnerability assessment performed using Nmap against a
Metasploitable 2 virtual machine in a controlled VMware lab
environment.

The assessment covers host discovery, port scanning, service
and version detection, operating system detection, and
vulnerability assessment using Nmap NSE scripts.

## Lab Environment

| Component | Details |
|---|---|
| Scanner | Kali Linux |
| Scanner IP | `192.168.6.128` |
| Target | Metasploitable 2 |
| Target IP | `192.168.6.139` |
| Network | `192.168.6.0/24` |
| Tool | Nmap 7.99 |
| Environment | VMware |

## Assessment Workflow

The assessment followed these stages:

1. Connectivity Testing
2. Host Discovery
3. Port Scanning
4. Service and Version Detection
5. Operating System Detection
6. Vulnerability Assessment
7. Security Findings
8. Remediation Recommendations
9. Final Security Report

## Commands Used

### Connectivity Test

```bash
ping -c 4 192.168.6.139
````

### Host Discovery

```bash
nmap -sn 192.168.6.0/24
```

### Port Scan

```bash
nmap 192.168.6.139
```

### Service and Version Detection

```bash
nmap -sV 192.168.6.139
```

### OS Detection

```bash
nmap -O 192.168.6.139
```

### Vulnerability Scan

```bash
nmap --script vuln 192.168.6.139
```

## Key Results

The host discovery scan identified 5 active hosts within the
`192.168.6.0/24` network.

The port scan identified 23 open TCP ports on the Metasploitable 2
target.

Service and version detection identified multiple services,
including FTP, SSH, Telnet, SMTP, DNS, HTTP, SMB, MySQL,
PostgreSQL, VNC, IRC, AJP13, and HTTP/Tomcat.

OS detection identified the target as a Linux 2.6.x system.

The vulnerability assessment identified multiple security
weaknesses across the target services.

## Vulnerability Findings

The main findings documented in this project include:

* vsFTPd 2.3.4 Backdoor — CVE-2011-2523
* Anonymous Diffie-Hellman / Logjam — CVE-2015-4000
* SSL POODLE — CVE-2014-3566
* Slowloris — CVE-2007-6750
* RMI Registry Remote Code Execution
* PostgreSQL SSL/TLS weaknesses
* UnrealIRCd Backdoor indication
* HTTP Session Cookie Security issue

Detailed vulnerability descriptions, evidence, impact, and
remediation recommendations are available in:

`findings/vulnerability-findings.md`

## Project Structure

```text
nmap-network-enumeration-lab/
│
├── README.md
│
├── scans/
│   ├── host-discovery.txt
│   ├── port-scan.txt
│   ├── service-version.txt
│   ├── os-detection.txt
│   └── vulnerability-scan.txt
│
├── screenshots/
│   ├── 01-kali-ip.png
│   ├── 02-target-ip.png
│   ├── 03-ping.png
│   ├── 04-host-discovery.png
│   ├── 05-port-scan.png
│   ├── 06-service-version.png
│   ├── 07-os-detection.png
│   └── 08-vulnerability-scan.png
│
├── findings/
│   ├── README.md
│   └── vulnerability-findings.md
│
└── report/
    ├── README.md
    └── Nmap-Network-Enumeration-Report.pdf
```

## Evidence

The `screenshots/` directory contains visual evidence of the
network configuration, connectivity test, host discovery, port
scan, service enumeration, OS detection, and vulnerability scan.

The `scans/` directory contains the raw Nmap output files.

## Final Report

The complete security assessment report is available in:

`report/Nmap-Network-Enumeration-Report.pdf`

## Conclusion

This project demonstrates a complete Nmap-based network
enumeration and vulnerability assessment workflow in a controlled
lab environment.

The assessment progressed from network discovery to service
enumeration, OS detection, vulnerability identification, evidence
collection, and remediation recommendations.

> This project was performed in an authorized and controlled
> laboratory environment for educational and security-testing
> purposes.

