 INFO_LEVEL
------------

The provided MISP event describes an incident involving the Akira Ransomware, a type of ransomware that targets both Windows and Linux systems. The malware is known to encrypt files on infected systems and demand a ransom payment from victims to restore access. It has been observed using lateral movement, exfiltration, and persistence mechanisms.

ACCESS_LEVEL
-------------

The sandbox environment consists of three hosts: c2-server (Ubuntu), victim (Ubuntu), and exfil-server (Ubuntu). The user account "cyrano" has been created on all hosts with the same password. SSH access is available between the hosts, and the victim host has been preconfigured to trust the exfil-server's public key.

TRAINING_LEVEL 1
-----------------

Task: Identify/investigate/detect suspicious outbound IP to C2 server

Objective: Find the IP address of the C2 server used by the Akira Ransomware in this scenario.

Hint: Check the network traffic from the victim host and look for connections to an unknown IP address.

Q/A:
- What is the IP address of the C2 server? (Answer: Unknown, as it's not provided in the MISP event)

TRAINING_LEVEL 2
-----------------

Task: Identify/investigate/detect suspicious outbound Port to C2 server

Objective: Find the port number used by the Akira Ransomware for communication with its C2 server.

Hint: Check the network traffic from the victim host and look for connections using an unknown port number.

Q/A:
- What is the port number used by the Akira Ransomware for communication with its C2 server? (Answer: Unknown, as it's not provided in the MISP event)

TRAINING_LEVEL 3
-----------------

Task: Identify/investigate/detect suspicious payload file

Objective: Find the filename of the Akira Ransomware payload on the victim host.

Hint: Look for executable files with unusual names or hashes that were dropped by the ransomware.

Q/A:
- What is the filename of the Akira Ransomware payload on the victim host? (Answer: AnyDesk.exe, Veeam-Get-Creds.ps1, Winscp.rnd, Sysmon.exe)