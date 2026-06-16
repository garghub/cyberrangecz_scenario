### Scenario: Coinminer Incident Response

**INFO_LEVEL:**
The organization has detected unusual CPU usage on several Linux servers. Initial investigation suggests a possible coinminer infection. Your task is to investigate, analyze, and respond to this incident.

**ACCESS_LEVEL:**
- Entry host: `miner-host`
- Username: `cyrano`
- Password: `cyrano`
- Access method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious service causing abnormal CPU usage.
**Description:** Investigate the `miner-host` to identify the suspicious service responsible for the high CPU usage.
**Hint:** Check running services and their resource usage.
**Flag:** `sys-monitor`

**TRAINING_LEVEL 2:**
**Task:** Identify the malware dropper artifact.
**Description:** Locate the file used by the attacker to drop the malware on the `miner-host`.
**Hint:** Check the `/tmp` directory for suspicious files.
**Flag:** `/tmp/ofd`

**TRAINING_LEVEL 3:**
**Task:** Identify the persistence mechanism through a system service.
**Description:** Investigate the persistence mechanism used by the malware on the `miner-host`.
**Hint:** Check the systemd services.
**Flag:** `sys-monitor.service`

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and file paths within the sandbox environment. The tasks focus on identifying and investigating the coinminer infection, ensuring alignment with the Incident Response security profile.