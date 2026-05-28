### Scenario: BRICKSTORM Backdoor Investigation

#### INFO_LEVEL
The BRICKSTORM backdoor is a sophisticated malware that uses multiple evasion techniques, including SOCKS proxying, multi-layered web service communication, and varied command execution. It has been observed in Linux environments and is known for its persistence mechanisms and lateral movement capabilities. Your task is to investigate and mitigate this threat.

#### ACCESS_LEVEL
You have SSH access to the `target` host with the username `cyrano` and password `cyrano`. From there, you can access the `next-target` host using SSH.

#### TRAINING_LEVEL 1
**Task:** Identify the suspicious file associated with the BRICKSTORM backdoor.

**Description:**
Investigate the `target` host for suspicious files. The BRICKSTORM backdoor is known to use a file named `updatemgr`. Locate this file and determine its properties.

**Hint:**
Check the `/usr/java/jre-vmware/bin/` directory for suspicious files.

**Validation:**
The flag is the name of the suspicious file. Submit the flag as `updatemgr`.

#### TRAINING_LEVEL 2
**Task:** Investigate the persistence mechanism used by the BRICKSTORM backdoor.

**Description:**
The BRICKSTORM backdoor is known to modify the PATH environment variable for persistence. Investigate the environment variables on the `target` host to identify any suspicious modifications.

**Hint:**
Check the PATH environment variable for unusual entries.

**Validation:**
The flag is the name of the environment variable modified for persistence. Submit the flag as `PATH`.

#### TRAINING_LEVEL 3
**Task:** Identify the C2 communication details used by the BRICKSTORM backdoor.

**Description:**
The BRICKSTORM backdoor communicates with a C2 server. Investigate the network connections on the `target` host to identify the C2 IP address and port.

**Hint:**
Check the network connections and logs for outbound connections to suspicious IPs and ports.

**Validation:**
The flag is the C2 IP address and port. Submit the flag as `8.8.8.8:443`.

---

This scenario aligns with the provided MISP event, sandbox topology, and security profile, ensuring a realistic and deployable exercise for investigating and mitigating the BRICKSTORM backdoor.