### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
The scenario simulates a Mirai botnet infection targeting Realtek & Huawei routers. The botnet uses new TABLE encoder and aims devices with default telnet passwords to perform DDoS attacks. Your task is to investigate and respond to this incident.

**ACCESS_LEVEL:**
- Entry Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service on bot1.
**Description:** Investigate the system services on bot1 to identify any suspicious beacon service that might be communicating with a command-and-control server.
**Hint:** Check the systemd services and look for any unusual service names or descriptions.
**Flag:** bot-beacon-Hilix.sh.service

**TRAINING_LEVEL 2:**
**Task:** Identify the suspicious flood service on bot1.
**Description:** Investigate the system services on bot1 to identify any suspicious flood service that might be performing DDoS attacks.
**Hint:** Check the systemd services and look for any unusual service names or descriptions.
**Flag:** bot-flood-Hilix.sh.service

**TRAINING_LEVEL 3:**
**Task:** Identify the persistence mechanism on bot1.
**Description:** Investigate the system services on bot1 to identify any persistence mechanisms that might be used to maintain the botnet's presence on the system.
**Hint:** Check the systemd services and timers for any unusual entries.
**Flag:** system-update-checker.timer

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to investigate and respond to a Mirai botnet infection, focusing on identifying suspicious services and persistence mechanisms. The scenario adheres to the sandbox alignment rules and strictly uses indicators and artifacts derived from the provided data.