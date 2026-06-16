Based on the provided MISP event, security profile, topology, Ansible configuration, and training level examples, I've created a deployable scenario for the KYPO/CyberRangeCZ platform. The scenario focuses on investigating and responding to a BiBi-Linux Wiper malware incident.

---

**INFO_LEVEL**
The scenario simulates a destructive malware attack using the BiBi-Linux Wiper. This malware is designed to corrupt files with random data, manipulate partition tables, and append mocking 'BiBi' extensions. It has no ransom note or command-and-control (C2) servers, indicating its sole purpose is data destruction. The malware targets Linux systems and has been detected on the workstation and file-server hosts in the network.

**ACCESS_LEVEL**
You will start with access to the workstation host as the user 'cyrano' with the password 'cyrano'. From there, you can investigate the compromise, analyze the malware, and take appropriate response actions. You may need to access other hosts in the network as part of your investigation.

---

**TRAINING_LEVEL 1**
**Task:** Investigate suspicious file destruction activity
**Description:** Users have reported that important files on the workstation have been corrupted or renamed. Investigate the file destruction activity and identify any suspicious processes or artifacts related to this incident.
**Hint:** Check the system logs and file modification timestamps for any unusual activity.
**Flag:** Destructive Activity Identifier

**Validation:**
- The student must identify the suspicious process related to file destruction.
- The student must provide the path to the wiper binary.
- The student must identify at least three files that have been modified or renamed by the wiper malware.

---

**TRAINING_LEVEL 2**
**Task:** Analyze malware execution logs and forensic artifacts
**Description:** Examine the logs and artifacts left by the wiper malware to understand its behavior and impact. Look for any evidence of anti-forensic activity, such as log clearing or disk manipulation.
**Hint:** Check the system logs for any unusual activity, such as log clearing or disk manipulation.
**Flag:** Log Artifact Identifier

**Validation:**
- The student must identify at least three logs that have been cleared or modified by the wiper malware.
- The student must provide the path to the artifact that simulates MBR overwrite.
- The student must identify the command-and-control (C2) server that the wiper malware attempted to report to.

---

**TRAINING_LEVEL 3**
**Task:** Contain and disable malicious timers and destructive services
**Description:** To prevent further damage, you need to contain and disable the malicious timers and services associated with the wiper malware. Investigate the systemd services and timers to identify and disable any suspicious entries.
**Hint:** Check the systemd services and timers for any unusual entries.
**Flag:** Persistence Identifier

**Validation:**
- The student must identify and disable the malicious systemd service associated with the wiper malware.
- The student must identify and disable the malicious systemd timer associated with the wiper malware.
- The student must verify that the wiper malware can no longer execute automatically after a system reboot.

---

This scenario provides a realistic and challenging exercise for incident response teams to investigate, analyze, and respond to a destructive malware attack. The tasks are designed to align with the NICE Incident Response profile and the provided MISP event, while also considering the sandbox environment and Ansible configuration.