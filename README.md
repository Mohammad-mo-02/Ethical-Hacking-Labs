# Ethical Hacking & Penetration Testing Portfolio  
### Postgraduate Offensive Security Laboratory

---

## Executive Technical Overview

This repository presents a structured Ethical Hacking and Penetration Testing portfolio completed as part of a postgraduate cybersecurity programme. All practical assessments were conducted within legally authorised sandbox environments provided by TryHackMe, ensuring full compliance with ethical and legal standards.

The objective of this project was not merely to execute isolated attacks, but to demonstrate a complete offensive security workflow aligned with recognised industry methodologies, including:

- NIST SP 800-115 – Technical Guide to Information Security Testing and Assessment  
- OWASP Top 10 (2021) – Web Application Risk Classification  
- MITRE CWE Framework – Vulnerability Taxonomy  

Each practical task followed a structured penetration testing lifecycle:

Reconnaissance → Enumeration → Exploitation Attempt → Vulnerability Classification → Impact Analysis → Mitigation Mapping

No unauthorised infrastructure was targeted. All exploitation was confined to controlled laboratory environments.

This portfolio demonstrates applied offensive capability, structured methodology, defensive awareness, and professional documentation standards.

---

# Offensive Security Competencies Demonstrated

- Structured reconnaissance and service enumeration  
- Manual and automated SQL injection testing  
- Password attack methodology using John the Ripper  
- Payload generation using MSFvenom  
- Reverse shell handler configuration via Metasploit Framework  
- Network packet capture and credential extraction using Wireshark  
- Service fingerprinting and vulnerability scanning using Nmap  
- Vulnerability classification via CWE and OWASP  
- CIA triad impact modelling  
- Structured mitigation and defensive control mapping  
- Ethical boundary enforcement and responsible disclosure awareness  

---

# Testing Environment Architecture

All testing activities were conducted within cloud-based lab environments to ensure:

- Legal compliance  
- Controlled exploitation boundaries  
- Reproducibility  
- Isolation from production infrastructure  

## Attacker Environment

Kali Linux-based attack box with access to:

- Nmap – service discovery and enumeration  
- sqlmap – automated SQL injection testing  
- Metasploit Framework – exploitation and handler configuration  
- MSFvenom – payload generation  
- Wireshark – packet capture and protocol inspection  
- John the Ripper – password cracking simulation  

## Target Environments

- DVWA (Damn Vulnerable Web Application)  
- Windows sandbox systems  
- Simulated FTP/HTTP network services  
- Public infrastructure reconnaissance simulation (Oracle case study)  

---

# Domain I — Web Application Exploitation (SQL Injection)

## Objective

To identify and exploit injection vulnerabilities within a controlled web application environment and assess their security impact.

## Methodology

1. Service enumeration using Nmap  
2. Manual payload injection testing  
3. Automated testing using sqlmap  
4. Vulnerability classification (CWE-89)  
5. Impact modelling (CIA triad)  
6. Mitigation strategy design  

## Key Findings

- Input fields accepted unsanitised user input  
- Authentication bypass achieved using logical injection payloads  
- Backend database interaction confirmed via sqlmap automation  
- Vulnerability aligned with OWASP A03:2021 – Injection  
- Classified as CWE-89  

## Security Impact

If exploited in production, this vulnerability could result in:

- Data exfiltration  
- Credential compromise  
- Administrative privilege escalation  
- Regulatory non-compliance  

## Mitigation Mapping

- Parameterised queries / prepared statements  
- Input validation enforcement  
- Least privilege database accounts  
- Secure coding review processes  

---

# Domain II — Malware Payload Simulation & Reverse Shell Infrastructure

## Objective

To simulate attacker payload creation and remote access establishment in order to understand early-stage compromise mechanics.

## Payload Generation

Using MSFvenom:

- windows/meterpreter/reverse_tcp payload  
- Custom LHOST and LPORT configuration  
- Executable binary generation  

## Listener Configuration

Using Metasploit multi/handler:

- Payload matching  
- Reverse TCP listener activation  
- Session establishment simulation  

## Vulnerability Classification

- CWE-434 – Unrestricted Upload of File with Dangerous Type  
- Improper execution control weaknesses  

## Security Impact

Successful exploitation would allow:

- Remote command execution  
- File system manipulation  
- Persistence installation  
- Lateral movement capability  

## Defensive Controls

- Endpoint Detection & Response (EDR)  
- Application whitelisting  
- Antivirus with behavioural analysis  
- Restricted execution policies  

---

# Domain III — Network Traffic Interception & Protocol Weakness Analysis

## Objective

To demonstrate how plaintext protocol usage enables credential interception.

## Methodology

- Packet capture using Wireshark  
- FTP protocol filtering  
- Credential extraction from captured traffic  

## Key Finding

FTP authentication credentials transmitted in plaintext.

## Vulnerability Classification

- CWE-319 – Cleartext Transmission of Sensitive Information  
- OWASP A02:2021 – Cryptographic Failures  

## Security Impact

- Credential theft  
- Privilege escalation  
- Lateral network movement  
- Business continuity disruption  

## Mitigation Strategy

- Replace FTP with SFTP/FTPS  
- Replace Telnet with SSH  
- Enforce HTTPS across services  
- Deploy VPN encryption  
- Implement IDS monitoring  

---

# Extended Offensive Modules (TryHackMe)

Beyond the core domains, this portfolio includes additional practical exposure through structured TryHackMe modules:

- Host enumeration  
- Password cracking using John the Ripper  
- Service fingerprinting  
- Banner grabbing  
- Exploit selection validation  
- Failed exploitation handling and correction  
- Reconnaissance automation  
- Certificate transparency analysis  

These exercises reinforced structured methodology rather than tool-centric execution.

---

# Bug Bounty Reconnaissance Simulation

A passive reconnaissance case study was conducted targeting publicly available infrastructure associated with Oracle Corporation under responsible disclosure boundaries.

## Tools Used

- WHOIS lookup  
- crt.sh certificate transparency search  
- SecurityHeaders analysis  
- Shodan exposure enumeration  

## Key Observations

- Multiple subdomain exposures  
- Missing HTTP security headers  
- Public service fingerprinting  
- Defensive infrastructure detection (Akamai edge protection)  

No intrusive scanning or exploitation was performed.

This demonstrates understanding of:

- Attack surface mapping  
- Passive reconnaissance strategy  
- Responsible disclosure ethics  
- Enterprise exposure assessment  

---

# Ethical & Legal Compliance

All testing adhered to:

- Controlled lab boundaries  
- Educational licensing terms  
- Responsible disclosure principles  
- No real-world unauthorised exploitation  

Activities were aligned with NIST SP 800-115 testing methodology and recognised ethical hacking standards.

---

# Strategic Value of This Portfolio

This repository demonstrates:

- Offensive capability grounded in structured methodology  
- Technical tool fluency  
- Vulnerability classification literacy  
- Defensive remediation awareness  
- Ethical boundary discipline  
- Professional documentation standards  

---

# Supporting Documentation

The full academic report, technical evidence, packet captures, and structured appendices are included within this repository.

---
