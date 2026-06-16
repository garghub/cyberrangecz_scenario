### Scenario: Okiru Worm Investigation

**INFO_LEVEL:**
The Okiru worm, a variant of the Mirai malware family, has been detected in your network. This worm targets IoT devices and uses exploits to propagate itself by scanning for vulnerable devices and compromising them. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: patient-zero
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious scheduled task/timer created by the worm.
**Description:** The Okiru worm creates a scheduled task/timer for persistence. Investigate the systemd timers on patient-zero to find the suspicious timer.
**Hint:** Look for timers in the /etc/systemd/system/ directory.
**Flag:** sysnet-monitor.timer

**TRAINING_LEVEL 2:**
**Task:** Identify the hidden malware directory used by the worm.
**Description:** The Okiru worm creates a hidden directory to store its files. Search the filesystem on patient-zero for suspicious directories.
**Hint:** Check directories in /opt/ for any unusual names.
**Flag:** /opt/.worm

**TRAINING_LEVEL 3:**
**Task:** Identify the beaconing mechanism used by the worm.
**Description:** The Okiru worm communicates with a command and control (C2) server. Investigate the scripts in the hidden malware directory on patient-zero to find the beaconing mechanism.
**Hint:** Look for scripts that make network connections.
**Flag:** /opt/.worm/beacon.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through identifying key components of the Okiru worm infection, ensuring a comprehensive understanding of the malware's behavior and persistence mechanisms.