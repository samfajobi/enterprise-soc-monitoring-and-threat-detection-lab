# Splunk Enterprise SOC Monitoring Lab

This project demonstrates a **realistic enterprise Security Operations Center (SOC) monitoring environment** using **Splunk Enterprise**.  
It focuses on collecting, correlating, detecting, and investigating security events across **Windows endpoints, Active Directory, network firewalls (pfSense), and simulated attacks from Kali Linux**.

The lab is designed to showcase **SOC workflows**, **detection engineering**, and **incident response thinking**, rather than just tool installation.

---

## 🎯 Project Objectives

- Deploy Splunk Enterprise as a centralized SIEM
- Forward Windows Event Logs using Splunk Universal Forwarder
- Monitor Active Directory authentication and privilege activity
- Ingest and analyze pfSense firewall logs
- Simulate attacks using Kali Linux
- Create detections, dashboards, and alerts using SPL
- Apply SOC playbooks for investigation and response
- Map detections to MITRE ATT&CK

---

## 🏗️ Lab Architecture

### Components

| Component | Description |
|--------|------------|
| Splunk Enterprise | Central SIEM (Indexer + Search Head) |
| Windows Server | Active Directory Domain Controller |
| Windows Workstation | Domain-joined endpoint |
| Splunk Universal Forwarder | Log collection agent |
| pfSense Firewall | Network perimeter & firewall logs |
| Kali Linux | Attack simulation platform |

### Data Flow

Security events follow this pipeline:

1. **Data Sources**
   - Windows Endpoints
   - Active Directory Domain Controller
   - pfSense Firewall

2. **Log Collection**
   - Splunk Universal Forwarder collects and forwards logs

3. **SIEM Processing**
   - Splunk Enterprise indexes and processes events

4. **SOC Operations**
   - Correlation searches
   - Alert generation
   - Dashboards and investigations



---

## 🔍 Monitoring Scope

### Windows Endpoints
- Authentication successes and failures
- Account lockouts
- Privilege and group membership changes
- Process execution events

### Active Directory
- Domain logon activity
- Administrative account usage
- Privileged group modifications
- Suspicious authentication patterns

### pfSense Firewall
- Allowed and blocked traffic
- Port scanning indicators
- Suspicious inbound/outbound connections
- Network-based attack visibility

---

## ⚔️ Attack Simulation

Attacks are performed from **Kali Linux** to validate detections and SOC workflows.

Simulated scenarios include:
- Brute-force authentication attacks
- Credential abuse
- Lateral movement attempts
- Network scanning and enumeration

Each attack is:
- Observed in Splunk
- Correlated across multiple data sources
- Documented with detections and playbooks

---

## 🧠 SOC Use Cases Demonstrated

This lab reflects how a SOC operates in practice:

- Centralized log ingestion
- Event correlation across endpoint, identity, and network layers
- Alert triage and investigation
- Use of dashboards for situational awareness
- Application of incident response playbooks
- Understanding detection gaps and false positives

---

## 🚨 Detections & Alerting

Detection logic is written using **Splunk Processing Language (SPL)** and focuses on:

- Authentication attacks
- Brute-force activity
- Privilege escalation
- Suspicious administrative behavior
- Network-based threats

Detections are mapped to **MITRE ATT&CK techniques** to align with industry-standard threat models.

---


## 📘 Playbooks & Incident Response

Each detection is supported by a SOC playbook defining:

- Initial triage steps (Tier 1)
- Investigation actions (Tier 2)
- Escalation criteria
- Containment and response options
- Incident closure requirements

This demonstrates **structured and repeatable incident response**.

---

## 📊 Dashboards & Visualization

Custom dashboards are built to provide:
- Authentication activity overview
- Active Directory security posture
- Firewall traffic analysis
- Incident investigation context

Dashboards support **both monitoring and investigation**.

---

## 📌 Key Skills Demonstrated

- SIEM deployment and architecture
- Windows and Active Directory security monitoring
- Network firewall log analysis
- Detection engineering with SPL
- SOC alert triage and investigation
- Attack simulation and validation
- Incident response documentation
- MITRE ATT&CK mapping

---

## 🔚 Conclusion

This project represents a **practical enterprise SOC monitoring lab** using Splunk.  
It demonstrates not only how logs are collected, but **how a SOC thinks, detects, investigates, and responds to threats** across multiple layers of an environment.

---
