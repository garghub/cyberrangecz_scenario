### Scenario: Akira Ransomware Incident Response

#### INFO_LEVEL
The Akira ransomware has been detected in your network. This ransomware is known for its double-extortion techniques, involving both data exfiltration and enterprise-wide encryption. Your task is to investigate the incident, identify the indicators of compromise (IOCs), and contain the threat.

#### ACCESS_LEVEL
You have access to the victim machine with the following credentials:
- **Hostname:** victim
- **Username:** cyrano
- **Password:** cyrano

You can use SSH to connect to the victim machine and perform your investigations.

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious payload file associated with the Akira ransomware.

**Description:**
The Akira ransomware is known to drop specific payload files on infected systems. Your task is to identify the suspicious payload file on the victim machine.

**Steps:**
1. Connect to the victim machine using SSH.
2. Search for files with suspicious names or extensions.
3. Identify the file named "akira" which is associated with the Akira ransomware.

**Flag:** The filename of the suspicious payload file.

**Hint:** Look for files with unusual names or extensions in the home directory of the victim machine.

#### TRAINING_LEVEL 2
**Task:** Investigate the ransom note left by the Akira ransomware.

**Description:**
The Akira ransomware leaves a ransom note on infected systems. Your task is to locate and investigate this ransom note to understand the ransomware's demands and instructions.

**Steps:**
1. Connect to the victim machine using SSH.
2. Search for files named "RANSOM_NOTE.txt" or similar.
3. Read the contents of the ransom note to understand the ransomware's demands.

**Flag:** The filename of the ransom note.

**Hint:** The ransom note is typically placed in the home directory of the victim machine.

#### TRAINING_LEVEL 3
**Task:** Identify the exfiltrated data from the victim machine.

**Description:**
The Akira ransomware is known to exfiltrate data from infected systems. Your task is to identify the exfiltrated data on the exfiltration server.

**Steps:**
1. Connect to the exfiltration server using SSH.
2. Search for directories or files that contain exfiltrated data.
3. Identify the exfiltrated data and note its location.

**Flag:** The filename or path of the exfiltrated data.

**Hint:** The exfiltrated data is typically stored in a specific directory on the exfiltration server.

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to guide the investigator through the process of identifying and investigating the Akira ransomware incident.