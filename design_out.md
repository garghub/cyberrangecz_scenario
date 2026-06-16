### Scenario: Godfather Android Banking Trojan Investigation

**INFO_LEVEL**
The victim host in your network has been compromised by the Godfather Android banking Trojan. Your task is to investigate the compromise, identify the indicators of compromise (IOCs), and contain the threat. The Godfather Trojan is designed to harvest login credentials for banking applications and other financial services, exfiltrate data, and establish reverse shell connections.

**ACCESS_LEVEL**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is `victim` with the IP address `192.168.60.10`. You also have access to the C2 server with the IP address `192.168.60.20`.

**TRAINING_LEVEL 1**
**Task:** Identify the suspicious scheduled task/timer used by the malware.
**Description:** The Godfather Trojan uses a scheduled task to maintain persistence on the victim host. Investigate the systemd timers and identify the suspicious timer used by the malware.
**Hint:** Look for timers related to network diagnostics or health checks.
**Flag:** `GoogleProtect.timer`

**TRAINING_LEVEL 2**
**Task:** Identify the hidden malware directory.
**Description:** The Godfather Trojan creates a hidden directory to store its components. Investigate the file system and identify the hidden directory used by the malware.
**Hint:** Look for directories with unusual names or paths.
**Flag:** `/var/lib/.netd`

**TRAINING_LEVEL 3**
**Task:** Identify the reverse shell mechanism.
**Description:** The Godfather Trojan establishes a reverse shell connection to the C2 server. Investigate the systemd services and identify the script used to establish the reverse shell connection.
**Hint:** Look for scripts in the hidden malware directory.
**Flag:** `/usr/local/lib/.netd/revshell.sh`