# Brief overview of Atomic Red Team

## What Is Atomic Red Team?

Red Canary created Atomic Red Team.

Atomic Red Team is:

> A library of small, controlled attack simulations mapped to MITRE ATT&CK.

Instead of running full-blown penetration tests, it lets you safely simulate specific attacker techniques on a system.

Think of it as:

🧪 “Unit testing” for your security controls.


## Why It Exists

Many organizations deploy:

 - SIEM

 - EDR

 - Firewall

 - IDS

 - Logging agents

But they don’t verify:

 - ❓ Are detections actually working?
 - ❓ Will alerts trigger for real attack behavior?
 - ❓ Are logs being collected properly?

Atomic Red Team answers those questions.



## How It Connects to MITRE ATT&CK

It is mapped to:

 - MITRE Corporation’s
 - MITRE ATT&CK

For example:

Technique:
T1059 – Command and Scripting Interpreter

Atomic Red Team provides:

 - Small test scripts

 - Safe commands

 - Cleanup steps

So you can simulate that behavior and check if your SIEM detects it.



## What It Actually Does

Atomic tests simulate things like:

 - Credential dumping behavior

 - PowerShell abuse

 - Scheduled task persistence

 - Registry modification

 - Lateral movement techniques

 - Suspicious command-line activity

Each “atomic test” is:

 - Small

 - Controlled

 - Specific to one technique

 - Easy to clean up

It’s not a full malware tool.
It’s controlled security validation.