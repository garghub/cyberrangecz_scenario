### Scenario: Mirai Botnet Investigation

**INFO_LEVEL:**
- **Scenario Title:** Mirai Botnet Investigation
- **Scenario Description:** You are an incident responder tasked with investigating a Mirai botnet infection targeting Realtek and Huawei routers. The botnet is using a new TABLE encoder and has been observed communicating with a command-and-control (C2) server. Your goal is to identify and mitigate the threat.
- **Learning Objectives:**
  - Identify suspicious beacon and flood services.
  - Investigate persistence mechanisms.
  - Contain C2 communication and flooding activities.
- **Prerequisites:**
  - Basic knowledge of Linux commands.
  - Familiarity with network security concepts.
  - Understanding of botnet behavior and mitigation techniques.

**ACCESS_LEVEL:**
- **Entry Host:** bot1
- **Username:** cyrano
- **Password:** cyrano
- **Access Method:** SSH
- **Privilege Boundaries:** User-level access on bot1, ability to SSH to bot2.

**TRAINING_LEVEL 1:**
- **Task:** Identify the suspicious beacon service.
- **Description:** Investigate the services running on bot1 and identify the suspicious beacon service used by the Mirai botnet.
- **Hint:** Look for services related to system health or updates.
- **Flag:** bot-beacon-Hilix.x86.elf.service

**TRAINING_LEVEL 2:**
- **Task:** Investigate the persistence mechanism.
- **Description:** Examine the systemd services on bot1 to identify and remove the persistence mechanism used by the Mirai botnet.
- **Hint:** Check for services disguised as system updaters.
- **Flag:** system-update-checker.timer

**TRAINING_LEVEL 3:**
- **Task:** Contain the C2 communication.
- **Description:** Identify the C2 server IP and port used by the beacon service and block the communication to prevent further commands from being received.
- **Hint:** Check the beacon script for the C2 server details.
- **Flag:** 2222

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the user through identifying, investigating, and mitigating the Mirai botnet threat within the sandbox environment.