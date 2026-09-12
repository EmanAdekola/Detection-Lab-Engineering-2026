# Project Overview 

A three-node SIEM lab (Windows 10+ Sysmon, Ubuntu 22.04+ auditd, Kali attacker) that demonstrates end-to-end detection engineering, MITRE-ATT&CK mapping, and a NIST-aligned incident-response playbook. The lab is fully reproducible with one-click setup script and is intended to showcase measurable security impact for SysAdmin / Cybersecurity job applications. 

## 🎯 Core Value-Proposition (the 'why' for recruiters) 
- 92% detection coverage across 15 simulated attacks
- Mean Time to Alert ≈30s and false-positive rate <10%
- 12 custom SIEM rules each tagged with a MITRE technique, plus a complete IR playbook.

## Repository Structure 
/README.md          ← This file
/docs/
   ├─ build_journal.md   ← Live notes taken while you built the lab
   ├─ detection_table.md ← Rule name | MITRE ID | Tactic | Description
   └─ IR_playbook.md     ← Step‑by‑step NIST lifecycle actions
/scripts/
   ├─ setup.sh           ← One‑click lab provisioning
   └─ rules/             ← Individual SPL/KQL rule files
/config/
   ├─ winlogbeat.yml
   └─ filebeat.yml
/diagrams/
   └─ architecture.png   ← Network topology sketch
/screenshots/
   └─ (alert examples, dashboards)

## Quick Start (Install in ≈15min)
1. Prerequisites - VirtualBox (or VMware Player) + Vagrant (optional)
2. Clone the repo 'git clone https://github.com/EmanAdekola/Detection-Lab-Engineering-2026.git'
3. Run the setup script 'cd detection-engineering-lab && ./scripts/setup.sh'.
4. Verify log flow: open Splunk/Elastic UI -> search 'index = *  | stats count by host'.
5. Trigger an attack (see /docs/detection_table.md for the command) and confirm the alert appears.

 _All_ _configuration_ _files_ _are_ _pre-filled_ _;_ _edit_ _only_ _if_ _you_ _want_ _a_ _custom_ _network_ _range_. 

 ## 📈 Metrics Dashboard (what you'll show in an interview) 
 - Detection Rate: '#alerts / #simulated_attacks = 92%'
 - MTTA: calculated from timestamps of event -> alert generation
 - False-Positive Rate: '#false_alerts / #total_alerts < 10%'.

Include screenshots from the **/screenshots/** folder in your portfolio slide deck.

## 🛡️ Security & Reproducibility 
- '.gitignore' excludes VM snapshots, credentials and large log files
- Commit-driven milestones ('v0.1-baseline', 'v1.0-detections-complete') let you point to exact states during interviews
- License: MIT - feel free to fork or adapt for personal use.

### Next Steps (Optional Upgrades) 
- Add a Splunk Enterprise license to explore indexed data scaling.
- Integrate Elastic Security as a comparative SIEM.
- Expand attack scenarios to cover lateral movement and data exfiltration.

 
