Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, here's a deployable scenario for the KYPO/CyberRangeCZ platform:

---

**Scenario Name:** Rhombus Botnet Investigation

**Objective:** Investigate and contain the Rhombus botnet (Linux/IRCTelnet) infection on compromised systems.

**Entry Point:**
- Host: bot1
- Username: cyrano
- Password: cyrano
- Access Method: SSH (port 22)

**INFO_LEVEL:**
1. You are a cybersecurity analyst responding to reports of unusual network traffic from internal systems.
2. The Rhombus botnet (Linux/IRCTelnet) has been detected in your network, targeting VPS and IoT devices.
3. Your task is to investigate the compromised systems, identify the command-and-control (C2) infrastructure, and contain the threat.

**ACCESS_LEVEL:**
1. SSH access to bot1 with user credentials provided.
2. From bot1, you can SSH to bot2 using the established trust relationship.
3. You have sudo privileges on both bot1 and bot2.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious beacon service communicating with the C2 server.
**Description:**
- Investigate the systemd services running on bot1.
- Identify the service responsible for beaconing to the C2 server.
- The service name will be your flag.
**Hint:** Look for services with unusual names or descriptions related to system health or updates.
**Q/A:**
- Q: What is the name of the beacon service?
- A: bot-beacon-RHOMBUS.service

**TRAINING_LEVEL 2:**
**Task:** Identify the persistence mechanism used by the malware.
**Description:**
- Examine the systemd timers and services on bot1.
- Identify the service responsible for maintaining persistence.
- The service name will be your flag.
**Hint:** Look for services with unusual names or descriptions related to system updates or health checks.
**Q/A:**
- Q: What is the name of the persistence service?
- A: system-update-checker.service

**TRAINING_LEVEL 3:**
**Task:** Contain the C2 communication by blocking the outbound connection.
**Description:**
- Identify the C2 server IP address and port from the beacon service configuration.
- Implement a firewall rule to block outbound connections to the C2 server.
- The port number used to block the connection will be your flag.
**Hint:** Check the beacon script or service configuration for the C2 server details.
**Q/A:**
- Q: What is the port number used to block the C2 communication?
- A: 2222

---

This scenario is strictly aligned with the provided sandbox environment and MISP event. All tasks reference real hosts, services, and file paths from the topology and Ansible data. The scenario focuses on investigating and containing the Rhombus botnet infection, with tasks designed to match the security profile and training level examples.