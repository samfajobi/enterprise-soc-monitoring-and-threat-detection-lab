# Enterprise SOC Monitoring Project

## Overview
This project simulates a real-world **Enterprise Security Operations Center (SOC)** environment focused on centralized logging, threat detection, alerting, and incident response.

The goal of this project is to demonstrate **SOC analyst skills** such as:
- Log collection and correlation
- Detection engineering
- Incident investigation
- Security monitoring across identity, endpoint, and network layers
- Documentation and operational thinking

The environment mirrors how a small-to-medium enterprise SOC operates using industry-relevant tools and workflows.

---

## Objectives
- Build an enterprise-style SOC monitoring environment
- Collect and analyze logs from multiple security data sources
- Create meaningful detections for common attack techniques
- Simulate SOC alert → investigation → response workflows
- Document detections, incidents, and lessons learned

---

## SOC Architecture

The lab environment consists of the following components:

- **Active Directory Domain Controller**
  - Centralized identity management
  - Authentication and authorization logging

- **Windows 10 Endpoint**
  - User workstation
  - Endpoint activity monitoring

- **pfSense Firewall**
  - Network traffic inspection
  - North-south and east-west traffic visibility

- **Splunk (SIEM)**
  - Centralized log ingestion
  - Detection, alerting, and dashboards

- **Kali Linux**
  - Used to generate security-relevant events for detection validation
  - No offensive focus; used strictly for defensive simulation

All logs are forwarded and correlated within Splunk to replicate a real SOC monitoring workflow.

---

## Data Sources
This project collects and analyzes logs from the following sources:

- **Active Directory**
  - Authentication events
  - Account and group management changes
  - Privilege escalation activity




