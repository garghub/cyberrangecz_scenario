 INFO_LEVEL:
```
Sandbox Overview:
The sandbox consists of three hosts: c2-server, target, and next-target. The operating system on all hosts is Ubuntu. The c2-server hosts a malicious Linux/Kobalos backdoor that communicates with the target host over SSH on port 7070.

MISP Event:
The MISP event indicates a Kobalos backdoor targeting high performance computing infrastructure. The malware is portable to various operating systems, including Linux, BSD, Solaris, and possibly AIX and Windows. The malware exhibits C2, lateral movement, exfiltration, persistence, and SSH credential stealing behaviors.

Security Profile:
The security profile specifies an Incident Response team responsible for investigating, analyzing, and responding to network cybersecurity incidents.
```

ACCESS_LEVEL:
```
Access Model:
- Username: cyrano
- Password: cyrano
- Access Method: SSH
- Privilege Boundaries: sudo access on target and next-target hosts
- Target or Victim Entry Host: target
```

TRAINING_LEVEL 1:
```
Task: Identify/investigate/detect suspicious service running on the target host.

Hint: Use netstat, ss, or lsof commands to list open network connections and running processes.

Validation: Check if the service named "sshd" is running on the target host.

Flag: sshd
```

TRAINING_LEVEL 2:
```
Task: Identify/investigate/detect persistence mechanism used by the malware on the target host.

Hint: Look for files or services that start automatically at boot time, such as systemd units, cron jobs, or startup scripts.

Validation: Check if a service named "ns.pid" exists and is started at boot time.

Flag: ns.pid
```

TRAINING_LEVEL 3:
```
Task: Identify/investigate/detect data exfiltration from the target host to the c2-server.

Hint: Analyze network traffic, logs, and file system activity for signs of data transfer.

Validation: Check if there is any outbound SSH traffic from the target host to the IP address 151.80.57.191 on port 7070. Also, look for the presence of a file named "e094dd02cc954b6104791925e0d1880782b046cf" on the target host.

Flag: 151.80.57.191 (C2 IP address) and e094dd02cc954b6104791925e0d1880782b046cf (filename)
```