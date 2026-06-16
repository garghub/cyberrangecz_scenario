### Scenario: Umbreon Rootkit Investigation

**INFO_LEVEL:**
The Umbreon rootkit is a Pokémon-themed Linux rootkit that targets both x86 and ARM systems. It is designed to hide processes, files, and network connections from system administrators. The rootkit uses various techniques to maintain persistence and evade detection. Your task is to investigate and analyze the compromised systems to identify and mitigate the rootkit's presence.

**ACCESS_LEVEL:**
- Entry Host: victim (IP: 192.168.50.5)
- Username: cyrano
- Password: cyrano

**TRAINING_LEVEL 1:**
**Task:** Identify the suspicious shared library injection.
**Description:** Investigate the system for any suspicious shared libraries that might be used by the Umbreon rootkit.
**Hint:** Check the /lib/x86_64-linux-gnu/ directory for any unusual files.
**Flag:** Shared Library Identifier

**TRAINING_LEVEL 2:**
**Task:** Identify the malicious system-wide preload configuration.
**Description:** Examine the system-wide preload configuration to detect any malicious entries that might be used by the Umbreon rootkit.
**Hint:** Check the /etc/ld.so.preload file for any suspicious entries.
**Flag:** Preload Configuration Identifier

**TRAINING_LEVEL 3:**
**Task:** Identify the hidden privileged account.
**Description:** Investigate the system for any hidden privileged accounts that might have been created by the Umbreon rootkit.
**Hint:** Check the /etc/passwd and /etc/shadow files for any unusual user entries.
**Flag:** User Account Identifier