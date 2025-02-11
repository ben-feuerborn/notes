# Threat Modeling
> A ***systematic*** way of discovering **strengths** and **weaknesses** in software applications.

## STRIDE
Threat model that helps developers analyze security risks and implement mitigation early in the Software Development Lifecycle (SDLC).

| STAGE | DEFINITION |
| :--- | :--- |
| Spoofing | Impresonating someone else to gain unauthorized access. |
| Tampering | Modifying data or code maliciously. |
| Repudiation | Denying an action occured, without proof to verify it. |
| Information Disclosure | Exposing sensitive information to unauthorized parties. |
| Denial of Service (DoS) | Disrupting system availability to prevent legitimate access. |
| Elevation of Privilege | Gaining higher access rights than intended. |


### DREAD
A risk managment framework that helps quantify and prioritize security threats.

| RATING | HIGH (3) | MEDIUM (2) | LOW (1) |
| :--- | :--- | :--- | :--- |
| Damage Potential | Attacker can cause serious damage | Attacker can inflict moderate damage | Attacker can cause minor damage |
| Reproducibility | Attack can be reproduced every time | Attack can be reproduced within limits | Attack is very difficult to reproduce |
| Exploitability | Attack can be exploited with no knowledge | Attack requires skilled operator with fundamental knowledge | Attack requires exterme skill and in-depth knowledge |
| Affected Users | Majority of useres will be affected | Sizeable number of users will be affected | A very small percentage of users will be affected |
| Discoverability | Published information readily explains the attack | Attacker requires skills to discover attacks | Extreme skills are required to implement the attack |