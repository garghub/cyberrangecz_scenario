### Scenario: Mirai Botnet Investigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a Mirai botnet infection on your organization's network. The malware, specifically the Linux/Mirai-Hilix variant, targets Realtek and Huawei routers. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify suspicious beacon and flood services.
- Investigate persistence mechanisms.
- Contain C2 communication and flooding activities.

**Prerequisites:**
- Basic knowledge of Linux commands.
- Familiarity with network security concepts.
- Understanding of incident response procedures.

**Scenario Duration:** 60 minutes

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Beacon Service

**Description:**
Investigate the suspicious beacon service running on bot1. This service is communicating with a known C2 server.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious beacon service named `bot-beacon-Hilix.x86.service`.
4. Examine the service details using `systemctl status bot-beacon-Hilix.x86.service`.

**Flag:** bot-beacon-Hilix.x86.service

**Validation:**
The flag should be the name of the suspicious beacon service.

**Hint:**
Look for services with unusual names or those that are not part of the standard system services.

#### TRAINING_LEVEL 2
**Task:** Identify Suspicious Flood Service

**Description:**
Investigate the suspicious flood service running on bot1. This service is responsible for performing DDoS attacks.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using `systemctl list-units --type=service`.
3. Identify the suspicious flood service named `bot-flood-Hilix.x86.service`.
4. Examine the service details using `systemctl status bot-flood-Hilix.x86.service`.

**Flag:** bot-flood-Hilix.x86.service

**Validation:**
The flag should be the name of the suspicious flood service.

**Hint:**
Look for services that are not part of the standard system services and have unusual names.

#### TRAINING_LEVEL 3
**Task:** Contain C2 Communication

**Description:**
Contain the C2 communication by blocking the suspicious port used by the beacon service.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. Identify the port used by the beacon service (44382).
3. Use `iptables` to block outgoing traffic on port 44382.
4. Verify the block using `iptables -L`.

**Flag:** 44382

**Validation:**
The flag should be the port number used by the beacon service.

**Hint:**
Use `netstat` or `ss` to identify the port used by the beacon service.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. Each task is mapped to real hosts, services, and artifacts within the sandbox environment.