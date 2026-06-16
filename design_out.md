### Scenario: HackingTeam Android Implant Investigation

**INFO_LEVEL:**
The victim host in the network has been compromised by an Android implant spyware from the HackingTeam malware family. This spyware requests extensive permissions, including access to SMS, contacts, location, and more. It uses string encryption to hide its activities and communicates with C2 servers via HTTPS. The malware can exfiltrate data, execute commands, and maintain persistence on the device.

**ACCESS_LEVEL:**
You have SSH access to the victim host with the username `cyrano` and password `cyrano`. The victim host is part of a network that includes a spy-server and a colleague host. You can investigate the victim host and any reachable hosts from it.

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious hidden directory used by the spyware.
**Description:** The spyware creates hidden directories to store its components and collected data. Investigate the victim host to find the hidden directory used by the spyware.
**Hint:** Check the file system for directories with unusual names or permissions.
**Flag:** /var/lib/.monitor

**TRAINING_LEVEL 2:**
**Task:** Identify the keylogging mechanism used by the spyware.
**Description:** The spyware logs keystrokes to capture sensitive information. Investigate the victim host to find the file used for keylogging.
**Hint:** Look for files in the hidden directory that contain logged commands or keystrokes.
**Flag:** /var/lib/.monitor/keylog.log

**TRAINING_LEVEL 3:**
**Task:** Identify the data exfiltration mechanism used by the spyware.
**Description:** The spyware exfiltrates collected data to a C2 server. Investigate the victim host to find the script used for exfiltration.
**Hint:** Check for scripts in the hidden directory that send data to an external server.
**Flag:** /usr/local/lib/.monitor/exfil.sh

---

This scenario is designed to align with the provided MISP event, security profile, topology, and Ansible configuration. The tasks are structured to investigate the HackingTeam Android implant spyware on the victim host, focusing on identifying hidden directories, keylogging mechanisms, and data exfiltration scripts. The scenario adheres to the sandbox constraints and uses only the indicators and artifacts present in the provided data.