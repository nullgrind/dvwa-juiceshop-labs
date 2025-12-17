# Lab Environment

## Purpose
This lab environment supports web security practice using:
- DVWA (Apache + PHP + MySQL) on Ubuntu Server
- OWASP Juice Shop (Docker container) on Ubuntu Server
- Kali Linux as the attacker workstation
- Burp Suite as the intercepting proxy

## Topology (high level)
- Attacker: Kali Linux VM
- Target: Ubuntu Server VM (DVWA + Docker/Juice Shop)
- Network type: Internal
- Internet access for targets: No

### Apps
- DVWA security level used in labs: Low → Medium → High (document per lab)
- OWASP Juice Shop image: grep juiceshop

### Juice Shop (Docker)
- Start: `docker run ...` or `docker compose up -d` 
- Stop: `docker stop <container>` or `docker compose down`
- Reset: remove container + re-run 

## Evidence Storage
- Screenshots: `evidence/<app>/`
- Scan outputs: `evidence/scans/`
- Burp exports (sanitized): `evidence/burp/`

