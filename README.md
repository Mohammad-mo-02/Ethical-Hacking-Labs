# Ethical Hacking & Penetration Testing Portfolio  
### Postgraduate Offensive Security Laboratory

---

## Executive Statement

This repository documents a structured series of offensive security assessments conducted within legally authorised sandbox environments, primarily through TryHackMe laboratories and controlled virtualised infrastructure.

The objective of this body of work was not merely to execute exploitation techniques, but to demonstrate the disciplined application of formal penetration testing methodology. Each engagement was approached as a simulated real-world security assessment, integrating technical execution with vulnerability classification, impact modelling, and defensive remediation strategy.

All activities were conducted in isolated educational environments. No unauthorised systems were targeted.

---

## Testing Philosophy & Threat Model

All practical exercises were conducted using a structured black-box testing perspective unless explicitly stated otherwise. This simulated an external threat actor with no prior credentials or internal knowledge of the target environment.

The methodology applied throughout aligns with principles from:

- NIST SP 800-115 (Technical Guide to Information Security Testing)
- OWASP Top 10 (2021)
- MITRE CWE Vulnerability Classification Framework

Each task followed a consistent lifecycle:

Reconnaissance → Enumeration → Exploitation Attempt → Validation → Vulnerability Classification → Impact Assessment → Mitigation Strategy

This ensured technical activity remained analytically grounded and defensively contextualised.

---

# Domain I — Web Application Exploitation (SQL Injection)

## Objective

To assess input validation weaknesses within a controlled web application environment and evaluate the systemic risk posed by injection vulnerabilities.

## Methodological Approach

Initial reconnaissance and service enumeration were conducted using Nmap to identify exposed web services and potential entry points. Manual payload testing was performed to validate injection behaviour before automation was introduced via sqlmap.

This staged approach ensured understanding preceded automation, preventing tool dependency and reinforcing vulnerability comprehension.

## Technical Findings

The target application accepted unsanitised user input within authentication and query parameters. Logical injection payloads successfully bypassed authentication controls, demonstrating backend database interaction.

Automated enumeration confirmed database schema accessibility under certain conditions.

The vulnerability aligns with:

- CWE-89 — SQL Injection
- OWASP A03:2021 — Injection

## Risk & Operational Impact

In a production environment, this class of vulnerability can facilitate:

- Credential harvesting  
- Sensitive data exfiltration  
- Privilege escalation  
- Regulatory exposure (GDPR implications in EU contexts)  

Injection flaws are particularly severe because they collapse trust boundaries between user input and database execution layers.

## Defensive Remediation Strategy

Mitigation requires systemic correction rather than surface filtering. Recommended controls include:

- Parameterised queries and prepared statements  
- Strict input validation and output encoding  
- Principle of least privilege at the database layer  
- Secure development lifecycle integration  

This exercise reinforced how minor validation oversights can escalate into systemic compromise.

---

# Domain II — Payload Generation & Remote Access Simulation

## Objective

To simulate the mechanics of initial compromise through payload generation and controlled reverse shell establishment, demonstrating how endpoint weaknesses can lead to remote command execution.

## Technical Execution

Using MSFvenom, a reverse TCP payload was generated with defined LHOST and LPORT parameters. A corresponding listener was configured via the Metasploit Framework multi/handler module.

Upon simulated execution within the sandbox environment, a session was successfully established, enabling controlled command interaction.

## Vulnerability Context

This scenario models weaknesses such as:

- Unrestricted file upload (CWE-434)  
- Inadequate execution controls  
- Insufficient endpoint protection  

The focus was not on bypassing enterprise-grade EDR, but on understanding compromise mechanics at a foundational level.

## Operational Impact

In real-world scenarios, successful reverse shell establishment enables:

- Persistent access  
- Privilege escalation  
- Lateral movement  
- Data staging for exfiltration  

The exercise highlighted the asymmetry between simple execution flaws and large-scale organisational risk.

## Defensive Countermeasures

Effective mitigation requires layered controls:

- Endpoint Detection & Response (EDR)  
- Application whitelisting  
- Execution policy enforcement  
- Network segmentation  
- Behavioural anomaly detection  

This reinforced the importance of defence-in-depth architecture.

---

# Domain III — Network Traffic Analysis & Protocol Weaknesses

## Objective

To analyse plaintext protocol behaviour and assess the risk posed by insecure service configurations.

## Methodology

Network traffic was captured and analysed using Wireshark. FTP authentication flows were inspected to determine whether credential material was transmitted securely.

## Key Observation

Authentication credentials were transmitted in plaintext within FTP sessions, allowing extraction directly from packet capture.

This vulnerability maps to:

- CWE-319 — Cleartext Transmission of Sensitive Information  
- OWASP A02:2021 — Cryptographic Failures  

## Risk Implications

Plaintext protocol usage remains common in legacy infrastructure and poorly segmented networks. In environments lacking encrypted transport layers, attackers positioned within the network can harvest credentials passively without triggering authentication alerts.

The risk multiplies in flat network architectures where credential reuse is common.

## Remediation Strategy

- Replace FTP with SFTP or FTPS  
- Replace Telnet with SSH  
- Enforce HTTPS across services  
- Implement TLS configuration hardening  
- Deploy intrusion detection monitoring  

This exercise demonstrated how configuration weaknesses often pose equal or greater risk than software flaws.

---

# Extended Offensive Modules

Additional laboratory exercises conducted via structured TryHackMe modules included:

- Service enumeration and fingerprinting  
- Password cracking using John the Ripper  
- Hash identification and attack strategy selection  
- Exploit research validation  
- Banner grabbing and version analysis  
- Controlled brute-force simulations  

These modules reinforced a critical principle: tools are secondary to methodology. Each exercise was treated as a miniature engagement rather than a checklist task.

---

# Passive Reconnaissance Case Study

A passive reconnaissance simulation was conducted against publicly available infrastructure belonging to Oracle Corporation. Only open-source intelligence techniques were used.

Activities included:

- WHOIS analysis  
- Certificate transparency search (crt.sh)  
- Security header inspection  
- Exposure enumeration via Shodan  

No intrusive scanning or exploitation was performed.

This case study demonstrated understanding of attack surface mapping, responsible disclosure boundaries, and enterprise exposure profiling without crossing ethical lines.

---

# Ethical Compliance

All assessments were conducted:

- Within authorised lab environments  
- Under educational licensing agreements  
- Without targeting live unauthorised systems  

The objective throughout was skill development, not exploitation.

---

# Strategic Competency Demonstrated

This portfolio reflects capability in:

- Structured penetration testing methodology  
- Technical exploitation fundamentals  
- Vulnerability classification literacy  
- Impact modelling using CIA triad principles  
- Defensive remediation mapping  
- Ethical boundary adherence  
- Analytical reporting discipline  

The work bridges offensive execution with defensive awareness, reflecting an understanding that penetration testing is ultimately a risk identification and mitigation discipline.

---


---

## Closing Reflection

Security weaknesses rarely exist in isolation. They emerge from misaligned validation, configuration drift, and insufficient architectural layering. Through structured laboratory assessment, this portfolio explores how seemingly small technical flaws can escalate into systemic compromise.

The emphasis throughout has been discipline, clarity, and defensible methodology.

---
