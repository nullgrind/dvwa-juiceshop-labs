# Lab Rules & OPSEC

## Scope
All activities in this repository are performed exclusively in isolated lab
environments owned and controlled by the author.

Targets include:
- DVWA running on a local Ubuntu Server VM
- OWASP Juice Shop running in a local Docker container

No testing is performed against systems, networks, or applications
without explicit authorization.

## Environment Isolation
- Attacker machine: Kali Linux VM
- Targets are accessible only from the lab network
- No internet-facing scanning or exploitation

## Data Handling
- All credentials are lab-generated and reused nowhere else
- Any tokens, cookies, or session identifiers shown in evidence are redacted
- Screenshots are sanitized before publication

## Tool Usage
- Automated tools (burpsuite, nmap, sqlmap, nikto, hydra) are used only after
  manual validation of attack surface
- Tool output is reviewed and filtered before being committed

## Evidence Policy
- Evidence is collected to demonstrate understanding, not exploitation
- No weaponized payloads targeting real services are published

## Legal & Ethical Notice
This repository is for educational and defensive security training only.
