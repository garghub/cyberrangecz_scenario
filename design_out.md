 Based on the provided MISP event, sandbox topology, and Ansible configuration, I will generate a deployable KYPO scenario aligned with the given constraints.

---

**INFO_LEVEL**
- Scenario Name: Akira Ransomware Investigation
- Description: This exercise simulates an investigation of the Akira ransomware attack on a Linux network. The goal is to identify indicators of compromise, detect lateral movement, and recover exfiltrated data.

**ACCESS_LEVEL**
- Access Level: Network Administrator
- Target Host: victim (192.168.90.10)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1**

**Task**
Title: Identify C2 IP address
Description: Investigate network traffic to identify the IP address of the command and control (C2) server.
Expected Outcome: The C2 IP address should be identified from the MISP event or by analyzing network traffic logs.
Validation: Compare the obtained IP with the one provided in the MISP event.
Hint: Look for unusual outbound connections, especially those using SSH (sshd.exe) or other known C2 protocols.

**TRAINING_LEVEL 2**

**Task**
Title: Identify Exfiltration IP address
Description: Determine the IP address of the server used for data exfiltration during the ransomware attack.
Expected Outcome: The exfiltration IP address should be identified from the MISP event or by analyzing network traffic logs.
Validation: Compare the obtained IP with the one provided in the MISP event.
Hint: Look for unusual outbound connections, especially those using Rclone (Rclone.exe) or other known data exfiltration tools.

**TRAINING_LEVEL 3**

**Task**
Title: Recover Exfiltrated Data
Description: Retrieve the exfiltrated data from the sandbox environment and compare it with the original files to verify their integrity.
Expected Outcome: The exfiltrated data should be recovered and compared with the original files to ensure they match.
Validation: Compare the recovered data with the original files provided in the MISP event examples (quarterly_report.txt, employee_data.csv).
Hint: Look for hidden files or directories where the exfiltrated data might be stored (e.g., /home/cyrano/.flag).