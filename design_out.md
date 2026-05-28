 INFO_LEVEL:
```
Sandbox Overview:
The sandbox consists of three hosts: c2-server, target, and next-target. The c2-server is running a malicious backdoor named BRICKSTORM, which communicates with its C2 server over WebSocket using the DoH protocol. The target host has been compromised by this malware and is used for lateral movement to the next-target host.

The target host's user account (cyrano) has access to all three hosts via SSH, and there is a benign listener running on the target host listening on port 4444. The c2-server has a service named 'lab-checkin-listener' that listens for connections from the target host on port 4444.

The malware modifies the PATH environment variable to persist on the compromised system and uses SOCKS proxying, VSOCK proxying, multi-layered web service communication, and varied command execution to obscure its activities.
```

ACCESS_LEVEL:
```
Access Level:
The user (cyrano) has SSH access to all three hosts in the sandbox. The user account on the target host has sudo privileges. The user can access logs, config files, and deployed applications on each host.

Entry Point:
The user will start from the c2-server host using the provided credentials (username: cyrano, password: cyrano).
```

TRAINING_LEVEL 1:
```
Task: Identify/investigate/detect suspicious service running on the target host.

Hint: Use netstat or ss command to list open network connections and active services.

Flag: lab-checkin (service name)
```

TRAINING_LEVEL 2:
```
Task: Investigate the persistence mechanism used by the malware on the target host.

Hint: Look for modified system files, environment variables, or startup scripts that could indicate persistence.

Flag: PATH (environment variable)
```

TRAINING_LEVEL 3:
```
Task: Identify/investigate/detect malicious communication between the target and c2-server hosts.

Hint: Analyze network traffic, logs, or process listings to find indicators of compromise (IOCs) related to the BRICKSTORM backdoor.

Flag: 8090 (C2 Port address)
```