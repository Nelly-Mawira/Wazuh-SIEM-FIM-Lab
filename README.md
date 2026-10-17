# Enterprise SIEM Deployment & File Integrity Monitoring (FIM) Lab

## Executive Summary
This project demonstrates the deployment, configuration, and operational validation of an enterprise-grade Security Information and Event Management (SIEM) solution using **Wazuh v4.9.0** hosted on Ubuntu Linux via Docker Compose. The lab simulates host-based intrusion detection and real-time File Integrity Monitoring (FIM) to detect unauthorized system modifications and sensitive file tampering.

---

## Technical Architecture & Topology
- **Host OS:** Ubuntu Linux
- **Deployment Model:** Single-Node Containerized Stack via Docker Compose
  - `wazuh.manager`: Core correlation engine and ruleset processing
  - `wazuh.indexer`: High-performance search and analytics database
  - `wazuh.dashboard`: Security visualization and alert management web interface (`https://localhost`)
- **Endpoint Agent:** `ubuntu-host` (Wazuh Agent enrolled via `127.0.0.1`)

---

## MITRE ATT&CK Framework Mapping
- **Tactics:**
  - **TA0007:** Discovery
  - **TA0005:** Defense Evasion / Data Tampering
- **Techniques:**
  - **T1083:** File and Directory Discovery
  - **T1565.001:** Data Manipulation - File Modification

---

## Key Implementation Steps

### 1. SIEM Stack Deployment
Containerized cluster instantiated using Docker Compose:
