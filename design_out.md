### Scenario: Mirai Botnet Investigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation

**Scenario Description:**
You are an incident responder tasked with investigating a Mirai botnet infection targeting Realtek and Huawei routers. The malware variant, Linux/Mirai-Hilix, uses a new TABLE encoder and employs various DDoS attack methods. Your goal is to identify and mitigate the threat.

**Learning Objectives:**
- Identify and investigate suspicious beacon services.
- Detect and analyze DDoS attack methods.
- Mitigate the threat by containing C2 communication and blocking flooding.

**Prerequisites:**
- Basic knowledge of Linux commands.
- Familiarity with network security concepts.
- Understanding of botnet behavior and mitigation techniques.

**Scenario Duration:** 60 minutes

---

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify and investigate the suspicious beacon service.

**Description:**
The Mirai botnet uses a beacon service to communicate with its command-and-control (C2) server. Your task is to identify and investigate this suspicious beacon service on the infected host.

**Steps:**
1. Log in to the entry host `bot1` using SSH.
2. Investigate the running services using `systemctl list-units --type=service`.
3. Identify the suspicious beacon service named `bot-beacon-Hilix.sh.service`.
4. Examine the service details using `systemctl status bot-beacon-Hilix.sh.service`.
5. Check the beacon log file located at `/var/lib/.botcache/beacon.log`.

**Flag:** bot-beacon-Hilix.sh.service

**Validation:**
The flag should be the name of the suspicious beacon service.

**Hint:**
Use `systemctl list-units --type=service` to list all running services and look for any suspicious services related to the beacon.

---

#### TRAINING_LEVEL 2
**Task:** Identify and investigate the suspicious flood service.

**Description:**
The Mirai botnet is known to launch DDoS attacks using a flood service. Your task is to identify and investigate this suspicious flood service on the infected host.

**Steps:**
1. Continue working on the entry host `bot1`.
2. Investigate the running services using `systemctl list-units --type=service`.
3. Identify the suspicious flood service named `bot-flood-Hilix.sh.service`.
4. Examine the service details using `systemctl status bot-flood-Hilix.sh.service`.
5. Check the flood log file located at `/var/lib/.botcache/flood.log`.

**Flag:** bot-flood-Hilix.sh.service

**Validation:**
The flag should be the name of the suspicious flood service.

**Hint:**
Use `systemctl list-units --type=service` to list all running services and look for any suspicious services related to the flood.

---

#### TRAINING_LEVEL 3
**Task:** Contain the C2 communication by blocking the suspicious outbound port.

**Description:**
To mitigate the threat, you need to contain the C2 communication by blocking the suspicious outbound port used by the beacon service.

**Steps:**
1. Continue working on the entry host `bot1`.
2. Identify the suspicious outbound port used by the beacon service, which is `80`.
3. Use `iptables` to block outgoing traffic on port `80`.
4. Verify the blocking rule using `iptables -L -n`.

**Flag:** 80

**Validation:**
The flag should be the port number that was blocked.

**Hint:**
Use `iptables -A OUTPUT -p tcp --dport 80 -j DROP` to block outgoing traffic on port `80`.

---

### Conclusion
By completing these tasks, you will have identified and investigated the suspicious beacon and flood services, and mitigated the threat by containing the C2 communication. This exercise enhances your skills in incident response and network security.