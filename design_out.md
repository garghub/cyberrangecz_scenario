### Scenario: Mirai Botnet Investigation and Mitigation

#### INFO_LEVEL
**Scenario Title:** Mirai Botnet Investigation and Mitigation

**Scenario Description:**
You are an incident responder tasked with investigating and mitigating a Mirai botnet infection on your network. The botnet, specifically the Linux/Mirai-Hilix variant, targets Realtek & Huawei routers, exploiting vulnerabilities to deliver payloads and establish a botnet for DDoS attacks. Your goal is to identify the compromised hosts, understand the botnet's behavior, and implement containment measures.

**Learning Objectives:**
- Identify and investigate suspicious services related to the Mirai botnet.
- Detect and analyze the botnet's command-and-control (C2) communication.
- Implement containment measures to block C2 communication and mitigate the DDoS attack.

**Prerequisites:**
- Basic knowledge of Linux commands and network protocols.
- Familiarity with incident response procedures.

**Scenario Duration:** 60 minutes

---

#### ACCESS_LEVEL
**Entry Host:** bot1
**Username:** cyrano
**Password:** cyrano
**Access Method:** SSH

---

#### TRAINING_LEVEL 1
**Task:** Identify Suspicious Beacon Service

**Description:**
Investigate the services running on bot1 and identify the suspicious beacon service used by the Mirai botnet for C2 communication.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. List all running services using the `systemctl list-units --type=service` command.
3. Identify the suspicious beacon service related to the Mirai botnet.

**Flag:** bot-beacon-Hilix.sh.service

**Validation:**
- The flag must be the exact name of the suspicious beacon service.

**Hint:**
- Look for services with unusual names or those that are not part of the standard system services.

---

#### TRAINING_LEVEL 2
**Task:** Identify Suspicious Outbound IP and Port

**Description:**
Analyze the network connections on bot1 to identify the suspicious outbound IP address and port used for C2 communication.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. Use the `netstat -tuln` command to list all network connections.
3. Identify the suspicious outbound IP address and port used for C2 communication.

**Flag:** 192.168.70.5:44382

**Validation:**
- The flag must be the exact IP address and port used for C2 communication.

**Hint:**
- Look for connections to unusual IP addresses or ports that are not part of the standard network traffic.

---

#### TRAINING_LEVEL 3
**Task:** Contain C2 Communication

**Description:**
Implement containment measures to block the C2 communication between bot1 and the C2 server.

**Steps:**
1. SSH into bot1 using the provided credentials.
2. Use the `iptables` command to block the suspicious outbound IP address and port identified in the previous task.
3. Verify that the C2 communication is blocked by checking the network connections again.

**Flag:** 44382

**Validation:**
- The flag must be the exact port number used for C2 communication that was blocked.

**Hint:**
- Use the `iptables -A OUTPUT -p tcp --dport <port> -j DROP` command to block the port.

---

### Conclusion
By completing these tasks, you will have successfully identified the Mirai botnet's suspicious services and C2 communication, and implemented containment measures to mitigate the threat. This exercise enhances your incident response skills and prepares you for real-world cybersecurity challenges.